# ✅ Daily CS : DNS(Domain Name System)


> ❓
>DNS는 무엇이고, 어떻게 동작하는가?
>재귀 쿼리와 반복 쿼리, 캐싱의 개념은?

---

## 📌 정의

🔷 D사람이 읽기 쉬운 도메인 이름(www.example.com)을 IP 주소로 변환해주는 분산형 데이터베이스 시스템

-  사용자가 IP 대신 도메인을 이용할 수 있게 하여 접근성을 높임

-  전 세계에 분산된 네임서버 계층 구조로 동작

---

## 🏛 계층 구조

| 계층                | 역할                                  | 예시                 |
| ----------------- | ----------------------------------- | ------------------ |
| **Root**          | 최상위 네임서버, TLD 서버 정보 제공              | `.`                |
| **TLD**           | Top Level Domain 서버, 하위 권한 서버 정보 제공 | `.com`, `.org`     |
| **Authoritative** | 실제 도메인 정보(IP) 보유                    | `example.com` 네임서버 |


---

## 🔁 동작 방식 (재귀 쿼리 예시)

- 클라이언트 → `Local DNS resolver`에 www.example.com 요청


- `Local Resolver` → 루트 서버로 .com TLD 정보 요청


- `Root Server` → .com TLD 서버 주소 반환


- `Local Resolver` → .com TLD 서버에 example.com 정보 요청


- TLD Server → example.com의 `Authoritative 서버` 주소 반환


- `Local Resolver` → `Authoritative 서버`에 IP 요청


- `Authoritative 서버` → IP 주소 반환


- `Local Resolver`  → 클라이언트에 IP 응답

---

## 🧩 쿼리 방식

| 방식                | 특징                                  |
| ----------------- | ----------------------------------- |
| **재귀(Recursive)** | 리졸버가 최종 IP까지 찾아서 응답                 |
| **반복(Iterative)** | 각 서버가 다음 단계 서버 주소만 반환, 클라이언트가 계속 질의 |

---

## 🗄 캐싱

- `DNS 캐시`: TTL(Time To Live) 동안 응답을 저장하여 속도 향상


- 위치: OS, 브라우저, `Local Resolver`, `ISP DNS 서버` 등


- TTL이 만료되면 재질의 수행

---

## 🧠 활용 사례

- CDN 연동: 지리적으로 가까운 엣지 서버로 트래픽 유도


- 도메인 기반 로드밸런싱: A 레코드 다중 IP로 분산


- 서비스 장애 대응: DNS Failover로 대체 IP 제공

---

## ❗ 주의할 점

- TTL이 길면 변경 반영이 늦음, 짧으면 캐시 HIT 감소로 쿼리 부하↑


- `DNS Spoofing`/`Cache Poisoning` 방지를 위해 `DNSSEC` 사용 권장