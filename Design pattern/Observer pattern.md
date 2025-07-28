# ✅ Daily CS :  Observer Pattern (옵서버 패턴)

>❓
>옵서버 패턴이란 무엇이며, 어떤 상황에서 사용될까?
>장단점과 주요 구성요소는?

***

## 📌 정의

🔷 **객체의 상태 변화가 있을 때, 그에 따라 의존 관계에 있는 다른 객체들에게 자동으로 알림이 전달되도록 하는 패턴**


-  주체(`Subject`)의 상태가 바뀌면 구독자(`Observers`)들이 자동으로 업데이트


- `Publish-Subscribe` (발행-구독) 패턴이라고도 함

***

## 🧩 구성 요소

| 구성 요소                | 설명                                       |
| -------------------- | ---------------------------------------- |
| **Subject**          | 상태를 가지고 있으며, 옵서버를 등록/제거하고 상태 변화 시 알림을 보냄 |
| **Observer**         | Subject의 상태 변화를 감지하여 행동을 취하는 객체          |
| **ConcreteSubject**  | 실제 상태를 보유하고 변경 시 옵서버들에게 알림 전송            |
| **ConcreteObserver** | 상태가 변경될 때 어떤 반응을 보일지 구현                  |

***

## 🖼️ 구조 그림 (의사 코드 기준)

```
+----------------+       +---------------------+
|   Subject      |<>---->|     Observer        |
+----------------+       +---------------------+
| + attach()     |       | + update()          |
| + detach()     |       +---------------------+
| + notify()     |
+----------------+
```

***

## 🧑‍💻 코드 예시 (Java)

```java
// Subject
interface Subject {
void attach(Observer o);
void detach(Observer o);
void notifyObservers();
}

// Observer
interface Observer {
void update(String message);
}

// Concrete Subject
class NewsAgency implements Subject {
    private List<Observer> observers = new ArrayList<>();
    private String news;

    public void setNews(String news) {
        this.news = news;
        notifyObservers();
    }

    public void attach(Observer o) { observers.add(o); }
    public void detach(Observer o) { observers.remove(o); }
    public void notifyObservers() {
        for (Observer o : observers) {
            o.update(news);
        }
    }
}

// Concrete Observer
class Subscriber implements Observer {
    private String name;
    public Subscriber(String name) { this.name = name; }

    public void update(String message) {
        System.out.println(name + " received: " + message);
    }
}
```

***

## 💡 사용 예시

🔷 **GUI 이벤트 시스템**: 버튼 클릭 시 여러 리스너가 반응

🔷 **뉴스/주식 알림**: 주가 변화 → 여러 구독자에게 푸시

🔷 **모니터링 시스템**: 서버 상태 변경 → 관리자 대시보드에 즉시 반영

***

### ✅ 장점

- 객체 간의 결합도 낮음 (Low Coupling)

- 확장성 우수: 옵서버를 자유롭게 추가/삭제 가능

- 실시간 반응성 구현 용이

### ❌ 단점

- 옵서버 수가 많을 경우 성능 저하

- 디버깅 어려움: 어떤 옵서버가 알림을 받았는지 추적 어려움

***

