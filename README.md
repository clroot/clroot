<h1 align="center">Backend Engineer · Full-stack capable</h1>
<p align="center">
  <em>반복되는 큰 흐름은 고정하고, 바뀌는 정책만 제어하는 구조를 선호합니다</em>
</p>

---

## 👋 About

반복되는 큰 흐름은 고정하고,
바뀌는 정책만 제어하는 구조를 중심으로 개발해왔습니다.

그래서 기능을 빠르게 추가하는 것보다,
정책이 추가되거나 수정될 때 기존 흐름이 흔들리지 않는지를 먼저 봅니다.

---

## 🛠 Tech Stack

**Backend**
- Kotlin, Spring Boot 4.0
- JPA / Hibernate Reactive, PostgreSQL
- Kotlin Coroutines, Kafka

**Frontend**
- TypeScript, React 19, Next.js 15+
- TanStack Query, Zustand

**Test / Infra**
- Kotest, MockK, ArchUnit, Testcontainers
- Docker, Docker Compose

---

## 💡 What I've Been Doing

- 여러 고객사에 **유사하지만 조금씩 다른 서비스**를 제공하는 환경에서 개발
- 출결, 정산, 인증, 컨설팅처럼 **큰 흐름은 고정되고 정책만 달라지는 도메인**을 주로 담당
- 반복되는 구조는 공통화하고, 정책 변화만 국소적으로 흡수하는 방향을 선택
- 기획자가 없는 환경에서 정책을 정리하고 기술적 의사결정을 함께 수행

---

## 📌 Highlight Projects

### ✨ Selah
개인 프로젝트 (Backend + Frontend 단독)

서버조차 평문을 알 수 없는 개인 기록 서비스

- **E2E 암호화**: AES-256-GCM + PBKDF2/HKDF 키 파생, Web Crypto API 활용
- **Hexagonal Architecture + DDD**: ArchUnit으로 아키텍처 규칙 자동 검증
- **Multi-OAuth**: Google, Apple, Kakao 지원 및 계정 연결
- 보안·복구·편의 기능 사이의 트레이드오프를 문서로 명시

🔗 https://github.com/clroot/selah-api-server
🔗 https://github.com/clroot/selah-web-application

---

### 📦 Hibernate Reactive Coroutines
개인 프로젝트 (오픈소스 라이브러리)

Spring Data JPA 스타일을 Hibernate Reactive + Kotlin Coroutines 환경에서 사용할 수 있게 해주는 라이브러리

- **PartTree 기반 동적 쿼리 생성**: Spring Data 메서드 네이밍 규칙 호환
- **Spring Transaction 통합**: Propagation, Isolation, Timeout 지원
- **Spring Boot 3.x & 4.0 멀티버전 지원**
- JitPack을 통한 배포

🔗 https://github.com/clroot/hibernate-reactive-coroutines

---

### 🧱 Internal SDK (Private)
B2B 교육/장학 서비스용 사내 공통 SDK

- **모듈화된 SDK 아키텍처**: 인증, 알림, 출결, 컨설팅, 강의, 외부 API 연동 등 13+ 모듈
- **Hexagonal Architecture**: 도메인/애플리케이션/어댑터 계층 분리
- **Kafka 기반 이벤트 처리**
- 반복되는 사업 흐름을 공통 구조로 고정하고, 정책 변화만 제어
- Testcontainers 기반 통합 테스트로 안정성 확보

> 실제 운영 서비스에서 사용 중 (비공개 레포지토리)

---

## 🧠 How I Think About Code

> “반복되는 것을 매번 다시 만들지 않기 위해,  
> 바뀌는 부분만 안전하게 다룰 수 있는 구조를 고민합니다.”

- 구조는 오래 유지되고, 정책만 교체될 수 있어야 한다고 생각합니다  
- 사이드 이펙트가 넓게 퍼지는 변경을 가장 위험하다고 봅니다  
- 기술 선택보다, **이 구조가 얼마나 오래 버틸 수 있는지**를 더 중요하게 봅니다  

<p align="center">
  <em>계속 성장하는 개발자를 목표로 합니다.</em>
</p>

[![Solved.ac 프로필](http://mazassumnida.wtf/api/generate_badge?boj=abcdkh1209)](https://solved.ac/abcdkh1209)
