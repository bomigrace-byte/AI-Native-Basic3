# 노코드 자동화 도구 비교 및 자동화 구현

## 1. 미션 요약

[반복 업무를 노코드 자동화 도구로 구현하고, 도구별 차이를 비교한다.]

---

## 2. 사용 도구 및 서비스

1. [MAKE]
2. [ZAPIER]

---

# 프로젝트 1. 동일 워크플로우 도구 비교

## 3. 프로젝트 1 주제

[날씨 데이터 자동 수집 및 알림 시스템]

## 4. 워크플로우 구조

1. Trigger: [Schedule]
2. 조건 분기: [체감온도 28도 기준 "기온높음/낮음" 표기 구분]
3. Action 1: [Google Sheets]
4. Action 2: [Discord]

---

## 5. 도구 A 구현

### 5-1. 도구 이름

[MAKE]

### 5-2. 구현 내용

1. Trigger: [Schedule] - HTTP Request
2. 조건 분기: [Router:체감온도 기준 구분 표기]
3. Action 1: [Google Sheets 날씨 데이터 행 추가]
4. Action 2: [Discord 날씨 요약 메시지 전송]

### 5-3. 캡처

1. 워크플로우 구성 화면
 
<img width="1117" height="627" alt="image" src="https://github.com/user-attachments/assets/7f2e8c90-72f6-40f0-a67c-97b146733210" />

2. 실행 결과 화면

<img width="347" height="112" alt="image (1)" src="https://github.com/user-attachments/assets/8360346b-9021-4383-b757-ec03b157a48e" />
   
3. 조건분기 화면

<img width="561" height="723" alt="image (7)" src="https://github.com/user-attachments/assets/5f39596f-07e2-4f91-a09d-add048cb67f6" />
<img width="558" height="712" alt="image (8)" src="https://github.com/user-attachments/assets/c7e4ade2-bb69-4638-9f7a-d06cd1ca3333" />

4. 액션 1 실행 결과

<img width="658" height="215" alt="image (2)" src="https://github.com/user-attachments/assets/98947413-66ac-4e48-bc41-4883dcb506a0" />

5. 액션 2 실행 결과

<img width="298" height="472" alt="image (3)" src="https://github.com/user-attachments/assets/b6d0ae26-f0ac-4755-a4d4-ce9bfb245dc7" />


### 5-4. 느낀 점

1. 장점: [전체 워크플로우를 시각적으로 한눈에 파악 가능, 무료 플랜에서 Webhook 사용 가능]
2. 단점: [모듈 옵션이 많아 초반에 복잡하게 느껴지고 기능명이 생소함]
3. 어려웠던 점: [모듈 생성에 따른 필드 사용법이 복잡해 적용하기 어려웠음]

---

## 6. 도구 B 구현

### 6-1. 도구 이름

[ZAPIER]

### 6-2. 구현 내용

1. Trigger: [Schedule] - Weather by Zapier
2. 조건 분기: [Filter by Zapier:체감온도 기준 구분 표기]
3. Action 1: [Google Sheets 날씨 데이터 행 추가]
4. Action 2: [Discord 날씨 요약 메시지 전송]

### 6-3. 캡처

1. 워크플로우 구성 화면
 
<img width="968" height="123" alt="image (4)" src="https://github.com/user-attachments/assets/94354af9-b9e6-4281-a783-32ecbeb07904" />

<img width="317" height="585" alt="image (5)" src="https://github.com/user-attachments/assets/ced86945-a87e-4b28-83e6-63cafbce6ae6" />

2. 실행 결과 화면

<img width="1132" height="209" alt="image (6)" src="https://github.com/user-attachments/assets/fd69e0c7-69c2-464f-85ee-838e15e14422" />

3. 조건분기 화면

<img width="487" height="240" alt="image (9)" src="https://github.com/user-attachments/assets/78b7ab2b-d5ef-4fb5-9c3a-5c26a25fc047" />

<img width="488" height="241" alt="image (10)" src="https://github.com/user-attachments/assets/e656bd45-22ae-48c3-b708-78e684b16939" />  

4. 액션 1 실행 결과
 
<img width="673" height="197" alt="image (11)" src="https://github.com/user-attachments/assets/a6555b04-e66c-4dd3-b0cd-23957acb8cdb" />

5. 액션 2 실행 결과

<img width="278" height="451" alt="image (12)" src="https://github.com/user-attachments/assets/d26bc3f5-086b-41e7-bce9-fdd103460dac" />


### 6-4. 느낀 점

1. 장점: [내장 기능이 많고 연동 가능한 앱 수가 매우 많음 (6000개 이상)]
2. 단점: [Webhook이 유료 플랜이어서 무료로 API 직접 호출이 불가하고 무료로는 여러 범위의 조건을 한번에 걸기 어려움]
3. 어려웠던 점: [유료인 Path by Zapier를 사용하지 못하기 때문에 유료인 filter by zapier를 사용했는데 조건별 Zaps가 필요해 동일 과정을 두번 구현해야 했음]

---

## 7. Trigger / Action / 조건 분기 설명

1. Trigger: [정해진 시간 🕥7:30]
2. Action1: [Google Sheets 기록]
3. Action2: [Discord 날씨 알림 전송]
4. 조건 분기 사용 이유: [체감온도에 따른 기온 높음/낮음 구분 표기]

---

## 8. 도구 비교

| 비교 항목 | MAKE | ZAPIER |
|---|---|---|
| 1. UI/UX | [캔버스에 맵핑] | [하향식 리스트] |
| 2. 설정 난이도 | [복잡 구조도 한 캔버스 안에서 설계 가능] | [별도의 Zap으로 구성해야하므로 복잡] |
| 3. API 연동 서비스 | [HTTP 모듈] | [Weather by Zapier] |
| 4. 조건 분기 설정 | [Router] | [Filter by Zapier] |
| 5. 실행 로그 확인 | [Run with existing data] | [Zap history] |
| 6. 오류 확인 | [캔버스에서 루트를 통해 시각적으로 & Error message] | [각 Step 마다 Test에서 확인 가능] |
| 7. 무료 플랜 | [월 1,000 Ops] | [월 100 Tasks] |

---

## 9. 프로젝트 1 결론

1. 더 적합하다고 생각한 도구: [Make]
2. 이유: [API 연동이 쉽고 전체 흐름을 시각적으로 관리하기 편함]

---

# 프로젝트 2. 자유 주제 자동화 구현

## 10. 프로젝트 2 주제

[자동화할 반복 업무 작성]

## 11. 자동화하려는 이유

[Github 이슈 자동 알림]

---

## 12. 사용 도구

1. 도구 이름: [MAKE]
2. 선택 이유: [조건 분기 쉽게 구현 가능]

---

## 13. 워크플로우 설계

1. Trigger: [Github 이슈 발생]
2. 조건 분기: [Router - 업데이트 대상에 따른 분리]  
3. Action 1: [Google Sheet]
4. Action 2: [Discord]


[Trigger] Github 이슈 발생

↓

[조건 분기] Router

├─ [분기 1] 기타 업데이트

└─ [분기 2] README 업데이트

↓

[Action 1] Google Sheet 기록

↓

[Action 2] Discord 알림

---

## 14. 프로젝트 2 구현 결과
14-1. 캡처
-워크플로우 구성 화면

<img width="1113" height="592" alt="image (13)" src="https://github.com/user-attachments/assets/641b9a83-b2d0-4265-bd3b-e3f3f97da0c0" />

-전체 실행 결과

<img width="419" height="80" alt="image" src="https://github.com/user-attachments/assets/a30ef79d-b85d-4fd4-ae32-4940499e9190" />

-분기 1 실행 결과

<img width="940" height="89" alt="image (14)" src="https://github.com/user-attachments/assets/cba9536c-28f1-47d9-b66a-22ce57818c5e" />

-분기 2 실행 결과

<img width="871" height="503" alt="image (15)" src="https://github.com/user-attachments/assets/f98fc675-bd09-486f-ad28-88e74b54f23c" />

---

## 15. 테스트 결과 [데이터 / 예상 결과 / 실제 결과]

-테스트 1: [PDF 파일 깃허브 업로드/라우터를 통해 기타 수정 루트로 실행/제목에 README로 써있어서 README 루트로 실행됨]

-테스트 2: [디스코드 날짜표기 형식/ 년월일시간 순서의 날짜 형식 /ISO 8601 날짜형식 ]

-테스트 3: [시나리오 실행/ 오류 없이 실행 / branch 아닌 main 저장으로 인식 못함]

---

## 16. 문제점 및 개선

발견한 문제: [15번 실제 결과]

해결 방법:
-테스트1 : file 업로드를 README로 인식하지 않는 필드사용(Message Headline)

-테스트2: YYYY-MM-DD hh:mm A 형식으로 변환(formatDate 필드)

-테스트3 : Pull Request가 적용된 branch에 이슈 업로드

추가 개선점: [Discord 알림 형식 깔끔하게 반영]

---

## 17. 민감정보 처리

API Key 노출 여부: [없음]

Token 노출 여부: [없음]

Webhook URL 노출 여부: [없음]

이메일/전화번호/이름 처리: [해당 없음]

캡처 이미지 민감정보 처리: [해당 없음]

---

## 18. 배운 점

-2개 프로젝트를 진행하며 MAKE 사용을 조금 더 익숙하게 할 수 있게 되었습니다.

-모듈을 배치하면서 여러가지 기능의 차이점을 알게 되었습니다.

-형식 변환 방법에 대해 공부하게 되었습니다.

---

## 19. 어려웠던 점

-원하는 워크플로우 자동화를 위해 설계하는 과정 자체가 익숙지 않아 전체 흐름을 잡지 못하고 단계별로 수정하는 일이 많았습니다.

-Pull Request 개념을 잡지 못해 깃허브 연동 과정에서 많은 시간 소모를 하였습니다.

---

## 20. 최종 소감
- 여러 가지 프로젝트를 진행하면서 간단한 워크플로우 정도는 만들 수 있을 정도로 사용체계에 익숙해졌습니다.

- 이론만 가지고는 습득하는 데에 시간이 많이 걸렸을 것 같은데, 직접 실행해보며 오류를 수정해 나가다 보니 훨씬 빠르게 배울 수 있었습니다.
