<h1 align="center">Backend Engineer · Full-stack capable</h1>
<p align="center">
  <em>반복되는 큰 흐름은 고정하고, 바뀌는 정책만 제어하는 구조를 선호합니다</em>
</p>

---

## 👋 About

반복되는 큰 흐름은 고정하고, 바뀌는 정책만 제어하는 구조를 중심으로 개발해왔습니다.

그래서 기능을 빠르게 추가하는 것보다, 정책이 추가되거나 수정될 때 기존 흐름이 흔들리지 않는지를 먼저 봅니다.

주로 Kotlin + Spring 기반의 백엔드 시스템을 설계하고, 필요에 따라 Next.js (React) 기반의 프론트엔드 개발도 함께 진행합니다.

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

## 📌 Highlight Projects

### 📦 Hibernate Reactive Coroutines
**개인 프로젝트 (오픈소스 라이브러리)**

Spring Data JPA 스타일을 Hibernate Reactive + Kotlin Coroutines 환경에서 사용할 수 있게 해주는 라이브러리입니다.

- **PartTree 기반 동적 쿼리 생성**: Spring Data 메서드 네이밍 규칙 호환, 36개 조건 연산자 지원 (findBy, countBy, existsBy, deleteBy)
- **Spring Transaction 통합**: Propagation, Isolation, Timeout 지원
- **Spring Boot 3.x & 4.0 멀티버전 지원**

🔗 [hibernate-reactive-coroutines on GitHub](https://github.com/clroot/hibernate-reactive-coroutines)

---

### 📊 Kotlin Excel DSL
**개인 프로젝트 (오픈소스 라이브러리)**

Kotlin DSL로 Excel 파일을 타입 안전하고 직관적으로 생성할 수 있게 해주는 라이브러리입니다.

- **Hybrid API**: 단순한 케이스는 어노테이션(`@Column`)으로, 복잡한 케이스는 DSL(`excel { }`)로 처리
- **CSS-like Styling**: 컬럼 단위 스타일링과 사전 정의된 테마(Modern, Minimal, Classic) 지원
- **Header Groups**: 다중 행 헤더와 자동 셀 병합 지원
- **SXSSF 스트리밍**: 대용량 데이터 렌더링 시 메모리 효율적 처리

🔗 [kotlin-excel-dsl on GitHub](https://github.com/clroot/kotlin-excel-dsl)

---

### 🧱 Internal SDK (Private)
**B2B 교육/장학 서비스용 사내 공통 SDK**

여러 고객사에 유사하지만 조금씩 다른 서비스를 제공하는 환경에서, 반복되는 비즈니스 로직을 표준화하고 재사용성을 극대화하기 위해 개발했습니다.

- **모듈화된 SDK 아키텍처**: 인증, 상담, 강의, 알림 등 13개 핵심 도메인 모듈화
- **Hexagonal Architecture + DDD**: 도메인/애플리케이션/어댑터 계층 분리, ArchUnit으로 규칙 강제
- **Hook + Policy 패턴**: AOP 기반 타입 바인딩으로 UseCase에 자동 적용되는 Hook과, 조합 가능한 순수 함수 기반 Policy로 비즈니스 규칙 검증
- **Kafka 기반 이벤트 처리**로 시스템 간 결합도 감소
- Testcontainers 기반 통합 테스트로 안정성 확보

> 다수의 실제 운영 서비스에서 핵심적인 역할을 수행하고 있습니다. (비공개 레포지토리)

---

### ✨ Selah
**개인 프로젝트 (Backend + Frontend 단독)**

서버조차 평문을 알 수 없는 개인 기록 서비스입니다. E2E 암호화 기술을 적용하여 사용자의 프라이버시를 최대한 보장합니다.

- **E2E 암호화**: AES-256-GCM + PBKDF2/HKDF 키 파생, Web Crypto API 활용
- **복구 키 기반 3단계 복구 시스템**: PIN 분실 시에도 데이터 복구 가능
- **Hexagonal Architecture + DDD**: ArchUnit으로 아키텍처 규칙 자동 검증
- **Multi-OAuth**: Google, Apple, Kakao 지원 및 계정 연결

🔗 [Selah API Server](https://github.com/clroot/selah-api-server)
🔗 [Selah Web Application](https://github.com/clroot/selah-web-application)

---

## 👨‍💻 Other Projects

### Company

- **B2B 교육 플랫폼 개발**: 다수 고객사를 위한 SaaS형 학습 관리 시스템(LMS)을 개발하고 운영했습니다. (Kotlin, Next.js)
- **레거시 시스템 현대화**: PHP/그누보드4 기반의 레거시 시스템을 Java/Spring + React(Vite) 기반의 API 서버/클라이언트 구조로 전환했습니다.
- **사내 풀스택 보일러플레이트**: Hexagonal Architecture 기반의 Kotlin 백엔드와 Next.js 프론트엔드로 구성된 표준 템플릿을 개발하여 신규 프로젝트의 생산성을 향상시켰습니다.
- **운영 자동화 스크립트**: 데이터 마이그레이션, 통계 집계, 외부 API 연동 등 반복적인 운영 업무를 자동화하는 Python 스크립트를 개발했습니다.

---

## 🧠 How I Think About Code

> “반복되는 것을 매번 다시 만들지 않기 위해,  
> 바뀌는 부분만 안전하게 다룰 수 있는 구조를 고민합니다.”

- 구조는 오래 유지되고, 정책만 교체될 수 있어야 한다고 생각합니다.
- 사이드 이펙트가 넓게 퍼지는 변경을 가장 위험하다고 봅니다.
- 기술 선택보다, **이 구조가 얼마나 오래 버틸 수 있는지**를 더 중요하게 봅니다.

<p align="center">
  <em>계속 성장하는 개발자를 목표로 합니다.</em>
</p>

[![Solved.ac 프로필](http://mazassumnida.wtf/api/generate_badge?boj=abcdkh1209)](https://solved.ac/abcdkh1209)