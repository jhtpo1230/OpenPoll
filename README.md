<p align="center">
  <img width="591" height="330" alt="image" src="https://github.com/user-attachments/assets/e7d99443-f31e-4c46-a0af-b41edc25d719" />
</p>

<h1 align="center">OpenPoll</h1>

<p align="center">
  <b>정치 참여를 쉽고 재미있게</b><br/>
  실시간 투표 · 정치 성향 테스트 · 밸런스 게임 · AI 뉴스 요약
</p>

<p align="center">
  <a href="https://openpoll.co.kr"><s>openpoll.co.kr</s></a>
  &nbsp;·&nbsp;
  <i>운영 종료</i>
</p>

<p align="center">
  <sub>
    데브코스 풀스택 8기 팀 프로젝트(6명)<br/>
    원본 팀 저장소:
    <a href="https://github.com/P2P-J/OpenPoll">P2P-J/OpenPoll</a><br/><br/>
    본 저장소는 <b>본인의 백엔드 기여를 중심으로 재정리한 포트폴리오용 저장소</b>입니다.
  </sub>
</p>

---

## 미리보기

> 라이브 서비스는 종료되었지만, 아래는 **실제 운영 화면**입니다. 라이트/다크 모드를 모두 지원합니다.

| 화면 | 라이트 모드 | 다크 모드 |
| --- | --- | --- |
| **OAuth 로그인** | <img src="https://github.com/user-attachments/assets/53acf911-dfed-47df-a41b-e256b92a77ef" width="320" height="200" alt="OAuth 로그인 라이트 모드" /> | <img src="https://github.com/user-attachments/assets/53acf911-dfed-47df-a41b-e256b92a77ef" width="320" height="200" alt="OAuth 로그인 다크 모드" /> |
| **AI 중립 뉴스 목록** | <img src="https://github.com/user-attachments/assets/847d37f6-1149-4255-9bcc-a81d185a75b5" width="320" height="200" alt="AI 중립 뉴스 목록 라이트 모드" /> | <img src="https://github.com/user-attachments/assets/dcab0803-af94-435a-9d59-216330cc4489" width="320" height="200" alt="AI 중립 뉴스 목록 다크 모드" /> |
| **AI 중립 뉴스 상세** | <img src="https://github.com/user-attachments/assets/dd6ba613-989b-48a8-9951-ec9d0c6e361b" width="320" height="200" alt="AI 중립 뉴스 상세 라이트 모드" /> | <img src="https://github.com/user-attachments/assets/41386798-0f3d-48ce-a54a-3d8fddac1666" width="320" height="200" alt="AI 중립 뉴스 상세 다크 모드" /> |

---

## 프로젝트 종료 안내

> **OpenPoll 서비스는 2026년 5월을 끝으로 운영을 종료했습니다.**
>
> 본 저장소는 학습 및 포트폴리오 목적으로 보존합니다.

| 항목      | 내용                                |
| ------- | --------------------------------- |
| 프로젝트 유형 | 데브코스 풀스택 8기 팀 프로젝트                |
| 팀 인원    | 6명                                |
| 개발 기간   | 2026.01 ~ 2026.04                 |
| 운영 기간   | ~ 2026.05                         |
| 현재 상태   | 서비스 운영 종료 / 코드 보존                 |
| 원본 저장소  | https://github.com/P2P-J/OpenPoll |

---

# 프로젝트 소개

OpenPoll은 정치에 익숙하지 않은 사용자도 쉽게 참여할 수 있도록
**실시간 정당 투표, 정치 성향 테스트, 밸런스 게임, AI 뉴스 요약** 등을 제공한 정치 참여형 웹 서비스입니다.

저는 **백엔드 개발자**로 참여해 다음 영역을 담당했습니다.

### 담당 영역

* 네이버 정치 뉴스 크롤링 및 AI 요약 파이프라인 구현
* BullMQ 기반 기사 단위 비동기 작업 처리
* Redis Lock / Cooldown을 이용한 중복 갱신 제어
* JWT Access / Refresh Token 기반 인증
* 이메일 인증 기반 회원가입
* Google / Naver OAuth Provider 구현
* OAuth 가입·로그인·탈퇴·재가입 흐름 구현
* AWS 환경 및 GitHub Actions CI/CD 구축 보조
* 서비스 운영 시작을 위한 AWS 계정 이전 작업

특히 외부 뉴스 사이트와 AI API처럼 **응답 지연이나 실패 가능성이 높은 작업을 안정적으로 처리하는 방법**과,
일반 로그인부터 OAuth 탈퇴·재가입까지 이어지는 **인증 생명주기 전체를 설계하는 경험**을 얻었습니다.

---

# 주요 기능

## 실시간 정당 지지율

사용자가 정당에 투표하고 전체 결과를 실시간으로 확인할 수 있습니다.

연령과 지역에 따른 통계를 제공하며 SSE를 이용해 결과를 갱신합니다.

---

## DOS 정치 성향 테스트

정치·사회 관련 질문을 기반으로 사용자의 성향을 여러 축으로 분석합니다.

결과 유형과 전체 응답자 통계를 비교하고 결과를 공유할 수 있도록 구성했습니다.

---

## 밸런스 게임

정치·사회적 주제에 대해 두 선택지 중 하나에 투표하고 다른 사용자와 의견을 나눌 수 있습니다.

* 투표
* 댓글
* 대댓글
* 좋아요

기능을 제공합니다.

---

## AI 뉴스

네이버 정치 섹션의 주요 기사를 자동으로 수집한 뒤
기사 본문을 AI로 요약해 서비스에 제공합니다.

---

# Backend Contribution

## 1. AI 뉴스 크롤링 · 요약 파이프라인

네이버 정치 섹션의 주요 기사를 수집하고, AI로 요약한 뒤 DB에 저장하는 파이프라인을 구현했습니다.

```text
Naver Politics
      ↓
Headline URL 수집
      ↓
BullMQ Article Job
      ↓
Worker (concurrency: 3)
      ↓
본문 파싱 · AI 요약
      ↓
Prisma Upsert
      ↓
PostgreSQL
```

### 기사 단위 비동기 처리

전체 뉴스 갱신을 하나의 작업으로 처리하지 않고 **기사 하나를 하나의 BullMQ Job으로 분리**했습니다.

특정 기사에서 네트워크·파싱·AI 요약 오류가 발생해도 다른 기사 처리는 유지되도록 `Promise.allSettled()`로 결과를 개별 처리했습니다.

Worker는 `concurrency: 3`으로 제한해 뉴스 사이트와 AI API에 과도한 동시 요청이 발생하지 않도록 했습니다.

### 중복 데이터 · 중복 실행 방지

반복 수집되는 동일 기사는 `naverUrl` 기준 Prisma `upsert`로 중복 저장을 방지했습니다.

뉴스 갱신 자체가 동시에 실행되는 문제는 Redis의 `cooldown`과 `lock`으로 제어했습니다.

```text
Refresh
   ↓
Redis Guard
   ↓
Crawler
   ↓
BullMQ
```

Cooldown 확인과 Lock 획득은 **Redis Lua Script로 원자적으로 처리**했으며, 작업 종료 시 Lock 소유권을 확인한 뒤 해제하도록 구성했습니다.

수동 갱신과 주기적 자동 갱신 모두 동일한 `refreshArticles()`를 사용해 같은 중복 실행 정책을 적용했습니다.

---

## 2. 인증 · OAuth

이메일 기반 일반 인증과 **Google / Naver OAuth 로그인**을 구현했습니다.

```text
              Auth Service
                   │
        ┌──────────┴──────────┐
        ↓                     ↓
 Email / Password        Google / Naver
        ↓                     ↓
    JWT 인증             OAuth Provider
        │                     ↓
        │                State 검증
        │                     ↓
        └──────────→ 사용자 조회 / 가입
                              ↓
                    Access / Refresh Token
                              ↓
                            Redis
```

### JWT Access / Refresh Token

로그인 시 Access Token과 Refresh Token을 발급하고 Refresh Token은 Redis에 저장했습니다.

Access Token 갱신 시 다음 순서로 Refresh Token을 검증합니다.

```text
JWT 검증
   ↓
Redis Token 조회
   ↓
요청 Token 비교
   ↓
User 확인
   ↓
새 Token 발급
```

로그아웃 또는 비밀번호 변경 시 Redis의 Refresh Token을 삭제해 기존 인증 상태를 무효화했습니다.

### Google / Naver Provider 분리

Google과 Naver의 OAuth API 차이가 Auth Service에 직접 노출되지 않도록 Provider별 구현을 분리했습니다.

```text
          Auth Service
               ↓
         getProvider()
       ┌───────┴───────┐
       ↓               ↓
    Google           Naver
       ↓               ↓
    공통 Profile 형태 반환
```

각 Provider는 사용자 정보를 다음과 같은 공통 구조로 반환합니다.

```js
{
  provider,
  providerUserId,
  email,
  name,
  oauthRefreshToken
}
```

이를 통해 Auth Service에서는 Provider별 응답 구조와 관계없이 동일한 가입·로그인 로직을 사용할 수 있도록 했습니다.

### OAuth State · 가입 분기

OAuth 요청 시 UUID 기반 `state`를 생성하고 Provider 정보와 요청 모드를 함께 저장했습니다.

Callback에서는 `state`와 요청 Provider를 검증한 뒤, `provider + providerUserId`를 기준으로 기존 OAuth 계정을 조회합니다.

```text
OAuth Callback
      ↓
State 검증
      ↓
OAuthAccount 조회
   ↙             ↘
기존 계정        신규 계정
   ↓               ↓
 로그인      User + OAuthAccount 생성
```

신규 가입 시 `User`, `OAuthAccount`, `PointHistory` 생성을 Prisma Transaction으로 묶어 처리했습니다.

### OAuth 탈퇴 · 재가입

OAuth 회원 탈퇴 시 Provider별 `revokeToken()`을 호출해 Google / Naver 연동 해제를 시도합니다.

이후 `provider + providerUserId`를 탈퇴 이력으로 저장하고 사용자를 삭제합니다.

같은 OAuth 계정으로 다시 접근하면 탈퇴 이력을 확인하고, 사용자가 명시적으로 재가입을 선택한 경우에만 `rejoin` 상태를 통해 다시 가입할 수 있도록 구현했습니다.

```text
가입
 ↓
로그인
 ↓
탈퇴
 ↓
재가입
```

이를 통해 단순 OAuth 로그인뿐 아니라 **가입부터 탈퇴·재가입까지의 사용자 생명주기**를 처리했습니다.

---

## 3. AWS · CI/CD

실제 서비스 배포 과정에서 **AWS 환경 설정 및 GitHub Actions 기반 CI/CD 구축을 보조**했습니다.

또한 서비스 운영 시작을 위해 기존 개발 환경의 AWS 리소스를 운영 계정으로 이전하고, 이전된 환경에서 서비스가 정상적으로 배포·동작하도록 관련 설정을 점검했습니다.

### 담당 영역

- AWS 배포 환경 설정 보조
- GitHub Actions CI/CD 파이프라인 구축 보조
- EC2 배포 환경 점검
- 서비스 운영을 위한 AWS 계정 이전
- 이전 환경에 맞춘 배포 설정 및 서비스 구동 확인

---

# 주요 문제와 해결

## 문제 1. 한 기사 실패가 전체 뉴스 갱신에 영향을 줄 수 있다

### 문제

뉴스 갱신은 여러 기사를 한꺼번에 처리하기 때문에
하나의 Promise 흐름으로 연결하면 기사 하나의 실패가 전체 작업에 영향을 줄 수 있습니다.

### 해결

기사별로 BullMQ Job을 분리하고 `Promise.allSettled()`를 사용했습니다.

```text
10개 기사

↓ 기사별 Job

8 SUCCESS
1 PARSING FAIL
1 AI FAIL
```

실패한 기사만 로그로 남기고 성공한 기사 결과는 정상적으로 유지했습니다.

### 배운 점

대량 작업에서는 단순한 병렬 처리보다
**실패의 범위를 어디까지 격리할지 정하는 것이 중요하다**는 것을 배웠습니다.

---

## 문제 2. 갱신 요청이 겹치면 동일한 외부 작업이 반복된다

### 문제

뉴스 갱신이 동시에 여러 번 실행되면

* 네이버 기사 중복 요청
* AI API 중복 호출
* 불필요한 Queue Job 생성

이 발생할 수 있었습니다.

### 해결

Redis Lua Script를 이용해

```text
Cooldown Check
+
Distributed Lock
```

을 원자적으로 처리했습니다.

Lock 획득 시 `SET NX PX`를 사용하고
해제 시에는 Lock 소유 값을 확인했습니다.

### 배운 점

중복 요청을 막는 것과
**동일한 작업이 동시에 실행되는 것을 막는 것은 서로 다른 문제**라는 것을 경험했습니다.

---

## 문제 3. OAuth Provider마다 구현 방식이 다르다

### 문제

Google과 Naver는 OAuth라는 공통 규격을 사용하지만
Token API와 Profile 응답, 연동 해제 방법이 서로 달랐습니다.

이를 Auth Service에서 직접 분기하면

```text
if google ...
else if naver ...
```

가 인증 전반에 계속 퍼질 수 있었습니다.

### 해결

Provider별 외부 API 처리를 별도 객체로 분리하고

```text
getAuthUrl()
getProfileFromCode()
revokeToken()
```

이라는 공통 인터페이스 형태로 사용했습니다.

Auth Service에서는 Provider가 반환하는 정규화된 Profile만 사용합니다.

### 배운 점

외부 서비스 연동에서는
**서비스별 차이를 비즈니스 로직 밖으로 격리하는 것이 변경과 확장에 유리하다**는 점을 배웠습니다.

---

## 문제 4. OAuth 탈퇴 후 동일 계정 재가입 처리

### 문제

OAuth 회원을 DB에서 단순 삭제하면
같은 Provider 계정으로 다시 인증했을 때 신규 가입인지 탈퇴 회원의 재가입인지 구분하기 어렵습니다.

### 해결

탈퇴 시

```text
provider + providerUserId
```

를 별도의 탈퇴 이력으로 저장했습니다.

OAuth Callback에서는 이 이력을 확인하고
일반 로그인 요청이면 재가입이 필요하다는 상태를 반환합니다.

사용자가 명시적으로 재가입을 선택한 경우에만

```text
mode = rejoin
```

을 OAuth state에 함께 저장해 Callback까지 전달하고
탈퇴 이력을 제거한 뒤 다시 가입할 수 있도록 구성했습니다.

### 배운 점

인증은 로그인 성공 여부만 다루는 기능이 아니라

```text
가입
→ 로그인
→ Token 갱신
→ 로그아웃
→ 탈퇴
→ 재가입
```

전체 사용자 생명주기를 함께 고려해야 한다는 것을 경험했습니다.

---

# AWS / CI/CD

OpenPoll은 AWS 환경에 실제 배포하여 운영했습니다.

저는 팀원과 함께

* AWS 서비스 설정 및 배포 환경 구성 지원
* GitHub Actions CI/CD 구축 및 수정 지원
* EC2 배포 과정 점검
* 서비스 운영을 위한 AWS 계정 이전
* 이전 후 서비스가 정상적으로 구동될 수 있도록 관련 설정 점검

작업에 참여했습니다.

<img width="671" height="520" alt="image" src="https://github.com/user-attachments/assets/471419f5-9bf7-497d-8c51-5ada84a1efb4" />


```text
[사용자]
    ↓
 Route 53
    ↓
   ALB
    ↓
┌───────────────────┐
│ Frontend EC2      │
│ nginx + React     │
└───────────────────┘
          │
          ↓
┌───────────────────┐
│ Backend EC2       │
│ Node + Express    │
│ PM2               │
└───────────────────┘
      │          │
      ↓          ↓
 PostgreSQL     Redis
     RDS
```

> AWS 인프라 전체를 단독으로 설계·구축한 것은 아니며,
> 본인은 **AWS 설정 및 CI/CD 파이프라인 구축 지원과 서비스 운영을 위한 AWS 계정 이전 작업**에 참여했습니다.

---

# 기술 스택

## Backend

| 기술           | 용도                                 |
| ------------ | ---------------------------------- |
| Node.js      | Backend Runtime                    |
| Express      | REST API                           |
| Prisma       | ORM / Transaction                  |
| PostgreSQL   | Main Database                      |
| Redis        | Refresh Token / News Guard / Queue |
| BullMQ       | 뉴스 기사 단위 비동기 처리                    |
| JWT          | Access / Refresh Token             |
| bcrypt       | 비밀번호 해싱                            |
| Axios        | 외부 HTTP 요청                         |
| Cheerio      | 뉴스 HTML 파싱                         |
| OpenAI API   | 뉴스 AI 요약                           |
| Nodemailer   | 이메일 인증                             |
| Google OAuth | 소셜 인증                              |
| Naver OAuth  | 소셜 인증                              |

## Infra / DevOps

| 기술                      | 용도                   |
| ----------------------- | -------------------- |
| AWS EC2                 | Application Server   |
| AWS RDS                 | PostgreSQL           |
| AWS ElastiCache / Redis | Redis                |
| AWS ALB                 | Load Balancing / TLS |
| AWS Route 53            | DNS                  |
| AWS SSM                 | 서버 접근 및 배포           |
| AWS IAM                 | 권한 관리                |
| GitHub Actions          | CI/CD                |
| PM2                     | Node Process Manager |
| nginx                   | Frontend Serving     |

---

# Backend Structure

```text
backend/
├── prisma/
│   └── schema.prisma
│
└── src/
    ├── config/
    │
    ├── middlewares/
    │
    ├── modules/
    │   │
    │   ├── auth/
    │   │   ├── auth.service.js
    │   │   │
    │   │   └── oauth/
    │   │       ├── google.js
    │   │       ├── naver.js
    │   │       ├── oauth.state.js
    │   │       └── index.js
    │   │
    │   └── news/
    │       ├── news.service.js
    │       │
    │       ├── ai/
    │       │   └── aiSummarize.js
    │       │
    │       └── jobs/
    │           ├── crawler.js
    │           ├── queueWorker.js
    │           ├── redisGuard.js
    │           └── refreshJob.js
    │
    ├── app.js
    └── server.js
```

---

# 핵심 결과

### News

* 네이버 정치 Headline 자동 수집
* 기사 단위 BullMQ Job 분리
* Worker `concurrency: 3` 기반 외부 요청 제어
* 기사별 파싱 / AI 요약 실패 격리
* `Promise.allSettled()` 기반 Job 결과 개별 처리
* URL 기반 Prisma Upsert로 기사 중복 저장 방지
* Redis Lua Script 기반 Refresh Lock / Cooldown
* 주기적인 뉴스 자동 갱신

### Auth

* Redis 기반 이메일 인증
* bcrypt 기반 비밀번호 저장
* JWT Access / Refresh Token 인증
* Redis 기반 Refresh Token 관리
* 로그아웃 및 비밀번호 변경 시 Refresh Token 무효화
* Google / Naver OAuth Provider 구현
* OAuth state 검증
* 기존 OAuth 회원 로그인 / 신규 회원가입 분기
* OAuth 회원 탈퇴 시 Provider 연동 해제
* 탈퇴 OAuth 계정 이력 관리
* `rejoin` 상태를 이용한 재가입 흐름 구현
* 사용자·OAuthAccount·PointHistory 생성 Transaction 처리

### Infra

* AWS 환경 구성 및 배포 작업 참여
* GitHub Actions CI/CD 구축 지원
* 서비스 운영 시작을 위한 AWS 계정 이전

---

# 회고

OpenPoll은 단순히 API를 구현하는 것을 넘어
**외부 시스템과 연결된 백엔드를 실제 서비스 환경에서 어떻게 안정적으로 동작시키는지** 고민한 프로젝트였습니다.

가장 많은 고민을 했던 부분은 뉴스 처리였습니다.

뉴스 기능에는 크롤링, 기사 페이지 요청, HTML 파싱, AI API 호출처럼
언제든 느려지거나 실패할 수 있는 외부 작업이 연속해서 존재했습니다.

처음부터 이를 하나의 큰 작업으로 바라보기보다
기사 하나를 하나의 BullMQ Job으로 분리했습니다.

그 결과 특정 기사에서 파싱이나 AI 요약이 실패하더라도
다른 기사의 처리는 계속할 수 있었습니다.

또한 Worker의 동시 실행 수를 제한하고
Redis Lock과 Cooldown으로 전체 뉴스 갱신의 중복 실행을 막으면서,

**비동기 작업에서는 Queue 사용 자체보다 작업 단위, 실패 범위, 중복 실행을 어떻게 정의하는지가 중요하다**는 것을 배웠습니다.

인증 기능에서는 Google과 Naver OAuth를 구현하면서
OAuth 로그인을 단순한 외부 로그인 API 연결로만 생각해서는 안 된다는 점을 배웠습니다.

Provider마다 다른 외부 API를 별도 모듈로 분리하고
그 위에서

```text
OAuth 요청
→ state 검증
→ 기존 사용자 확인
→ 신규 가입
→ Profile 보완
→ Token 발급
→ 탈퇴
→ Provider 연동 해제
→ 재가입
```

까지 전체 사용자 생명주기를 처리했습니다.

특히 탈퇴한 OAuth 계정의 재가입을 처리하면서
현재 User 테이블에 데이터가 존재하는지만 보는 것이 아니라
**과거 상태까지 고려해야 올바른 인증 정책을 구현할 수 있다는 점**을 경험했습니다.

마지막으로 실제 AWS 환경의 설정과 CI/CD 작업, 운영을 위한 AWS 계정 이전 과정에 참여하면서
백엔드는 코드만 정상적으로 동작한다고 끝나는 것이 아니라

```text
Application
→ Database
→ Redis
→ External API
→ IAM
→ Deployment
→ Infrastructure
```

전체가 연결되어야 실제 서비스가 된다는 점을 배웠습니다.

이 프로젝트 이후에는 기능 구현에서 끝내지 않고
**실패, 중복, 상태 변화와 실제 운영 환경까지 고려하는 백엔드 개발**을 지향하고 있습니다.

---

# 시작하기

## Requirements

* Node.js 20+
* PostgreSQL
* Redis

## Backend

```bash
cd backend

npm install

npx prisma migrate dev

npx prisma db seed

npm run dev
```

## Frontend

```bash
cd frontend/openpoll

npm install

npm run dev
```

---

# License

MIT License

---

<p align="center">
  <sub>OpenPoll — 2026.01 ~ 2026.05</sub>
</p>
