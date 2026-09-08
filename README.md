<p align="center">
  <img width="1191" height="630" alt="image" src="https://github.com/user-attachments/assets/e7d99443-f31e-4c46-a0af-b41edc25d719" />
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

| 화면                                 | 라이트 모드                                                     | 다크 모드                                                      |
| ------------------------------------ | --------------------------------------------------------------- | -------------------------------------------------------------- |
| **Oauth 로그인**                     |     <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/53acf911-dfed-47df-a41b-e256b92a77ef" />
   |   <img width="2880" height="1800" alt="image" src="https://github.com/user-attachments/assets/72e6d706-211d-4bfc-b809-c6567ef590f6" />
   |
| **AI 중립 뉴스 목록**                     |    <img width="2880" height="6920" alt="image" src="https://github.com/user-attachments/assets/8bb2dfac-fc8c-4d54-b40b-d00a5aed95b0" />
    |   <img width="2880" height="6920" alt="image" src="https://github.com/user-attachments/assets/f72ab54b-3bbd-4309-8442-403683f9f498" />
   |
| **AI 중립 뉴스 상세**                     |    <img width="2880" height="4906" alt="image" src="https://github.com/user-attachments/assets/c7724ce8-4811-4b7e-bbef-3a7f283fac58" />
    |   <img width="2880" height="4906" alt="image" src="https://github.com/user-attachments/assets/f3c61de3-b16a-4f15-b67d-1bf3aff52531" />
   |

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

# 1. 뉴스 크롤링 + AI 요약 파이프라인

뉴스 기능은 단순 크롤링 API가 아니라

```text
URL 수집
→ 기사 본문 요청
→ HTML 파싱
→ AI API 호출
→ 결과 가공
→ DB 저장
```

처럼 여러 외부 I/O 작업이 연속해서 발생합니다.

이를 안정적으로 처리하기 위해 뉴스 처리 과정을 여러 단계로 분리했습니다.

---

## 1-1. 정치 뉴스 Headline URL 수집

네이버 뉴스 정치 섹션에서 Headline 기사 URL을 수집합니다.

```text
Naver Politics
      ↓
Cheerio Parsing
      ↓
Headline
      ↓
URL + 언론사
```

수집 과정에서 `Set`을 이용해 동일 URL을 한 번 더 걸러냅니다.

```js
const urls = new Set();

if (urls.has(naverUrl)) return;

urls.add(naverUrl);
items.push({ naverUrl, press });
```

전체 기사 페이지를 한 번에 처리하지 않고
먼저 **처리 대상 URL만 수집한 뒤 각 기사를 독립된 작업으로 넘기는 구조**로 설계했습니다.

---

## 1-2. 기사 단위 BullMQ Job 분리

처음부터 전체 뉴스를 하나의 큰 작업으로 처리하지 않고
**기사 하나를 하나의 BullMQ Job으로 분리했습니다.**

```text
Article A → Job A ─┐
Article B → Job B ─┼→ BullMQ → Worker
Article C → Job C ─┘
```

기사 URL을 기반으로 `jobId`를 생성합니다.

```js
const jobId = Buffer
  .from(item.naverUrl)
  .toString('base64url');
```

각 기사는 별도의 Job이므로 특정 기사에서

* HTML 파싱 실패
* 네트워크 오류
* AI 요약 실패

가 발생하더라도 다른 기사 작업까지 함께 실패하지 않습니다.

---

## 1-3. Worker 동시 실행 개수 제한

기사 처리 Worker는 `concurrency: 3`으로 구성했습니다.

```js
new Worker(
  'article',
  async (job) => {
    // 본문 크롤링
    // AI 요약
    // DB 저장
  },
  {
    concurrency: 3,
  }
);
```

뉴스 본문 크롤링과 AI API 호출은 모두 외부 요청이기 때문에
Job을 무제한 병렬 처리하면 외부 서비스와 서버에 동시에 부하가 발생할 수 있습니다.

따라서 Worker가 한 번에 처리할 수 있는 작업 수를 제한했습니다.

---

## 1-4. 기사 본문 검증 및 실패 분리

Worker에서 실제 뉴스 페이지를 요청한 뒤

* 제목
* 본문
* 원문 URL

을 추출합니다.

```text
Article URL
     ↓
Axios
     ↓
Cheerio
     ↓
Title / Body / Original URL
```

제목이 없거나 본문이 비정상적으로 짧으면 정상 기사로 처리하지 않습니다.

```js
if (!title) {
  throw new Error('INVALID_TITLE');
}

if (!body || body.length < 100) {
  throw new Error('INVALID_BODY');
}
```

AI 요약 과정에서 오류가 발생한 경우도 별도의 실패 유형으로 구분했습니다.

```js
AI_SUMMARY_FAILED
```

갱신 작업에서는 `Promise.allSettled()`를 사용해 각 Job의 결과를 개별적으로 확인합니다.

```text
Job A → SUCCESS
Job B → PARSING FAIL
Job C → SUCCESS
Job D → AI SUMMARY FAIL
```

따라서 Job B와 D가 실패하더라도 A와 C의 처리는 유지됩니다.

---

## 1-5. URL 기준 Upsert로 중복 기사 방지

뉴스 크롤러는 일정 주기로 반복 실행되기 때문에
같은 기사가 다시 수집되는 상황이 자연스럽게 발생합니다.

이를 위해 `naverUrl`을 기사 식별 기준으로 사용했습니다.

```text
기사 수집
   ↓
naverUrl
   ↓
DB에 존재?
 ↙        ↘
YES       NO
 ↓         ↓
UPDATE    INSERT
```

Prisma의 `upsert`를 이용해 동일 URL의 기사가 다시 처리되더라도
중복 Row가 생성되지 않도록 구성했습니다.

---

# 2. Redis 기반 뉴스 갱신 중복 실행 제어

기사 단위 중복뿐 아니라
**뉴스 갱신 작업 자체가 동시에 여러 번 실행되는 문제**도 고려했습니다.

예를 들어 두 요청이 거의 동시에 들어오면

```text
Request A ─→ News Refresh
Request B ─→ News Refresh
```

동일한 뉴스가 두 번 크롤링되고 AI API도 중복 호출될 수 있습니다.

이를 방지하기 위해 Redis에

* `cooldown`
* `lock`

두 가지 상태를 관리했습니다.

---

## 2-1. Redis Lua Script를 이용한 원자적 Guard

단순하게

```text
GET lock
→ 확인
→ SET lock
```

순서로 처리할 경우 두 요청이 동시에 확인하는 순간 Race Condition이 발생할 수 있습니다.

따라서 Redis Lua Script 안에서

```text
Cooldown 확인
      ↓
Lock 획득
      ↓
Cooldown 생성
```

을 하나의 연산으로 처리했습니다.

```text
Refresh Request
      ↓
Cooldown 존재?
 ┌────┴────┐
YES        NO
 ↓          ↓
SKIP     SET NX Lock
             ↓
         Cooldown 생성
             ↓
          Refresh
```

Lock은 `SET NX PX`를 이용하여 하나의 실행만 진입할 수 있도록 했습니다.

---

## 2-2. Lock 소유권 확인 후 해제

작업 완료 후 Lock을 단순히 삭제하지 않고
자신이 생성한 Lock인지 확인한 뒤 삭제합니다.

각 Lock에는

```text
process.pid + timestamp
```

기반의 값을 저장했습니다.

```text
현재 Redis Lock 값
        ↓
내 Lock 값과 동일?
     ↙       ↘
   YES       NO
    ↓         ↓
  DELETE     유지
```

이를 통해 다른 실행이 새롭게 획득한 Lock을 이전 작업이 실수로 삭제하지 않도록 했습니다.

---

# 3. 주기적인 뉴스 자동 갱신

뉴스 데이터는 별도의 요청이 없더라도 주기적으로 갱신될 수 있도록 구성했습니다.

기본적으로 일정 간격마다 `refreshArticles()`를 호출합니다.

```text
Timer
  ↓
refreshArticles()
  ↓
Redis Guard
  ↓
Crawler
  ↓
BullMQ
```

수동 뉴스 갱신과 자동 갱신 모두 같은 `refreshArticles()` 로직을 사용하기 때문에
어떤 경로로 호출되더라도 동일한 Lock / Cooldown 정책을 거칩니다.

---

# 4. 일반 회원 인증

OpenPoll의 인증은

```text
일반 이메일 회원
+
Google OAuth
+
Naver OAuth
```

를 함께 지원하도록 구현했습니다.

일반 회원은

* 이메일 인증
* 회원가입
* 로그인
* Access Token 갱신
* 로그아웃
* 비밀번호 변경

흐름을 제공합니다.

---


# 5. JWT Access / Refresh Token 인증

로그인 이후

```text
Access Token
+
Refresh Token
```

을 발급합니다.

Access Token은 실제 API 인증에 사용하고,
Refresh Token은 새로운 Access Token을 발급할 때 사용합니다.

Refresh Token은 Redis에 저장합니다.

```text
User Login
    ↓
Access Token
Refresh Token
    ↓
Redis
userId → refreshToken
```

Refresh 요청이 들어오면

```text
JWT Signature 검증
        ↓
Redis Refresh Token 조회
        ↓
요청 Token과 비교
        ↓
User 존재 확인
        ↓
새 Token 발급
```

순서로 검증합니다.

로그아웃 시 Redis에 저장된 Refresh Token을 삭제하며,
비밀번호가 변경된 경우에도 기존 Refresh Token을 제거해 다시 로그인을 요구하도록 했습니다.

---

# 6. Google / Naver OAuth Provider 분리

Google과 Naver는 모두 OAuth 기반 로그인이지만

* Authorization URL
* Token API
* 사용자 정보 API
* 응답 구조
* 연동 해제 방식

이 서로 다릅니다.

Provider별 차이가 인증 서비스 전체에 퍼지지 않도록
Google과 Naver 구현을 각각 Provider로 분리했습니다.

```text
            Auth Service

                 ↓

           getProvider()

        ┌────────┴────────┐
        ↓                 ↓

 GoogleProvider       NaverProvider

 getAuthUrl()         getAuthUrl()

 getProfileFromCode() getProfileFromCode()

 revokeToken()        revokeToken()
```

각 Provider가 외부 API 차이를 처리한 뒤 Auth Service에는 공통 형식으로 반환합니다.

```js
{
  provider,
  providerUserId,
  email,
  name,
  oauthRefreshToken
}
```

따라서 인증 서비스는 Google/Naver의 응답 구조를 직접 알 필요 없이
공통된 Profile 형태만 처리합니다.

---

# 7. OAuth State 관리

OAuth 로그인 시작 시 UUID 기반 `state`를 생성합니다.

```text
OAuth 로그인 요청
       ↓
UUID state 생성
       ↓
state 저장
       ↓
Google / Naver Authorization URL
```

저장하는 정보는

```text
providerName
mode
```

입니다.

Callback에서는 전달받은 state를 소비하고
요청을 시작한 Provider와 Callback Provider가 동일한지 검증합니다.

```text
Callback
   ↓
state consume
   ↓
state 존재?
   ↓
provider 일치?
   ↓
OAuth 처리
```

유효하지 않거나 Provider가 일치하지 않는 state는 인증을 거부합니다.

이 `state`는 OAuth 요청 검증뿐 아니라
탈퇴 회원의 **재가입 모드(`rejoin`)를 Callback까지 전달하는 역할**도 수행합니다.

---

# 8. OAuth 기존 회원 / 신규 회원 분기

Provider에서 사용자 정보를 받아오면

```text
provider
+
providerUserId
```

조합을 기준으로 기존 OAuth 계정을 조회합니다.

```text
OAuth Callback
      ↓
Provider Profile
      ↓
OAuthAccount 조회
   ↙             ↘
존재              없음
 ↓                 ↓
로그인          신규 회원 생성
```

기존 OAuth 계정이면 연결된 User를 그대로 사용합니다.

Provider에서 새로운 Refresh Token이 내려온 경우
저장되어 있는 OAuth Refresh Token도 갱신합니다.

---

## 신규 OAuth 회원

기존 OAuthAccount가 없다면 신규 가입을 진행합니다.

먼저 Provider에서 이메일을 가져올 수 있는지 확인하고
이미 일반 회원으로 사용 중인 이메일인지 검사합니다.

신규 회원 생성 과정은

```text
User
+
OAuthAccount
+
회원가입 PointHistory
```

를 하나의 Prisma Transaction으로 묶었습니다.

```text
BEGIN

User 생성

OAuthAccount 생성

PointHistory 생성

COMMIT
```

OAuth로 처음 가입한 사용자는 닉네임·나이·지역·성별 등이 없을 수 있기 때문에

```text
profileComplete
```

값을 함께 반환합니다.

프로필이 미완성이라면 이후 별도 API에서 추가 정보를 입력하도록 구성했습니다.

---

# 9. OAuth 탈퇴 및 재가입 처리

OAuth 계정의 경우 단순히 OpenPoll의 User만 삭제하면
Provider에는 기존 OAuth 연결 정보가 남을 수 있습니다.

따라서 탈퇴 과정에서 Provider별 `revokeToken()`을 호출합니다.

### Google

Google revoke API를 이용해 Token을 폐기합니다.

### Naver

Naver의 경우 Refresh Token으로 Access Token을 다시 발급한 뒤
`grant_type=delete` 요청을 보내 연동을 해제합니다.

Provider별 차이는 각각의 Provider 내부에서 처리합니다.

---

## 탈퇴 이력 관리

OAuth 회원이 탈퇴하면

```text
provider
+
providerUserId
```

정보를 `withdrawnOauth`에 기록한 뒤 User를 삭제합니다.

```text
OAuth 탈퇴
   ↓
Provider 연동 해제
   ↓
withdrawnOauth 저장
   ↓
User 삭제
```

같은 OAuth 계정으로 다시 접근하면
탈퇴 이력이 존재하는지 확인합니다.

```text
OAuth Callback
      ↓
withdrawnOauth 존재?
     ↙           ↘
   YES            NO
    ↓              ↓
rejoin 확인      일반 로그인/가입
```

일반 OAuth 요청이라면 `REJOIN_REQUIRED`를 반환하고,
사용자가 재가입을 선택해 `rejoin` 모드로 인증을 시작한 경우에만 탈퇴 이력을 삭제하고 다시 가입 절차를 진행합니다.

즉 OAuth 회원의

```text
가입
→ 로그인
→ 탈퇴
→ 재가입
```

전체 생명주기를 하나의 인증 흐름 안에서 관리하도록 구현했습니다.

---

# Authentication Flow

```text
                     [일반 회원]

사용자
  ↓
이메일 인증
  ↓
회원가입
  ↓
bcrypt Password Hash
  ↓
User + PointHistory Transaction
  ↓
Access / Refresh Token
  ↓
Refresh Token → Redis


                     [OAuth]

사용자
  ↓
Google / Naver 로그인
  ↓
state 생성 및 저장
  ↓
OAuth Provider
  ↓
Callback
  ↓
state 검증
  ↓
Provider Profile 정규화
  ↓
탈퇴 이력 확인
  ↓
OAuthAccount 조회
    │
    ├─ 기존 계정 → 로그인
    │
    └─ 신규 계정
           ↓
        User 생성
        OAuthAccount 생성
        PointHistory 생성
           ↓
    Access / Refresh Token
```

---

# News Processing Flow

```text
                    Refresh Trigger
                           │
                           ↓
                 Redis Refresh Guard
                           │
                 ┌─────────┴─────────┐
                 │                   │
             COOLDOWN              LOCKED
                 │                   │
                SKIP                SKIP
                           │
                           ↓
                Naver Politics Crawler
                           │
                           ↓
                  Headline URL List
                           │
                           ↓
                  BullMQ Article Queue
                           │
             ┌─────────────┼─────────────┐
             ↓             ↓             ↓
           Job A          Job B          Job C
             │             │             │
             └─────────────┼─────────────┘
                           ↓
                  Worker concurrency=3
                           │
                           ↓
                    Article Crawling
                           │
                           ↓
                    Content Validate
                           │
                           ↓
                       AI Summary
                           │
                           ↓
                    Prisma Upsert
                           │
                           ↓
                     PostgreSQL
```

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

<!-- AWS 아키텍처 이미지 삽입 -->

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
