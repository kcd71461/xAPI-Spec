# xAPI 한국어 번역 용어집

이 번역에서 사용한 용어와 표기 원칙을 정리한 문서입니다. 번역문을 읽다가 용어가 헷갈리면 이 문서를 참고하세요.

## 표기 원칙

* **스펙 고유 객체·리소스 이름은 영어 그대로 씁니다.** `Statement`, `Actor`, `Verb`, `Object`, `Activity`처럼 스펙에서 대문자로 시작하는 고유 개념은 JSON 속성명·API 이름과 바로 대응되도록 원어를 유지합니다. 처음 정의되는 곳에서만 한국어 설명을 괄호로 붙입니다.
* **규범 키워드(MUST, SHOULD, MAY 등)는 한국어로 풀어 쓰고 원어를 괄호로 함께 적습니다.** 예: "반드시 포함해야 한다(MUST)".
* **JSON, 코드, URL, HTTP 헤더, 쿼리 파라미터, 속성명은 번역하지 않습니다.**
* 본문은 기술 문서에 맞게 평서체("~한다", "~이다")로 씁니다.
* 원문과 번역이 다르면 **원문이 우선**합니다.

## 규범 키워드 (RFC 2119)

| 원문 | 번역 표기 | 의미 |
|---|---|---|
| MUST / REQUIRED | 반드시 ~해야 한다(MUST) | 절대적 요구사항 |
| MUST NOT | ~해서는 안 된다(MUST NOT) | 절대적 금지 |
| SHOULD / RECOMMENDED | ~해야 한다(SHOULD), ~하는 것을 권장한다(SHOULD) | 타당한 이유가 없는 한 따라야 함 |
| SHOULD NOT | ~하지 않아야 한다(SHOULD NOT) | 타당한 이유가 없는 한 하지 말아야 함 |
| MAY / OPTIONAL | ~할 수 있다(MAY) | 선택 사항 |
| Required / Recommended / Optional (표) | 필수 / 권장 / 선택 | 표의 Required 열 값 |

## 원어 유지 용어 (한국어 설명)

| 용어 | 설명 |
|---|---|
| Statement | 학습 경험 하나를 기록한 데이터 단위. "누가(Actor) 무엇을 했다(Verb) 무엇을(Object)" 구조 |
| Actor | Statement의 행위 주체 (Agent 또는 Group) |
| Agent | 개인(사람 또는 시스템) 하나를 나타내는 Actor |
| Group | 여러 Agent의 모음을 나타내는 Actor |
| Identified Group / Anonymous Group | 식별된 Group / 익명 Group |
| Verb | Actor가 한 행위 |
| Object | 행위의 대상 (Activity, Agent, Group, Sub-Statement, StatementRef) |
| Activity | 상호작용의 대상이 되는 학습 활동 단위 |
| Activity Definition | Activity의 메타데이터 정의 |
| Result | 결과 (점수, 성공 여부, 완료 여부 등) |
| Context | 맥락 정보 |
| Timestamp / Stored | 경험이 발생한 시각 / LRS에 저장된 시각 |
| Authority | Statement의 진위를 보증하는 주체 |
| Attachment | Statement에 첨부되는 파일 |
| Extension | 확장 속성 |
| Sub-Statement / StatementRef | 하위 Statement / 다른 Statement 참조 |
| Voiding / voided Statement | 무효화 / 무효화된 Statement |
| Document | LRS에 저장되는 비정형 데이터 (State, Activity Profile, Agent Profile) |
| State | Activity·Agent 조합별 상태 Document |
| Activity Profile / Agent Profile | Activity 또는 Agent에 대한 Profile Document |
| Learning Record Store (LRS) | 학습 기록 저장소 |
| Learning Record Provider (LRP) | 학습 기록 제공자 (Statement를 생성해 전송하는 주체) |
| Learning Record Consumer (LRC) | 학습 기록 소비자 (LRS에서 데이터를 조회하는 주체) |
| Activity Provider (AP) | 액티비티 제공자 (LRP의 이전 명칭) |
| Client | 클라이언트 |
| Endpoint / Resource | 엔드포인트 / 리소스 |
| Inverse Functional Identifier (IFI) | 역함수 식별자. Agent를 고유하게 식별하는 속성 (mbox, mbox_sha1sum, openid, account) |
| IRI / IRL / URI / URL | 원어 유지 |
| Language Map | 언어 맵 (언어 태그 → 문자열) |
| Profile | xAPI 프로파일 (특정 커뮤니티·도메인용 규칙 모음) |
| Vocabulary | 어휘 (Verb, Activity Type 등 IRI의 모음) |
| Community of Practice (CoP) | 실천 공동체 |
| Registration | 등록 (하나의 학습 시도를 묶는 UUID) |
| Canonical / Canonical Format | 정규 / 정규 형식 |
| Signed Statement | 서명된 Statement |
| Metadata / Hosted Metadata | 메타데이터 / 호스팅된 메타데이터 |
| Concurrency | 동시성 제어 |
| Authentication / Authorization | 인증 / 인가 |
| Immutable / Immutability | 불변 / 불변성 |
| Interaction Activity | 상호작용 Activity (cmi.interaction) |
| Conformance / Conformant | 적합성 / 적합한 |
