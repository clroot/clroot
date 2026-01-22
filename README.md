<h1 align="center">Backend Engineer · Full-stack capable</h1>
<p align="center">
  <em>반복되는 큰 흐름은 고정하고, 바뀌는 정책만 제어하는 구조를 선호합니다</em>
</p>

---

## 👋 About

프레임워크 내부를 파고들어 기술적 빈 틈을 메우는 것과, 비즈니스 복잡도를 구조화하여 오래 유지되는 시스템을 설계하는 것 — 두 방향 모두 좋아합니다.

주로 Kotlin + Spring 기반의 백엔드를 설계하고, 필요에 따라 프론트엔드(Next.js), 인프라, 운영까지 함께 다룹니다.

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

Kotlin Coroutines + JPA 조합으로 개인 서비스를 만들다가, 여러 엔티티에 걸친 트랜잭션을 코루틴 컨텍스트에서 안정적으로 처리할 수 없는 한계에 부딪혔습니다. Reactive 스택으로 전환하고 싶었지만, Spring Data JPA의 메서드 네이밍 쿼리(`findByNameAndStatus` 등)를 포기하기 아쉬워서 — Hibernate Reactive 위에서 그대로 쓸 수 있게 직접 만든 라이브러리입니다.

- PartTree 기반 동적 쿼리 생성 — Spring Data 메서드 네이밍 규칙 호환, 36개 조건 연산자 지원
- 코루틴 트랜잭션 통합 — Spring은 ThreadLocal로, Hibernate Reactive는 Vert.x EventLoop로, 코루틴은 CoroutineContext로 각각 상태를 관리합니다. 코루틴이 스레드를 자유롭게 전환하는 순간 앞의 둘은 깨지는데, 커스텀 CoroutineContext element에 세션과 Vert.x 컨텍스트를 실어 코루틴의 전파 방식 그대로 흘려보내는 방법으로 해결했습니다
- Spring Boot 3.x & 4.0 멀티버전 지원

🔗 [hibernate-reactive-coroutines on GitHub](https://github.com/clroot/hibernate-reactive-coroutines)

---

### 📊 Kotlin Excel DSL
**개인 프로젝트 (오픈소스 라이브러리)**

실무에서 Apache POI로 Excel을 다루다 보면 스타일링, 수식, 조건부 컬럼 처리에서 코드가 급격히 복잡해집니다. 특히 사용자 권한에 따라 노출 컬럼이 달라지는 요구사항이 반복되면서, **컬럼을 선언하기만 하면 나머지는 알아서 처리되는 구조**가 필요했습니다.

```kotlin
// 컬럼을 선언하기만 하면 Excel 시트 완성
sheet.column("이름") { it.user.name }
sheet.column("부서") { it.user.department }
sheet.column("연락처") { it.user.phone ?: "-" }

// 권한에 따라 노출 컬럼을 분기
if (context.isAdmin) {
    sheet.column("급여") { it.salary }
}
```

- 단순한 케이스는 어노테이션(`@Column`)으로, 복잡한 케이스는 DSL(`excel { }`)로 처리
- 동일한 정의로 Excel 생성과 파싱 양방향 지원
- 선언적 스타일링 — `@HeaderStyle`, `@ConditionalStyle`, HEX 색상, 사전 정의 테마

🔗 [kotlin-excel-dsl on GitHub](https://github.com/clroot/kotlin-excel-dsl)

---

### 🧱 Internal SDK (Private)
**B2B 교육/장학 서비스용 사내 공통 SDK**

약 2년간 10개 이상의 고객사 사업을 운영하면서, 매번 비슷한 기능(인증, 상담, 강의, 게시판 등)을 copy-paste로 재구현하는 한계를 느꼈습니다. 반복되는 로직은 SDK로 표준화하고, 고객사별로 달라지는 정책만 외부에서 안전하게 확장할 수 있는 구조를 설계했습니다.

- **13개 도메인 모듈**: 인증, 상담, 강의, 게시판, 파일(S3), 회의(Zoom), 동영상(YouTube), SMS, 알림 등 — 고객사별로 필요한 모듈만 조합하여 서비스 구성
- **도메인 로직과 인프라의 완전 분리**: 비즈니스 규칙이 담긴 도메인 모델은 프레임워크(Spring, JPA) 의존 없이 순수 Kotlin으로 유지하여, DB나 프레임워크가 바뀌어도 핵심 로직은 그대로 재사용 가능
- **SDK 코드 수정 없이 고객사별 정책 확장**: 예를 들어 "대학생만 신청 가능" 같은 고객사별 규칙을 SDK 외부에서 등록하면, 기존 코드를 건드리지 않고 자동 적용
- **이벤트 기반 시스템 간 통신**: 상담 완료 시 알림 발송, 포인트 적립 등 후속 처리를 이벤트로 분리하여 모듈 간 직접 의존 제거

> 비공개 레포지토리

---

## 👨‍💻 Other Experience

- **레거시 시스템 현대화**: PHP/그누보드4 기반 시스템을 Java/Spring + React(Vite) 기반 API 서버/클라이언트 구조로 전환
- **운영 자동화**: 데이터 마이그레이션, 통계 집계, 외부 API 연동 등 반복 업무를 Python 스크립트로 자동화
