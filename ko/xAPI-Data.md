[English](../xAPI-Data.md) | **한국어** · [한국어 README](./README.md) · [용어집](./GLOSSARY.md)

> 이 문서는 xAPI 1.0.3 스펙의 **비공식 한국어 번역**입니다. 원문과 번역의 내용이 다를 경우 [영어 원문](../xAPI-Data.md)이 우선합니다.

<a name="experience-api"></a>
# Experience API
<a name="advanced-distributed-learning-adl-co-laboratories"></a>
## Advanced Distributed Learning (ADL) Co-Laboratories

>#### 라이선스 (License)

>"Copyright 2013 Advanced Distributed Learning (ADL) Initiative, U.S. Department of Defense

>Apache License, Version 2.0(이하 "License")에 따라 라이선스가 부여된다. 이 License를 준수하지 않는 한 
>이 파일을 사용할 수 없다. License 사본은 다음에서 얻을 수 있다.
>http://www.apache.org/licenses/LICENSE-2.0

>관련 법률에서 요구하거나 서면으로 동의하지 않는 한, License에 따라 배포되는 소프트웨어는 
>명시적이든 묵시적이든 어떠한 종류의 보증이나 조건 없이 "있는 그대로(AS IS)" 배포된다. 
>License에 따른 권한 및 제한 사항을 규정하는 구체적인 내용은 
>License를 참조한다."

>이 문서는 미 국방부 차관보 대리실(즉응태세, Office of the Deputy Assistant Secretary of Defense (Readiness)) 
>산하 Advanced Distributed Learning (ADL) Initiative를 지원하기 위해 Experience API Working Group 구성원들(명단은 
>[CONTRIBUTING.md](../CONTRIBUTING.md#contributors) 참조)이 작성했다. 모든 의견과 문의는 
>helpdesk@adlnet.gov 로 보내 주기 바란다.  

<a name="table-of-contents"></a>
## 목차 (Table of Contents)
*	1부:	[Experience API 소개](./xAPI-About.md#part-one-about-the-experience-api)  
	*	1.0.	[소개](./xAPI-About.md#10-introduction) 
	*	2.0.	[이 문서의 사용법](./xAPI-About.md#20-how-to-use-this-document)  
		*	2.1.	[MUST / SHOULD / MAY](./xAPI-About.md#21-must--should--may)  
	 	*	2.2.	[설명 텍스트와 표의 해석 지침](./xAPI-About.md#22-guidelines-for-interpreting-descriptive-text-and-tables)  
	*	3.0.	[직렬화와 JSON(JavaScript Object Notation)](./xAPI-About.md#30-serialization-and-javascript-object-notation-json)
	*	4.0.	[정의](./xAPI-About.md#40-definitions) 
	*	5.0.	[xAPI 구성 요소](./xAPI-About.md#50-xapi-components) 
	*	6.0.	[xAPI 확장](./xAPI-About.md#60-extending-xapi) 
	*	7.0.	[프로파일과 실천 공동체](./xAPI-About.md#70-profiles-vocabularies-and-communities-of-practice)  
	*	[부록](./xAPI-About.md#appendices)  
		*	[부록 A: 개정 이력](./xAPI-About.md#appendix-a-revision-history)  
		*	[부록 B: cmi5 예제](./xAPI-About.md#appendix-b-cmi5-example)  
*	2부:	[Experience API 데이터](./xAPI-Data.md#part-two-experience-api-data)  
	*	1.0.	[Document](./xAPI-Data.md#10-documents) 
	*	2.0.	[Statement](./xAPI-Data.md#20-statements)  
		*	2.1.	[목적](./xAPI-Data.md#21-purpose)  
	 	*	2.2.	[형식 요구사항](./xAPI-Data.md#22-formatting-requirements) 
	 	*	2.3.	[Statement 생명주기](./xAPI-Data.md#23-statement-lifecycle) 
		 	*	2.3.1.	[Statement 불변성](./xAPI-Data.md#231-statement-immutability) 
		 	*	2.3.2.	[무효화(Voiding)](./xAPI-Data.md#232-voiding) 
   		*	2.4.	[Statement 속성](./xAPI-Data.md#24-statement-properties)  
	        *	2.4.1.	[ID](./xAPI-Data.md#241-id)  
	        *	2.4.2.	[Actor](./xAPI-Data.md#242-actor)  
	        *	2.4.3.	[Verb](./xAPI-Data.md#243-verb)  
	        *	2.4.4.	[Object](./xAPI-Data.md#244-object)  
	        *	2.4.5.	[Result](./xAPI-Data.md#245-result)  
	        *	2.4.6.	[Context](./xAPI-Data.md#246-context)  
	        *	2.4.7.	[Timestamp](./xAPI-Data.md#247-timestamp)  
	        *	2.4.8.	[Stored](./xAPI-Data.md#248-stored)  
	        *	2.4.9.	[Authority](./xAPI-Data.md#249-authority)  
	        *	2.4.10.	[Version](./xAPI-Data.md#2410-version)  
	        *	2.4.11.	[Attachments](./xAPI-Data.md#2411-attachments)  
    	*	2.5.	[Statement 조회](./xAPI-Data.md#25-retrieval-of-statements)   
    	*	2.6.	[서명된 Statement](./xAPI-Data.md#26-signed-statements)  
	*	3.0.	[메타데이터](./xAPI-Data.md#30-metadata)
		*	3.1.	[IRI 요구사항](./xAPI-Data.md#31-iri-requirements)  
		*	3.2.	[호스팅된 메타데이터](./xAPI-Data.md#32-hosted-metadata)  
    *	4.0.	[특수 데이터 타입과 규칙](./xAPI-Data.md#40-special-data-types-and-rules)  
		*	4.1.	[Extensions](./xAPI-Data.md#41-extensions) 
		*	4.2.	[언어 맵(Language Maps)](./xAPI-Data.md#42-language-maps)
		*	4.3.	[IRI](./xAPI-Data.md#43-iris)
		*	4.4.	[UUID](./xAPI-Data.md#44-uuids)
		*	4.5.	[ISO 8601 타임스탬프](./xAPI-Data.md#45-iso-8601-timestamps)
		*	4.6.	[ISO 8601 기간(Duration)](./xAPI-Data.md#46-iso-8601-durations)
	*	[부록](./xAPI-Data.md#appendices)  
		*	[부록 A: Statement 예제](./xAPI-Data.md#appendix-a-example-statements)  
		*	[부록 B: 다양한 유형의 Statement Object 예제](./xAPI-Data.md#appendix-b-examples-of-statements-objects-of-different-types)  
		*	[부록 C: "cmi.interaction" 유형 Activity의 정의 예제](./xAPI-Data.md#appendix-c-example-definitions-for-activities-of-type-cmiinteraction)  	
		*	[부록 D: 서명된 Statement 예제](./xAPI-Data.md#appendix-d-example-signed-statement)  
*	3부:	[데이터 처리, 검증 및 보안](./xAPI-Communication.md#part-three-data-processing-validation-and-security)  
	*	1.0.	[요청](./xAPI-Communication.md#10-requests)
		*	1.1.	[HEAD 요청 구현](./xAPI-Communication.md#11-head-request-implementation)  
	 	*	1.2.	[헤더](./xAPI-Communication.md#12-headers) 
	 	*	1.3.	[대체 요청 구문](./xAPI-Communication.md#13-alternate-request-syntax) 
	 	*	1.4.	[인코딩](./xAPI-Communication.md#14-encoding) 
	 	*	1.5.	[콘텐츠 유형](./xAPI-Communication.md#15-content-types) 
	        *	1.5.1.	[Application/JSON](./xAPI-Communication.md#151-applicationjson) 
	        *	1.5.2.	[Multipart/Mixed](./xAPI-Communication.md#152-multipartmixed)
	*	2.0.	[리소스](./xAPI-Communication.md#20-resources)   
	 	*	2.1.	[Statement 리소스](./xAPI-Communication.md#21-statement-resource) 
	 	*	2.2.	[Document 리소스](./xAPI-Communication.md#doctransfer) 
	 	*	2.3.	[State 리소스](./xAPI-Communication.md#23-state-resource) 
	 	*	2.4.	[Agents 리소스](./xAPI-Communication.md#24-agents-resource) 
	 	*	2.5.	[Activities 리소스](./xAPI-Communication.md#25-activities-resource) 
	 	*	2.6.	[Agent Profile 리소스](./xAPI-Communication.md#26-agent-profile-resource) 
	 	*	2.7.	[Activity Profile 리소스](./xAPI-Communication.md#27-activity-profile-resource) 
	 	*	2.8.	[About 리소스](./xAPI-Communication.md#28-about-resource) 
   	*	3.0.	[데이터 검증](./xAPI-Communication.md#30-data-validation)     
    	*	3.1.	[동시성 제어](./xAPI-Communication.md#31-concurrency)  
    	*	3.2.	[오류 코드](./xAPI-Communication.md#32-error-codes)
    	*	3.3     [버전 관리](./xAPI-Communication.md#33-versioning)  
    *	4.0.	[인증](./xAPI-Communication.md#40-authentication)  
		*	4.1.	[OAuth 1.0 인증 시나리오와 방법](./xAPI-Communication.md#41-oauth-10-authentication-scenarios-and-methods) 
		*	4.2.	[OAuth 1.0 인가 범위](./xAPI-Communication.md#42-oauth-10-authorization-scope)
    *	5.0	[보안](./xAPI-Communication.md#50-security)
	*	[부록](./xAPI-Communication.md#appendices)  
		*	[부록 A: Statement를 1.0.0으로 변환하기](./xAPI-Communication.md#appendix-a-converting-statements-to-100)  
		*	[부록 B: 전체 리소스 표](./xAPI-Communication.md#appendix-b-table-of-all-resources)  
		*	[부록 C: 교차 도메인 요청 예제](./xAPI-Communication.md#appendix-c-cross-domain-request-example)  

<a name="part-two-experience-api-data"></a>
# 2부: Experience API 데이터 (Part Two: Experience API Data)

<a name="10-documents"></a>
## 1.0 Documents

Experience API는 Learning Record Provider가 임의의 데이터를 Document 형태로 저장할 수 있는 기능을 제공한다. 이 데이터는 
대체로 비정형이며, 그 덕분에 유연하게 활용할 수 있다. Document 동작에 관한 세부 사항은 [3부](./xAPI-Communication.md#doctransfer)에서 확인할 수 있다. 


<a name="20-statements"></a>
## 2.0 Statements  

<a name="21-purpose"></a>
### 2.1 목적 (Purpose)

Statement는 xAPI에서 추적하려는 모든 종류의 경험 또는 이벤트에 대한 증거이다. 
Statement는 기계가 읽을 수 있는 JSON 형식을 따르지만, 자연어로도 쉽게 기술할 수 있다. 
이는 설계 과정에서 매우 유용하다. Statement는 집계·분석되어, 개별 부분의 단순한 합보다 
전체 경험에 대해 더 큰 의미를 제공하도록 의도된 것이다.

<a name="22-formatting-requirements"></a>
### 2.2 형식 요구사항 (Formatting Requirements)

<a name="details"></a>
###### 세부 사항 (Details)

Statement에서 사용하는 모든 속성은 특정 데이터 타입으로 제한된다. 명확성을 위해 핵심 요구사항을 
여기에 정리하며, 특히 이 명세에 적합한(conformant) 것으로 간주되기 위해 xAPI 구성 요소가 특정 방식으로 동작해야 
하는 책임이 있는 부분을 강조한다.

<a name="requirements"></a>
###### 요구사항 (Requirements)

* Statement와 기타 객체는 값이 빈 객체인 속성을 포함하지 않아야 한다(SHOULD NOT). 
* Statement는 각 속성을 반드시 최대 한 번만 사용해야 한다(MUST).
* Statement는 반드시 "actor", "verb", "object"를 사용해야 한다(MUST).
* Statement는 속성을 임의의 순서로 사용할 수 있다(MAY).
* LRS는 [예외로 나열된](#231-statement-immutability) 속성을 제외한 어떤 속성도 다른 직렬화 형태로 
반환해서는 안 된다(MUST NOT).

<a name="learning-record-provider-requirements"></a>
###### Learning Record Provider 요구사항 (Learning Record Provider Requirements)

다음 요구사항은 이미 다른 곳에 포함된 요구사항 중 특히 중요한 것을 다시 언급하여 강조하고, 명확히 하며,
구현 지침을 제공하기 위한 것이다. 완전한 IRI 검증이나 속성이 한 번만 나타나는지에 대한 검증 같은 일부 검증은 
매우 어렵기 때문에, 데이터 이식성을 보장하는 부담의 상당 부분은 
Learning Record Provider에게 있다.

* IRI가 요구되는 값은 반드시 유효한 IRI로 전송해야 한다(MUST). 
* 같은 이유로, 언어 맵(Language Map)의 키는 반드시 유효한 [RFC 5646](http://tools.ietf.org/html/rfc5646) 
언어 태그로 전송해야 한다(MUST).
* IRI를 구성할 때는 문자열 연결 대신 라이브러리를 사용해야 한다(SHOULD). 
* 값은 별도로 명시되지 않는 한 대소문자를 구분하는 것으로 간주해야 한다(SHOULD). 
* 대소문자를 구분하지 않는 데이터를 전송할 때는 소문자를 사용해야 한다(SHOULD).
* 이 명세에서 명시적으로 허용하지 않는 한 Statement에 추가 속성을 넣지 않아야 한다(SHOULD* NOT). 
* 하나의 객체 안에서 속성이 여러 번 나타나지 않아야 한다(SHOULD not). 객체 안에서 속성이 여러 번 사용되면 
LRS의 동작은 정의되지 않으며, 대부분의 LRS는 각자 사용하는 프로그래밍 언어의 기존 JSON 파싱 
기능을 사용할 것으로 예상된다. 

__참고:__ LRS는 추가 속성을 포함한 Statement를 거부하는 것이 권장된다. Statement에 추가 속성이 있으면 
해당 Statement는 모든 LRS와 상호 운용될 수 없게 된다. 

<a name="lrs-requirements"></a>
###### LRS 요구사항 (LRS Requirements)

* LRS는 다음과 같은 Statement를 반드시 거부해야 한다(MUST).
    * (extension 내부를 제외하고) null 값이 하나라도 있는 경우.
    * 잘못된 데이터 타입이 사용된 경우. 예를 들어: 
        * 숫자가 요구되는 곳에 문자열이 있는 경우(그 문자열이 숫자를 담고 있더라도), 또는 
        * 불리언이 요구되는 곳에 문자열이 있는 경우(그 문자열이 불리언 값을 담고 있더라도).
    * 특정 형식(mailto IRI, UUID, IRI 등)의 문자열이 요구되는 곳에, 빈 문자열을 포함하여
      형식을 따르지 않는 키나 값이 있는 경우.
    * 키의 대소문자가 이 명세에서 지정한 대소문자와 일치하지 않는 경우.
    * 열거된 값으로 제한되는 값의 대소문자가 이 명세에 제시된 열거 값과
      정확히 일치하지 않는 경우.
    * 이 명세에서 허용하지 않는 키나 값이 있는 경우.
    * 스킴(scheme)이 없는 IRL 또는 IRI 값을 포함하는 경우.
* LRS는 최소한 언어 맵 키의 토큰 길이 순서가 [RFC 5646](http://tools.ietf.org/html/rfc5646) 표준과 
일치하는지는 반드시 검증해야 한다(MUST).
* LRS는 숫자를 최소한 IEEE 754 32비트 부동소수점 수의 정밀도로 반드시 처리하고 
저장해야 한다(MUST).
* LRS는 파라미터 값을 Statement 내 같은 타입의 값에 요구되는 것과 동일한 기준으로 
반드시 검증해야 한다(MUST). __참고:__ 문자열 파라미터 값은 JSON에서처럼 따옴표로 감싸지 않는다.
* LRS는 별도로 명시되지 않는 한 모든 값을 대소문자를 구분하여 다뤄야 한다(SHOULD).
* LRS는 형식 미준수 거부 요구사항을 충족하기 위해 IRL 및 IRI 형식에 대해 최선의 노력(best-effort) 
검증을 사용할 수 있다(MAY).
* LRS는 형식 미준수 거부 요구사항을 충족하기 위해 언어 맵 키에 대해 최선의 노력(best-effort) 
검증을 사용할 수 있다(MAY).
* 이 명세에서 명시적으로 허용하지 않는 한 Statement 및 기타 객체에 추가 속성을 넣지 않아야 하며(SHOULD* NOT), 
LRS는 그러한 추가 속성을 포함한 Statement를 거부해야 한다(SHOULD*).


<a name="23-statement-lifecycle"></a>
### 2.3 Statement 수명 주기 (Statement Lifecycle)

Statement는 추적된 학습 경험에 관한 정보이다. 일반적으로 Statement가 나타내는 정보는 
이미 일어난 일이다. 따라서 "display" 또는 Verb id의 사람이 읽을 수 있는 부분에 쓰이는 자연어는 
대개 과거 시제를 사용한다.

Statement는 영구적인 것으로 간주된다. 이 명세 안에서 Statement를 되돌리는 유일한 방법은 
[무효화하는 것](#232-voiding)이다. 무효화는 Statement를 파기하는 것이 아니라, 해당 Statement의 증거를 무시해야 함을 나타낸다.


<a name="231-statement-immutability"></a>
#### 2.3.1 Statement 불변성 (Statement Immutability)

Statement는 불변이다(변경할 수 없다). 다음은 이 규칙의 예외이거나 이 규칙이 적용되지 않는 영역이다.

* LRS 처리 과정에서 이루어질 수 있거나 반드시 이루어져야 하는 속성 할당 
("id", "authority", "stored", "timestamp", "version"). 

* Statement가 참조하는 Activity Definition. Statement에서 참조하는 Activity Definition의 
내용은 Statement 자체의 일부로 간주되지 않는다. 즉, 참조된 Activity Definition이 변경되면 Statement를 
JSON으로 깊게 직렬화(deep serialization)한 결과도 변경된다(자세한 내용은 [Statement 리소스의](./xAPI-Communication.md#21-statement-resource) "format" 
파라미터 참조).  

* Statement가 참조하는 Verb. Verb의 "display" 속성은 Statement 자체의 일부로 
간주되지 않는다(자세한 내용은 [Statement 리소스의](./xAPI-Communication.md#21-statement-resource) "format" 파라미터 참조). 

* Timestamp 데이터의 직렬화. 이는 불변 Statement 자체의 일부로 간주되지 않는다. 
예를 들어, Statement의 "timestamp" 및 "stored" 속성은 참조하는 시점이 바뀌지 않는 한 
저장될 때와 다른 시간대로 반환될 수 있다. 
자세한 내용은 [2.4.7 Timestamp](#247-timestamp)와 [2.4.8 Stored](#248-stored)를 참조한다. 

* 순서 없는 목록의 직렬화. Group 안의 Agent 목록은 순서 있는 목록으로 간주되지 
않는다. 따라서 LRS는 이 Agent 목록을 임의의 순서로 반환할 수 있다. [Group](#2422-when-the-actor-objecttype-is-group)을 참조한다.

* Attachment. Attachment는 Statement의 일부가 아니며, Client가 Statement를 요청할 때 LRS는 
Attachment 없이 Statement를 반환한다(자세한 내용은 [Statement 리소스의](./xAPI-Communication.md#21-statement-resource) "attachments" 파라미터 참조).

* 대소문자 구분. 일부 속성은 대소문자를 구분하지 않으므로, 대소문자가 바뀌어도 불변성에 
영향을 주지 않는다. 예를 들어 이메일 주소의 도메인 부분은 대소문자를 구분하지 않는다. 대소문자를 구분하지 않는 
텍스트에는 소문자를 사용하는 것이 권장된다. 

다음은 명시적으로 예외가 **아니며** 이 규칙의 적용을 **받는다**.

* Result Duration. 월, 연도, 심지어 분의 길이도 가변적이고, "timestamp" 속성은 경험의 시작, 
중간, 끝 중 어느 것이든 나타낼 수 있는 유연한 성격을 지니므로, LRS가 Result Duration을 정확히 
역직렬화하여 시간 단위 간에 변환하는 것은 불가능하다. 이러한 이유로 Statement 비교 목적에서 
Result Duration은 문자열로 간주된다. 

<a name="statement-comparision-requirements"></a>
###### Statement 비교 요구사항 (Statement Comparision Requirements)
이 명세에는 Statement가 일치하는지 확인하기 위해 비교해야 하는 여러 시나리오가
기술되어 있다. 이러한 시나리오에서는 다음 규칙이 적용된다.

* [Statement 불변성의 예외](#231-statement-immutability)로 인해 발생했을 수 있는 차이는 
반드시 무시해야 한다(MUST).
* [예외로 나열되지](#231-statement-immutability) 않은 속성의 직렬화 형태가 다른 데 따른 차이는
무시해서는 안 된다(MUST not). 


<a name="232-voiding"></a>
#### 2.3.2 무효화 (Voiding)

<a name="rationale"></a>
###### 근거 (Rationale)

Statement는 논리적으로 변경하거나 삭제할 수 없다는 사실 덕분에, LRS가 정확하고 완전한 데이터 모음을 
보유하고 있다는 확실성이 보장된다. 이러한 Statement의 불변성은 Experience API의 분산적 특성을 
가능하게 하는 핵심 요소이다.

그러나 모든 Statement가 한 번 발행된 뒤 영구히 유효한 것은 아니다. 실수나 기타 요인으로 인해 이전에 작성된 
Statement를 무효로 표시해야 할 수도 있다. 이를 "Statement 무효화(voiding a Statement)"라고 하며, 이 목적을 위해 
예약된 Verb `http://adlnet.gov/expapi/verbs/voided`를 사용한다. 다른 Statement를 무효화하는 Statement는
그 자체가 무효화될 수 없다.

<a name="requirements-1"></a>
###### 요구사항 (Requirements)

* 다른 Statement를 무효화하는 Statement를 발행할 때, 해당 무효화 Statement의 Object는 
"objectType" 속성을 반드시 `StatementRef`로 설정해야 한다(MUST).
* 다른 Statement를 무효화하는 Statement를 발행할 때, 해당 무효화 Statement의 Object는 
무효화 대상 Statement의 id를 반드시 "id" 속성으로 지정해야 한다(MUST).
* LRS는 자신이 보유한 Statement가 그 자체로 무효화 Statement가 아니고, 그 Statement를 참조하는 무효화 
Statement를 LRS가 함께 보유하고 있는 경우에만, 그리고 그 경우에는 반드시, 해당 Statement를 무효화된 것으로 간주해야 한다(MUST).
* 다른 Statement를 무효화하는 Statement를 수신했을 때, 요청이 Statement를 무효화할 권한이 있는 출처에서 온 것이 아니면 
LRS는 해당 무효화 Statement를 포함한 요청 전체를 `403 Forbidden`으로 거부해야 한다(SHOULD).
* 다른 Statement를 무효화하는 Statement를 수신했을 때, LRS는 해당 무효화 Statement의 Object가 
존재하지 않는다는 이유로 요청을 거부하지 않아야 한다(SHOULD NOT*). 
* 다른 Statement를 무효화하는 Statement를 수신했을 때, LRS는 방금 무효화된 Statement로 인해 도입된 Activity 또는 
Agent 정의의 변경 사항을 롤백할 수 있다(MAY).
* 이전에 무효화된 Statement를 "무효화 취소(unvoid)"하려는 Learning Record Provider는 
해당 Statement를 새 id로 다시 발행해야 한다(SHOULD).

__참고:__ 다른 Statement를 참조하는 방법에 대한 자세한 내용은 [Object가 Statement인 경우](#2443-when-the-object-is-a-statement)의 
["Statement 참조"](#statement-references)를 참조한다. 무효화된 Statement가 조회 시 어떻게 동작하는지는 
3부의 [StatementRef](./xAPI-Communication.md#filter-conditions-for-statementrefs)를 참조한다).

<a name="example"></a>
###### 예제 (Example)

이 예제 Statement는 Statement id "e05aa883-acaf-40ad-bf54-02c8ce485fb0"으로 식별되는 이전 Statement를 무효화한다.

```
{
	"actor" : {
		"objectType": "Agent",
		"name" : "Example Admin",
		"mbox" : "mailto:admin@example.adlnet.gov"
	},
	"verb" : {
		"id":"http://adlnet.gov/expapi/verbs/voided",
		"display":{
			"en-US":"voided"
		}
	},
	"object" : {
		"objectType":"StatementRef",
		"id" : "e05aa883-acaf-40ad-bf54-02c8ce485fb0"
	}
}
```  
<a name="24-statement-properties"></a>
### 2.4 Statement 속성 (Statement Properties)  

<a name="details-1"></a>
###### 세부 사항 (Details)
Statement의 각 속성에 대한 세부 사항은 아래 표에 설명되어 있다.  

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr><td>id</td><td>UUID</td>
	<td>Learning Record Provider가 설정하지 않은 경우 LRS가 할당하는 UUID.</td>
	<td>권장</td></tr>
	<tr><td><a href="#242-actor">actor</a></td><td>Object</td>
	<td>Statement의 대상이 되는 주체로, <a href="#2421-when-the-actor-objecttype-is-agent">Agent</a> 또는 
		<a href=#2422-when-the-actor-objecttype-is-group>Group</a> Object이다.</td>
	<td>필수</td></tr>
	<tr><td><a href="#243-verb">verb</a></td><td>Object</td>
	<td>Actor가 수행한 행위.</td>
	<td>필수</td></tr>
	<tr><td><a href="#244-object">object</a></td><td>Object</td>
	<td>Statement의 Object(대상)가 되는 Activity, Agent 또는 다른 Statement. 
	</td>
	<td>필수</td></tr>
	<tr><td><a href="#245-result">result</a></td><td>Object</td>
	<td>측정된 결과를 나타내는 추가 세부 정보인 Result Object.</td>
	<td>선택</td></tr>
	<tr><td><a href="#246-context">context</a></td><td>Object</td>
	<td>Statement에 더 많은 의미를 부여하는 맥락. 예: Actor가 함께 작업하는 팀, 
	비행 시뮬레이터에서 시나리오를 시도한 고도.</td>
	<td>선택</td></tr>
	<tr><td><a href="#247-timestamp">timestamp</a></td><td><a href="#45-iso-8601-timestamps">Timestamp</a></td>
	<td>이 Statement에 기술된 이벤트가 발생한 시각의 Timestamp. 제공되지 않으면 LRS가 설정한다.</td>
	<td>선택</td></tr>
	<tr><td><a href="#248-stored">stored</a></td><td><a href="#45-iso-8601-timestamps">Timestamp</a></td>
	<td>이 Statement가 기록된 시각의 Timestamp. LRS가 설정한다.</td>
	<td>LRS가 설정</td></tr>
	<tr><td><a href="#249-authority">authority</a></td><td>Object</td>
	<td>이 Statement가 참임을 보증하는 Agent 또는 Group. LRS가 인증을 기반으로 
	검증한다. 제공되지 않았거나 Learning Record Provider와 LRS 간에 강한 신뢰 관계가 
	구축되지 않은 경우 LRS가 설정한다.</td>
	<td>선택</td></tr>
	<tr><td><a href="#2410-version">version</a></td><td>Version</td>
	<td>Statement에 연관된 xAPI 버전으로, <a href="http://semver.org/spec/v1.0.0.html">Semantic Versioning 1.0.0</a>에 따른 형식이다.</td>
	<td>권장하지 않음</td></tr>
	<tr>
		<td><a href="#2411-attachments">attachments</a></td>
		<td>Ordered array of Attachment Objects</td>
	    <td>Statement에 대한 Attachment의 헤더</td>
	<td>선택</td></tr>
</table>

<a name="example-1"></a>
###### 예제 (Example)

반드시 사용해야 하거나(MUST) 사용해야 하는(SHOULD) 모든 속성을 사용한, 가능한 가장 단순한 Statement의 예이다.
관련이 있는 경우 선택 속성도 채우는 것이 권장된다. 
이 Statement를 LRS에서 반환할 때는 LRS가 추가한 몇 가지 속성이 포함된다.  
```
{
    "id": "12345678-1234-5678-1234-567812345678",
    "actor":{
        "mbox":"mailto:xapi@adlnet.gov"
    },
    "verb":{
        "id":"http://adlnet.gov/expapi/verbs/created",
        "display":{
            "en-US":"created"
        }
    },
    "object":{
        "id":"http://example.adlnet.gov/xapi/example/activity"
    }
}
```  
더 많은 예제는 [부록 A: Statement 예제](#appendix-a-example-statements)를 참조한다. 


<a name="241-id"></a>
#### 2.4.1 ID 

<a name="description"></a>
###### 설명 (Description)

UUID이다([RFC 4122](http://www.ietf.org/rfc/rfc4122.txt)의 variant 2에 속하는 모든 버전이 유효하며, UUID는 반드시 
표준 문자열 형식이어야 한다(MUST)).

<a name="requirements-2"></a>
###### 요구사항 (Requirements)

* id 없이 Statement를 수신한 경우 LRS는 반드시 Statement id를 생성해야 한다(MUST).
* Statement id는 Learning Record Provider가 생성해야 한다(SHOULD).


<a name="242-actor"></a>
#### 2.4.2 Actor  

<a name="description-1"></a>
###### 설명 (Description)
Actor는 행위를 수행한 주체를 정의한다. Statement의 Actor는 Agent 또는 Group일 수 있다. 


<a name="2421-when-the-actor-objecttype-is-agent"></a>
##### 2.4.2.1 Actor의 objectType이 Agent인 경우 (When the Actor objectType is Agent)
<a name="description-2"></a>
###### 설명 (Description)
Agent(개인)는 페르소나 또는 시스템이다.

<a name="details-2"></a>
###### 세부 사항 (Details)

* Agent는 반드시 네 가지 유형의 역함수 식별자(Inverse Functional Identifier) 중 하나(1개)로 식별되어야 한다(MUST)(
 [2.4.2.3 역함수 식별자(Inverse Functional Identifier)](#2423-inverse-functional-identifier) 참조).
* Agent는 둘 이상의 역함수 식별자(Inverse Functional Identifier)를 포함해서는 안 된다(MUST NOT).
* Agent는 Group 식별자로도 사용되는 역함수 식별자(Inverse Functional Identifier)를 사용하지 않아야 한다(SHOULD NOT).

아래 표는 Agent Object의 속성을 나열한다.

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr><td>objectType</td><td>string</td><td><code>Agent</code>. 이 속성은 Agent가 Statement의 object로 사용되는 경우를 제외하면 선택 사항이다.</td>
	<td>선택</td></tr>
	<tr><td>name</td><td>String</td><td>Agent의 전체 이름.</td>
	<td>선택</td></tr>
	<tr><td colspan="2"><a href="#2423-inverse-functional-identifier"> 2.4.2.3 역함수 식별자(Inverse Functional Identifier)</a> 참조</td>
	    <td>해당 Agent에 고유한 역함수 식별자(Inverse Functional Identifier).</td>
	    <td>필수</td></tr>
</table>



<a name="2422-when-the-actor-objecttype-is-group"></a>
##### 2.4.2.2 Actor의 objectType이 Group인 경우 (When the Actor ObjectType is Group)
<a name="description-3"></a>
###### 설명 (Description)

Group은 Agent의 모음을 나타내며, Agent를 사용할 수 있는 대부분의 상황에서 동일하게 사용할 수 
있다. Group에는 Anonymous Group(익명 Group)과 Identified Group(식별된 Group)의 두 가지 유형이 있다.

<a name="details-3"></a>
###### 세부 사항 (Details)

Anonymous Group은 임시로 구성된 팀처럼, 해당 집단에 대해 바로 사용할 수 있는 식별자가 없는 
사람들의 집단을 기술하는 데 사용된다.

아래 표는 Anonymous Group의 모든 속성을 나열한다.

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr><td>objectType</td><td>String</td><td><code>Group</code>. </td><td>필수</td></tr>
	<tr><td>name</td><td>String</td><td>Group의 이름.</td><td>선택</td></tr>
	<tr><td>member</td><td>Array of <a href="#2421-when-the-actor-objecttype-is-agent">Agent Objects</a></td>
	<td>이 Group의 구성원. 순서 없는 목록이다.</td>
	<td>필수</td></tr>
</table>

Identified Group은 Agent 집단을 고유하게 식별하는 데 사용된다.

아래 표는 Identified Group의 모든 속성을 나열한다.

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr><td>objectType</td><td>String</td><td><code>Group</code>. </td><td>필수</td></tr>
	<tr><td>name</td><td>String</td><td>Group의 이름.</td><td>선택</td></tr>
	<tr><td>member</td><td>Array of <a href="#2421-when-the-actor-objecttype-is-agent">Agent Objects</a></td>
	<td>이 Group의 구성원. 순서 없는 목록이다.</td>
	<td>선택</td></tr>
	<tr><td colspan="2"><a href="#2423-inverse-functional-identifier"> 2.4.2.3 역함수 식별자(Inverse Functional Identifier)</a> 참조</td>
	    <td>해당 Group에 고유한 역함수 식별자(Inverse Functional Identifier).</td><td>필수</td></tr>	
</table>

<a name="requirements-3"></a>
###### 요구사항 (Requirements)

* Learning Record Consumer는 각 Anonymous Group을 구성원 집합이 동일하더라도 반드시 서로 다른 것으로 
간주해야 한다(MUST).
* Learning Record Provider는 Group과 관련하여 여러 Statement를 발행하거나, 데이터를 집계하거나, Document를 
저장·조회하려는 경우 Identified Group을 사용해야 한다(SHOULD).
* Learning Record Provider는 특정 Anonymous Group 또는 Identified Group의 "member" 속성에 Agent의 
전체 목록 또는 일부 목록을 포함할 수 있다(MAY).
* Statement를 반환하는 LRS는 Group 구성원 목록을 임의의 순서로 반환할 수 있다(MAY).

<a name="requirements-for-anonymous-groups"></a>
###### Anonymous Group 요구사항 (Requirements for Anonymous Groups)

* Anonymous Group은 구성 Agent를 나열하는 "member" 속성을 반드시 포함해야 한다(MUST).
* Anonymous Group은 "member" 식별자에 Group Object를 포함해서는 안 된다(MUST NOT).

<a name="requirements-for-identified-groups"></a>
###### Identified Group 요구사항 (Requirements for Identified Groups)

* Identified Group은 Inverse Functional Identifier를 정확히 하나(1) 반드시 포함해야 한다(MUST).
* Identified Group은 "member" 속성에 Group Object를 포함해서는 안 된다(MUST NOT).
* Identified Group은 Agent 식별자로도 사용되는 Inverse Functional Identifier를 
사용하지 않아야 한다(SHOULD NOT).
* Identified Group은 구성 Agent를 나열하는 "member" 속성을 포함할 수 있다(MAY).


<a name="2423-inverse-functional-identifier"></a>
##### 2.4.2.3 Inverse Functional Identifier
<a name="description-4"></a>
###### 설명 (Description)
Inverse Functional Identifier(IFI, 역함수 식별자)는 Agent 또는 Identified Group의 값으로, 
오직 해당 Agent 또는 Identified Group만을 가리키는 것이 보장되는 값이다.

<a name="rationale-1"></a>
###### 근거 (Rationale)
Agent와 Group에 대해 데이터를 저장하고 조회하려면 이들을 고유하게 식별할 수 있어야 한다. 
xAPI Statement에서는 Inverse Functional Identifier를 사용하여 이를 달성하는데, 이는 널리 받아들여지는 
FOAF 원칙에서 느슨하게 착안한 것이다([Friend Of A Friend](http://xmlns.com/foaf/spec/#term_Agent) 참조).

<a name="details-4"></a>
###### 세부 사항 (Details)

아래 표는 사용 가능한 모든 Inverse Functional Identifier 속성을 나열한다.

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>Description</th></tr>
	<tr><td><a href="http://xmlns.com/foaf/spec/#term_mbox">mbox</a></td><td>mailto IRI</td><td>요구되는 형식은 "mailto:이메일 주소"이다. <br>
	이 속성과 mbox_sha1sum에는 과거에도 앞으로도 오직 이 Agent에게만 할당되고 다른 누구에게도 할당되지 않는 
이메일 주소만 사용해야 한다(SHOULD).</td></tr>
	<tr><td><a href="http://xmlns.com/foaf/spec/#term_mbox_sha1sum">mbox_sha1sum</a></td><td>String</td><td>mailto IRI(즉, mbox 속성의 값)의 16진수로 인코딩된 SHA1 해시. 요청이 mbox를 기준으로 하는 경우 LRS는 해시가 일치하는 Agent를 포함할 수 있다(MAY).</td></tr>
	<tr><td>openid</td><td>URI</td><td>Agent를 고유하게 식별하는 openID.</td></tr>
	<tr><td>account</td><td><a href="#2424-account-object">Object</a></td><td>기존 시스템(예: LMS 또는 인트라넷)의 사용자 계정.</td></tr>	
</table>

<a name="client-requirements"></a>
###### Client 요구사항 (Client Requirements)
* 이메일 주소의 도메인 부분은 대소문자를 구분하지 않는다. Client는 "mbox_sha1sum" 속성의 SHA1 해시를 
계산할 때 이메일 주소의 도메인 부분에 소문자를 사용해야 한다(SHOULD). 


<a name="2424-account-object"></a>
##### 2.4.2.4 Account Object

<a name="description-5"></a>
###### 설명 (Description)

비공개 시스템(LMS 또는 인트라넷)이나 공개 시스템(소셜 네트워킹 사이트)과 같은 
기존 시스템의 사용자 계정이다.

<a name="details-5"></a>
###### 세부 사항 (Details)

* account Object를 제공하는 시스템이 OpenID를 사용하는 경우, Learning Record Provider는
account Object 대신 openid 속성을 사용해야 한다(SHOULD).
* Learning Record Provider가 Agent 또는 Group에 대한 개인 식별 정보 노출을 우려하는 경우, 
익명성을 유지하면서 한 사람에 관한 모든 Statement를 식별할 수 있도록 불투명한(opaque) 계정 이름(예: 
계정 번호)을 사용해야 한다(SHOULD).

아래 표는 Account Object의 모든 속성을 나열한다.

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr><td>homePage</td><td>IRL</td><td>계정이 속한 시스템의 정규(canonical) 홈페이지. FOAF의 accountServiceHomePage를 기반으로 한다.</td>
	<td>필수</td></tr>
	<tr><td>name</td><td>String</td><td>이 계정에 로그인할 때 사용하는 고유 id 또는 이름. FOAF의 accountName을 기반으로 한다.</td><td>필수</td></tr>
</table>


<a name="example-2"></a>
###### 예시 (Example)

이 예시는 불투명한 account로 식별되는 Agent를 보여준다.

```
{
	"objectType": "Agent",
	"account": {
		"homePage": "http://www.example.com",
		"name": "1625378"
	}
}
``` 


<a name="243-verb"></a>
#### 2.4.3 Verb

<a name="description-6"></a>
###### 설명 (Description)

Verb는 Actor와 Activity 사이의 행위를 정의한다. 

<a name="rationale-2"></a>
###### 근거 (Rationale)

xAPI Statement의 Verb는 학습 경험 중에 수행된 행위를 기술한다. 
xAPI는 특정 Verb를 규정하지 않는다(단, 예약된 Verb인 
[http://adlnet.gov/expapi/verbs/voided](#232-voiding) 하나는 예외이다). 대신 Verb를 만드는 방법을 정의하여, 
실천 공동체(Community of Practice)가 구성원에게 의미 있는 Verb를 정립하고 누구나 사용할 수 있도록 
공개할 수 있게 한다. 미리 정의된 Verb 목록은 그 정의상 한정될 수밖에 없으며, 앞으로 생겨날 
모든 학습 경험을 효과적으로 담아내지 못할 수 있다. 

<a name="details-6"></a>
###### 세부 사항 (Details)

Verb는 Statement 안에서 IRI 하나와, Verb의 의미를 사람이 읽을 수 있게 제공하는 여러 언어 또는 방언별 
표시 이름(display name) 집합으로 구성된 Object로 나타난다. 
아래 표는 Verb Object의 모든 속성을 나열한다.

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr>
		<td>id</td>
		<td>IRI</td>
		<td>Verb 정의에 대응한다. 각 Verb 정의는 
			단어가 아니라 Verb의 의미에 대응한다. 
		</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>display</td>
		<td><a href="#lang-map">Language Map</a></td>
		<td>하나 이상의 언어로 된, 사람이 읽을 수 있는 
			Verb 표현. 이 값은 Statement의 
			의미에 아무런 영향을 주지 않으며, 선택된 Verb에 의해 이미 결정된 의미를 
			사람이 읽을 수 있게 표시하는 역할만 한다.</td>
		<td>권장</td>
	</tr>
</table>

<a name="verb-id-requirements"></a>
###### Verb id 요구사항 (Verb Id Requirements)

* Statement를 읽는 시스템은 의미를 추론할 때 반드시 Verb IRI를 사용해야 한다(MUST).
* id에 담긴 IRI는 사람이 읽을 수 있는 부분을 포함해야 하며(SHOULD), 이 부분은 원시(raw) Statement를 
검토하는 사람이 해당 Verb를 (구문상) 비슷한 다른 Verb와 구별할 수 있을 만큼의 의미를 제공해야 한다(SHOULD).
* 하나의 Verb IRI를 여러 의미를 가리키는 데 사용해서는 안 된다(MUST NOT).

<a name="verb-display-learning-record-provider-requirements"></a>
###### Verb display에 대한 Learning Record Provider 요구사항 (Verb Display Learning Record Provider Requirements)

* 모든 Statement는 "display" 속성을 사용해야 한다(SHOULD).
* "display" 속성은 반드시 Verb IRI에 의해 이미 결정된 의미를 나타내는 데 
사용해야 한다(MUST).

<a name="verb-display-lrs-requirements"></a>
###### Verb display에 대한 LRS 요구사항 (Verb Display LRS Requirements)

아래 요구사항은 LRS가 API를 통해 반환하는 "display" 속성에 관한 것이다.  

* Format이 `exact`인 Statement 조회 요청을 받으면, LRS는 반드시 "display" 속성을 
Statement에 포함된(또는 생략된) 그대로 반환해야 한다(MUST).
* Format이 `ids`인 Statement 조회 요청을 받으면, LRS는 "display" 속성을 포함하지 않아야 한다(SHOULD* NOT).
* Format이 `canonical`인 Statement 조회 요청을 받으면, LRS는 해당 Verb의 
정규(canonical) Display를 반환해야 한다(SHOULD*). 
* LRS는 수신한 Statement에 포함된 Verb의 "display" 속성, 
[3.2 호스팅된 메타데이터](#32-hosted-metadata)에 기술된 메타데이터의 "name" 속성, 또는 다른 곳에 정의된 Verb의 Display를 바탕으로 정규 Display를 결정할 수 있다.

<a name="verb-display-learning-record-consumer-requirements"></a>
###### Verb display에 대한 Learning Record Consumer 요구사항 (Verb Display Learning Record Consumer Requirements)

아래 요구사항은 Learning Record Consumer가 사용자에게 표시하는 display 속성에 관한 것이다. 

* "display" 속성을 Verb의 의미를 바꾸는 데 사용해서는 안 된다(MUST NOT).
* Learning Record Consumer는 "display" 속성을 사용해 Statement로부터 어떠한 의미도 추론해서는 안 된다(MUST NOT).
* Learning Record Consumer는 "display" 속성을 사람에게 표시하는 것 이외의 어떤 목적으로도 
사용해서는 안 된다(MUST NOT). "display" 속성을 Statement의 집계나 분류에 사용하는 것이 
이 요구사항을 위반하는 예이다. 
* 사용자 인터페이스에서 Statement의 Verb를 표시하는 Learning Record Consumer는 
Statement에 포함된 Verb의 "display" 속성, 
[3.2 호스팅된 메타데이터](#32-hosted-metadata)에 기술된 메타데이터의 "name" 속성, 또는 다른 곳에 정의된 Verb의 Display 중 무엇을 표시할지 선택할 수 있다(MAY).
* Statement의 Verb를 표시하는 Learning Record Consumer는 Verb의 의미와 다른 단어를 표시해서는 
안 되지만(MUST NOT), 사람이 읽기 쉽도록 표시되는 어구와 시제를 바꿀 수는 있다(MAY). 

<a name="example-3"></a>
###### 예시 (Example)
이 예시는 권장 속성이 설정되고 미국 영어와 스페인어를 사용하는 Verb를 보여준다. 
```
{
    "id":"http://example.com/xapi/verbs#defenestrated", 
    "display":{
        "en-US":"defenestrated",
        "es" : "defenestrado" 
    } 
}
``` 

위 예시의 Verb는 설명을 위해 포함한 것일 뿐이다. 이 의미를 가진 Verb가 이 id로 정의되어 있다는 
뜻이 아니다. 이는 예약된 Verb [http://adlnet.gov/expapi/verbs/voided](#232-voiding))를 제외하고 
이 스펙 문서에 나오는 모든 예시 Verb에 적용된다.
			
<a name="2431-use-in-language-and-semantics-of-verbs"></a>
##### 2.4.3.1 Verb의 언어와 의미론에서의 사용 (Use in Language and Semantics of Verbs)

<a name="details-7"></a>
###### 세부 사항 (Details)

_의미론 (Semantics)_

Verb id가 나타내는 IRI는 단어 자체가 아니라 단어의 특정한 의미를 식별한다. 

예를 들어 영어 단어 "fired"는 맥락에 따라 "fired(a weapon)"(무기를 발사했다), 
"fired(a kiln)"(가마에 구웠다), "fired(an employee)"(직원을 해고했다)처럼 서로 다른 의미가 될 수 있다. 
이 경우 IRI는 이 가운데 특정한 의미 하나를 식별한다. 

"display" 속성은 시제에 어느 정도 유연성이 있다. Verb id 중 사람이 읽을 수 있는 부분은 
보통 과거 시제를 사용하지만, "display" 속성 안에서 동사를 다른 시제로 활용하는 것이 
Statement 전체로 볼 때 가장 자연스럽다면 그렇게 해도 된다.

_언어 (Language)_

Experience API에서 Verb는 IRI이며, 특정 언어에 얽매이지 않는 특정한 의미를 나타낸다. 

예를 들어 http://example.org/firearms#fire 같은 특정 Verb IRI는 총을 쏘는 행위를 나타낼 수 있고, 
http://example.com/فعل/خواندن 같은 Verb IRI는 책을 읽는 행위를 나타낼 수 있다. 


<a name="244-object"></a>
#### 2.4.4 Object

<a name="description-7"></a>
###### 설명 (Description)

Object는 행위의 대상이 된 것을 정의한다. Statement의 Object는 Activity, Agent/Group, 
SubStatement, 또는 Statement Reference일 수 있다.

몇 가지 예:

* Object가 Activity인 경우: "Jeff가 하이킹에 관한 에세이를 썼다."

* Object가 Agent인 경우: "Nellie가 Jeff를 인터뷰했다."

* Object가 SubStatement 또는 Statement Reference인 경우(구현은 다르지만 사람이 읽을 때는 
비슷함): "Nellie가 'Jeff가 하이킹에 관한 에세이를 썼다'에 댓글을 달았다."

<a name="details-8"></a>
###### 세부 사항 (Details)

이 속성의 값으로 제공되는 Object는 "objectType" 속성을 포함해야 한다(SHOULD). 지정되지 않으면 
objectType은 `Activity`로 간주된다. 그 밖에 유효한 값은 `Agent`, `Group`, `SubStatement`, `StatementRef`이다.
Object의 속성은 objectType에 따라 달라진다.


<a name="2441-when-the-objecttype-is-activity"></a>
##### 2.4.4.1 objectType이 Activity인 경우 (When the ObjectType is Activity)

<a name="details-9"></a>
###### 세부 사항 (Details)

Statement는 Activity를 Statement의 Object로 나타낼 수 있다. 다음 표는 이 경우의 Object 
속성을 나열한다.

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr>
		<td>objectType</td>
		<td>String</td>
		<td>존재하는 경우 반드시 <code>Activity</code>여야 한다(MUST).</td>
		<td>선택</td>
	</tr>
	<tr>
		<td><a href="#activity-id-requirements">id</a></td><td>IRI</td>
		<td>고유한 단일 Activity의 식별자</td>
		<td>필수</td>
	</tr>
	<tr>
		<td><a href="#activity-definition">definition</a></td>
		<td>Object</td>
		<td>메타데이터. <a href="#activity-definition">아래 참조</a></td>
		<td>선택</td>
	</tr>
</table>

서로 다른 두 Activity에 같은 id를 사용할 수 있다면, 이 Activity들에 관한 Statement의 유효성이 
의심받을 수 있다. 따라서 LRS는 동일한 Activity id(에 대한 참조)를 서로 다른 두 Activity에 
속한 것으로 취급할 수 없으며, 그것이 의도된 것이라고 판단되더라도 마찬가지이다. 즉, 
다른 시스템과 충돌이 발생하면 어느 Activity를 의도한 것인지 판단할 수 없다. 


<a name="activity-definition"></a>
###### Activity Definition
아래 표는 Activity Definition Object의 속성을 나열한다.

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr>
		<td>name</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>사람이 읽거나 볼 수 있는 Activity의 이름</td>
		<td>권장</td>
	</tr>
	<tr>
		<td>description</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>Activity에 대한 설명</td>
		<td>권장</td>
	</tr>
	<tr>
		<a name="acttype"></a>
		<td>type</td>
		<td>IRI</td>
		<td>Activity의 유형.</td>
		<td>권장</td>
	</tr>
	<tr>
		<td>moreInfo</td>
		<td>IRL</td>
		<td>Activity에 관해 사람이 읽을 수 있는 정보를 담은 문서로 연결(resolve)된다. 
		이 문서에는 Activity를 실행(launch)하는 방법이 포함될 수 있다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td colspan="4">상호작용 속성. 참조: <a href="#interaction-activities">상호작용 Activity (Interaction Activities)</a></td>
	</tr>
	<tr>
		<td>extensions</td>
		<td>Object</td>
		<td>필요에 따른 기타 속성의 맵(참조: <a href="#41-extensions">Extensions</a>)</td>
		<td>선택</td>
	</tr>
</table>

__참고:__ IRI 프래그먼트(상대 IRL이라고도 함)는 유효한 IRI가 아니다. Verb와 마찬가지로, xAPI를
구현하는 사람은 이미 확립되어 널리 채택된 Activity type을 찾아 사용하는 것을 권장한다.


<a name="activity-id-requirements"></a>
###### Activity id 요구사항 (Activity id Requirements)

* Activity id는 반드시 고유해야 한다(MUST).
* Activity id는 반드시 항상 같은 Activity를 참조해야 한다(MUST).
* Activity id는 생성자가 이 목적으로 사용할 권한이 있는 도메인을 사용해야 한다(SHOULD).
* Activity id는 해당 도메인 내의 모든 Activity id가 고유하게 유지되도록 보장하는 체계에 따라 
생성해야 한다(SHOULD).
* Activity id는 메타데이터 또는 Activity의 IRL을 가리킬 수 있다(MAY).

<a name="lrs-requirements-1"></a>
###### LRS 요구사항 (LRS Requirements)

* LRS는 하나의 Activity id가 여러 작성자 및/또는 조직에 의해 사용되고 있다고 판단되더라도 
그에 대해 어떤 조치도 취해서는 안 된다(MUST NOT).
* LRS는 같은 Activity id에 대한 참조를 서로 다른 Activity에 대한 참조로 취급해서는 안 된다(MUST NOT).
* 저장된 것과 다른 Activity Definition이 담긴 Statement를 수신하면, LRS는
해당 Learning Record Provider에게 정의를 변경할 권한이 있다고 볼지 결정해야 하며(SHOULD), 그 결정이 긍정적이라면
저장된 Activity Definition을 그에 맞게 갱신해야 한다(SHOULD).
* LRS는 새 정의를 수신했을 때 Activity의 정규(canonical) 정의에 작은 수정(예: 철자 수정)을 
가할 수 있다(MAY).
* LRS는 갱신된 정의를 근거로 Activity의 정규 정의에 중대한 변경(예: 정답(correct responses) 변경)을 
가하지 않아야 한다(SHOULD NOT).

<a name="learning-record-provider-requirements-1"></a>
###### Learning Record Provider 요구사항 (Learning Record Provider Requirements)

* Learning Record Provider는 반드시 Activity id가 여러 Activity에 걸쳐 사용되지 않도록 보장해야 한다(MUST).
* Learning Record Provider는 반드시 특정 Activity id에 대해, 같은 Activity id에 대해 이전에 저장된 State 또는 
Statement와 호환되고 일관된 State 또는 Statement만 생성해야 한다(MUST).
* Learning Record Provider는 Activity의 새 버전(즉, 개정판 또는 다른 플랫폼용 버전)이 
호환성을 깨뜨리도록 허용해서는 안 된다(MUST NOT).	

<a name="interaction-activities"></a>
##### 상호작용 Activity (Interaction Activities)

<a name="rationale-3"></a>
###### 근거 (Rationale)

전통적인 이러닝에는 상호작용(interaction) 또는 평가를 위한 구조가 포함되어 왔다. 이러한 관행과
구조를 Experience API에서도 활용할 수 있도록, 이 스펙은 SCORM 2004 4th Edition Data Model에서 차용한
상호작용에 대한 내장 정의를 포함한다. 이 정의들은 상호작용 데이터를 기록하기 위한 간단하고 친숙한 수단을
제공하기 위한 것이다. 1.0.3부터는 SCORM 데이터 모델에 대한 직접 참조를 제거하기 시작했으며, 관련된
요구사항은 이 문서에 직접 포함하였다.

이러한 상호작용 정의는 사용하기 쉬운 대신 그만큼 제한적이다. 더 풍부한 상호작용 정의가 필요한
실천 공동체(Communities of Practice)는 Activity type과 Activity Definition Extension을 활용하여 이를 정의할 것으로 예상된다. 

<a name="details-10"></a>
###### 세부 사항 (Details)

아래 표는 상호작용 Activity의 속성을 나열한다.

<table>
	<tr><th>Property</th><th>Type</th><th>Description</th><th>Required</th></tr>
	<tr>
		<td>interactionType</td>
		<td>String</td>
		<td>상호작용의 유형. 가능한 값은 <code>true-false</code>, <code>choice</code>, <code>fill-in</code>, <code>long-fill-in</code>,
		<code>matching</code>, <code>performance</code>, <code>sequencing</code>, <code>likert</code>, <code>numeric</code>, <code>other</code>이다. </td>
		<td>필수</td>
	</tr>
	<tr>
		<td>correctResponsesPattern</td>
		<td>Array of Strings</td>
		<td>상호작용의 정답을 나타내는 패턴. 이 패턴의 구조는
		interactionType에 따라 달라지며, 아래에서 자세히 설명한다. </td>
		<td>선택</td>
	</tr>
	<tr>
		<td>choices | scale | source | target | steps</td>
		<td>Array of interaction components</td>
		<td>해당 interactionType에 따라 다르다(아래 참조).</td>
		<td>선택</td>
	</tr>
</table>

<a name="interaction-types"></a>
###### 상호작용 유형 (Interaction Types)

아래 표는 각 interactionType이 나타내는 상호작용의 종류를 설명한다. 이 상호작용 유형들은 원래 
SCORM 2004 4th Edition Run-Time Environment의 "cmi.interactions.n.type"에 허용된 상호작용 유형을 
기반으로 한 것이다. 각 상호작용 유형의 정의 예시는 [부록 C](#appendix-c-example-definitions-for-activities-of-type-cmiinteraction)를 참조한다. 

<table>
	<tr><th>interactionType</th><th>Description</th></tr>
	<tr>
		<td>true-false</td>
		<td>가능한 응답이 <code>true</code> 또는 <code>false</code> 두 가지인 상호작용.</td>
	</tr>
	<tr>
		<td>choice</td>
		<td>학습자가 선택할 수 있는 여러 선택지가 있는 상호작용. 
			목록에서 답을 하나만 고를 수 있는 상호작용과
			여러 항목을 고를 수 있는 상호작용을 모두 포함한다.</td>
	</tr>
	<tr>
		<td>fill-in</td>
		<td>학습자가 하나 이상의 문자열 형태로 짧은 응답을 입력해야 하는 
			상호작용. 일반적으로 정답은 단어의 일부, 한 단어 또는 몇 단어로 이루어진다. 
			"짧다"는 것은 정답 패턴과 학습자 응답 문자열이 보통 250자 이하라는 뜻이다.
		</td>
	</tr>
	<tr>
		<td>long-fill-in</td>
		<td>학습자가 긴 문자열 형태로 응답을 입력해야 하는 상호작용.
			"길다"는 것은 정답 패턴과 학습자 응답 문자열이 보통 250자를 넘는다는 뜻이다.
		</td>
	</tr>
	<tr>
		<td>matching</td>
		<td>학습자가 한 집합(source 집합)의 항목을 다른 집합(target 집합)의 항목과 짝짓도록 요구하는 상호작용.
			항목이 정확히 일대일로 짝지어질 필요는 없으며, 하나의 target에 여러 개 또는 0개의 source 항목이 짝지어질 수 있고 그 반대도 마찬가지이다.</td>
	</tr>
	<tr>
		<td>performance</td>
		<td>학습자가 여러 단계로 이루어진 과제를 수행해야 하는 상호작용.</td>
	</tr>
	<tr>
		<td>sequencing</td>
		<td>학습자가 집합 안의 항목들을 순서대로 배열하도록 요구하는 상호작용.</td>
	</tr>
	<tr>
		<td>likert</td>
		<td>학습자가 척도 상의 이산적인 선택지 집합에서 하나를 고르도록 요구하는 상호작용</td>
	</tr>
	<tr>
		<td>numeric</td>
		<td>학습자에게 숫자 응답을 요구하는 모든 상호작용.</td>
	</tr>
	<tr>
		<td>other</td>
		<td>위에 정의된 유형에 해당하지 않는 그 밖의 상호작용.</td>
	</tr>
</table>

<a name="response-patterns"></a>
###### 응답 패턴 (Response Patterns)
아래 표는 각 상호작용 유형별로 "correctResponsesPattern" 속성에 들어가는 문자열의 형식을 정리한 것이다. 
이 형식은 Result Object 안에서 학습자의 응답을 나타내는 데에도 사용된다. 이 형식들은 원래 SCORM 2004 4th Edition 
Run-Time Environment에 정의된 "cmi.interactions.n.correct_responses.n.pattern" 관련 요구사항을 기반으로 한 것이다. 
각 형식의 예시는 [부록 C](#appendix-c-example-definitions-for-activities-of-type-cmiinteraction)를 참조한다. 

<table>
	<tr><th>interactionType</th><th>Format</th></tr>
	<tr>
		<td>true-false</td>
		<td><code>true</code> 또는 <code>false</code> 중 하나</td>
	</tr>
	<tr>
		<td>choice</td>
		<td><code>[,]</code>로 구분된 항목 id 목록. 응답에 항목이 하나뿐이면 구분자를 사용해서는 안 된다(MUST NOT).</td>
	</tr>
	<tr>
		<td>fill-in and long-fill-in</td>
		<td><code>[,]</code>로 구분된 응답 목록. 응답에 항목이 하나뿐이면 구분자를 사용해서는 안 된다(MUST NOT).</td>
	</tr>
	<tr>
		<td>matching</td>
		<td>짝(pair)의 목록으로, 각 짝은 source 항목 id와 그 뒤에 오는 target 항목 id로 구성된다. 
			항목은 여러 개(또는 0개)의 짝에 나타날 수 있다.
			짝 안의 항목은 <code>[.]</code>로 구분한다. 짝과 짝은 <code>[,]</code>로 구분한다.
		</td>
	</tr>
	<tr>
		<td>performance</td>
		<td>
			단계 id와 해당 단계에 대한 응답을 담은 단계(step)의 목록.
			단계 id와 응답은 <code>[.]</code>로 구분한다. 단계와 단계는 <code>[,]</code>로 구분한다.
			응답은 fill-in 상호작용처럼 String이거나 numeric 상호작용처럼 숫자 범위일 수 있다. 
		</td>
	</tr>
	<tr>
		<td>sequencing</td>
		<td><code>[,]</code>로 구분된, 순서가 있는 항목 id 목록.</td>
	</tr>
	<tr>
		<td>likert</td>
		<td>단일 항목 id</td>
	</tr>
	<tr>
		<td>numeric</td>
		<td>최솟값과 최댓값을 <code>[:]</code>로 구분하여 나타낸 숫자 범위. 
			범위에 최댓값이나 최솟값이 없으면 해당 숫자는 생략하되 구분자는
			그대로 사용한다. 예: <code>[:]4</code>는 최댓값이 4이고 최솟값이 없음을 나타낸다. 
			정답 또는 학습자 응답이 범위가 아닌 단일 숫자인 경우, 구분자 없이 그 숫자 하나만
			사용할 수 있다(MAY). 
		</td>
	</tr>
	<tr>
		<td>other</td>
		<td>해당 상호작용 유형에 적절하다면 이 문자열에는 어떤 형식이든 유효하다.</td>
	</tr>
</table>

<a name="correct-responses-pattern"></a>
###### 정답 패턴 (Correct Responses Pattern)

정답 패턴(Correct Responses Pattern)은 응답 패턴의 배열을 담는다. 학습자의 응답이 그 배열에 있는 응답 패턴 중 
**어느 하나라도** 일치하면 정답으로 간주된다. 응답 패턴이 구분자로 나뉜 목록인 경우, 그 목록의 
**모든** 항목이 학습자의 응답과 일치해야만 정답으로 간주된다. 예를 들어 다음과 같은 값을 가진 
정답 패턴을 생각해 보자.

```
"correctResponsesPattern": [
    "foo[,]bar",
    "foo"
]
``` 

이 예에서는 "foo"와 "bar" 둘 다, *또는* "foo" 하나만이 정답인 학습자 응답이다. "bar" 하나만으로는 정답이 아니다.

정답 패턴을 사용하는 경우, 이는 가능한 정답을 빠짐없이 나열한 목록으로 의도된 것이다. 문항의 기준이 
복잡하여 정답을 빠짐없이 나열할 수 없는 경우, Learning Record Provider는 "correctResponsesPattern" 속성을 
사용하지 않는 것이 바람직하다.

Learning Record Consumer는 응답을 정답 패턴과 비교한 결과를 근거로 성공 여부를 추론할 수 없으며, 
정답 패턴이 항상 빠짐없는 목록이라고 가정할 수도 없다. Learning Record Provider는 응답이 정답 패턴과 
일치하지 않더라도 문항을 정답으로 표시할 수 있지만, 예외적인 상황이 아니라면 이는 
바람직하지 않다.

정답 패턴이 빈 배열을 담고 있다면, 이는 정답이 없다는 뜻, 즉 모든 답이 오답이라는 뜻이다. 
어떤 답이든 정답인 경우(예: 설문조사)에는 정답 패턴 속성을 
생략한다. 

<a name="characterstring-parameters"></a>
###### Characterstring 파라미터 (Characterstring parameters)

위에서 설명한 응답 안의 일부 값 앞에는 특정 추가 파라미터를 붙일 수 있다. 이 파라미터들은 원래 
SCORM 2004 4th Edition Run-Time Environment에 정의된 characterstring 구분자를 기반으로 한 것이다. 이 
파라미터는 `{parameter=value}` 형식으로 나타낸다. [부록 C의 long-fill-in 예시](#long-fill-in)를 참조한다. 

Characterstring 파라미터는 LRS가 검증하지 않는다. Statement 데이터를 해석하는 시스템은 유효하지 않은 
characterstring 파라미터와 값을 해석(또는 무시)할 때 자체적으로 최선의 판단을 내릴 수 있다.

다음 파라미터는 나열된 상호작용 유형에서 항목 목록을 나타내는 문자열의 시작 부분에 올 수 있다.
<table>
	<tr><th>Parameter</th><th>Default</th><th>Description</th><th>Value</th><th>Interaction types</th></tr>
	<tr>
		<td>case_matters</td>
		<td>false</td>
		<td>목록 항목의 대소문자를 구분할지 여부.</td>
		<td><code>true</code> 또는 <code>false</code></td>
		<td>fill-in, long-fill-in</td>
	</tr>
	<tr>
		<td>order_matters</td>
		<td>true</td>
		<td>목록 항목의 순서가 중요한지 여부.</td>
		<td><code>true</code> 또는 <code>false</code></td>
		<td>fill-in, long-fill-in, performance</td>
	</tr>
</table>

다음 파라미터는 나열된 상호작용 유형에서 목록의 각 항목 시작 부분에 올 수 있다.
<table>
	<tr><th>Parameter</th><th>Description</th><th>Value</th><th>Interaction types</th></tr>
	<tr>
		<td>lang</td>
		<td>항목에 사용된 언어.</td>
		<td><a href="http://tools.ietf.org/html/rfc5646">RFC 5646 Language Tag</a></td>
		<td>fill-in, long-fill-in, performance (String 응답만 해당)</td>
	</tr>
</table>


<a name="requirements-4"></a>
###### 요구사항 (Requirements)

* Interaction Activity는 반드시 유효한 interactionType을 가져야 한다(MUST).
* Interaction Activity는 Activity type으로 
`http://adlnet.gov/expapi/activities/cmi.interaction`을 가져야 한다(SHOULD).
* LRS는 유효한 interactionType을 수신하면, Interaction Activity에 대해 규정된 대로 나머지 속성을 
검증할 수 있으며(MAY), 나머지 속성이 해당 
Interaction Activity에 유효하지 않으면 `400 Bad Request`를 반환할 수 있다(MAY).
* LRS는 응답 패턴(response pattern)과 관련하여 문자 수 제한을 적용하지 않아야 한다(SHOULD* NOT). 
* LRS는 어떤 interactionType에 대해서도 correctResponsesPattern 배열의 길이를 제한하지 않아야 한다(SHOULD* NOT). 


<a name="interaction-components"></a>
##### 상호작용 컴포넌트 (Interaction Components)

<a name="details-11"></a>
###### 세부 사항 (Details)

상호작용 컴포넌트(interaction component)는 다음과 같이 정의된다.  

<table>
	<tr><th>Property</th><th>Type</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>id</td>
		<td>String</td>
		<td>목록 내에서 해당 상호작용 컴포넌트를 식별한다.</td>
        <td>필수</td>
	<tr>
		<td>description</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>상호작용 컴포넌트에 대한 설명 
			(예: 객관식(multiple-choice) 상호작용에서 특정 선택지의 텍스트)</td>
		<td>선택</td>
	</tr>
</table>


interactionType에 따라 Interaction Activity는 추가 속성을 가질 수 있으며, 각 추가 속성은 
상호작용 컴포넌트의 목록을 담는다. 이러한 추가 속성을 "상호작용 컴포넌트 목록(interaction component list)"이라고 한다. 다음 표는
주어진 interactionType을 가진 Interaction Activity에서 지원되는 상호작용 컴포넌트 목록을 보여준다.

<table>
	<tr><th>interactionType</th><th>지원되는 상호작용 컴포넌트 목록</th><th>설명</th><tr>
	<tr><td>choice, sequencing</td><td>choices</td>
	<td>상호작용에서 선택하거나 순서를 정할 수 있는 옵션의 목록.</td></tr>
	<tr><td>likert</td><td>scale</td>
	<td>리커트 척도(likert scale)상의 옵션 목록.</td></tr>
	<tr><td>matching</td><td>source, target</td>
	<td>서로 짝지어야 할 source와 target의 목록.</td></tr>
	<tr><td>performance</td><td>steps</td>
	<td>수행(performance) 상호작용을 구성하는 요소의 목록.</td></tr>
	<tr><td>true-false, fill-in, long-fill-in, numeric, other</td><td>[지원되는 컴포넌트 목록 없음]</td><td></td></tr>
</table>


<a name="requirements-5"></a>
###### 요구사항 (Requirements)

* 상호작용 컴포넌트 배열 내에서 모든 id 값은 반드시 서로 달라야 한다(MUST).
* 상호작용 컴포넌트의 id 값에는 공백이 없어야 한다(SHOULD NOT).

<a name="examples"></a>
###### 예제 (Examples)

각 cmi.interaction 유형별 Activity Definition 예제는 [부록 C](#appendix-c-example-definitions-for-activities-of-type-cmiinteraction)를 참고한다.


<a name="2442-when-the-object-is-an-agent-or-a-group"></a>
##### 2.4.4.2 "Object"가 Agent 또는 Group인 경우 (When the "Object" is an Agent or a Group)

<a name="requirements-6"></a>
###### 요구사항 (Requirements)

* Agent 또는 Group을 Object로 지정하는 Statement는 반드시 "objectType" 속성을 지정해야 한다(MUST). 

Agent에 대한 자세한 내용은 [Actor](#242-actor)를 참고한다.  


<a name="2443-when-the-object-is-a-statement"></a>
##### 2.4.4.3 "Object"가 Statement인 경우 (When the "Object" is a Statement)

<a name="rationale-4"></a>
###### 근거 (Rationale)

Statement를 Object로 사용하는 방법은 두 가지이다. 첫째, Object는 Statement Reference를 사용하여 
이미 존재하는 Statement의 형태를 취할 수 있다. Statement Reference의 일반적인 사용 사례는 
독립된 이벤트로 추적될 수 있는 경험에 대해 채점하거나 의견을 다는 것이다. 
Statement를 무효화(voiding)하는 특수한 경우에도 Statement Reference를 사용한다.
둘째, Object는 SubStatement를 사용하여 완전히 새로운 Statement가 될 수 있다. 각 유형은 아래에 정의되어 있다.


<a name="statement-references"></a>
##### Statement Reference (Statement References)

<a name="description-8"></a>
###### 설명 (Description)
Statement Reference는 이미 존재하는 다른 Statement를 가리키는 포인터이다.

<a name="requirements-7"></a>
###### 요구사항 (Requirements)

* Statement Reference는 반드시 값이 `StatementRef`인 "objectType" 속성을 지정해야 한다(MUST).
* Statement Reference는 반드시 "id" 속성을 어떤 Statement의 UUID로 설정해야 한다(MUST). 
LRS가 해당 UUID가 실제로 존재하는 Statement와 일치하는지 검증해야 한다는 요구사항은 없다.

아래 표는 Statement Reference Object의 모든 속성을 나열한다.

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>설명</th><th>필수 여부</th></tr>
	<tr><td>objectType</td><td>String</td><td>이 경우 반드시 <code>StatementRef</code>여야 한다(MUST).</td><td>필수</td></tr>
	<tr><td>id</td><td>UUID</td><td>Statement의 UUID. 
	</td><td>필수</td></tr>
</table>

<a name="example-4"></a>
###### 예제 (Example)

어떤 Statement가 id `8f87ccde-bb56-4c2e-ab83-44982ef22df0`으로 이미 저장되어 있다고 가정할 때, 다음 예제는 
새로운 Statement를 사용하여 원래 Statement에 의견(comment)을 다는 방법을 보여준다.  

```
{
	"actor" : { 
		"objectType": "Agent", 
		"mbox":"mailto:test@example.com" 
	},
	"verb" : { 
		"id":"http://example.com/commented", 
		"display": {
			"en-US":"commented"
		} 
	},
	"object" : {
		"objectType":"StatementRef",
		"id":"8f87ccde-bb56-4c2e-ab83-44982ef22df0"
	},
	"result" : { 
		"response" : "Wow, nice work!" 
	}
}
``` 


<a name="substatements"></a>
##### SubStatement (SubStatements)

<a name="description-9"></a>
###### 설명 (Description)
SubStatement는 이를 포함하는 Statement의 일부로 들어간다는 점에서 StatementRef와 비슷하지만, StatementRef와 달리 
이미 발생한 이벤트를 나타내지 않는다. 예를 들어, 잠재적인 미래 Statement에 대한 예측(predication)이나, 
교사가 학생을 평가할 때 살펴본 행동(학생이 실제로 그 행동을 했다는 것을 나타내지 않고)을 
기술하는 데 사용할 수 있다. 

<a name="requirements-8"></a>
###### 요구사항 (Requirements)

* SubStatement는 반드시 값이 `SubStatement`인 "objectType" 속성을 지정해야 한다(MUST).
* SubStatement는 다른 SubStatement 요구사항에 더하여 반드시 Statement로서도 검증되어야 한다(MUST).
* SubStatement는 "id", "stored", "version", "authority" 속성을 가져서는 안 된다(MUST NOT).
* SubStatement는 자기 안에 또 다른 SubStatement를 포함해서는 안 된다(MUST NOT). 즉, 중첩될 수 없다.

<a name="example-5"></a>
###### 예제 (Example)

SubStatement의 흥미로운 활용 중 하나는 의도(intention)를 나타내는 Statement를 만드는 것이다. 예를 들어, SubStatement를 사용하면 
어떤 행동을 하기로 계획했음을 나타내기 위해 `"<I> <planned> (<I> <did> <this>)"` 형태의 Statement를 만들 수 있다. 
다음의 구체적인 예제는 논리적으로 "나는 'Some Awesome Website'를 방문할 계획을 세웠다"를 나타낸다. 
 


```
{
	"actor": {
		"objectType": "Agent", 
		"mbox":"mailto:test@example.com" 
	},
	"verb" : { 
		"id":"http://example.com/planned", 
		"display":{
			"en-US":"planned"
		} 
	},
	"object": {
		"objectType": "SubStatement",
		"actor" : {
			"objectType": "Agent", 
			"mbox":"mailto:test@example.com" 
		},
		"verb" : { 
			"id":"http://example.com/visited", 
			"display":{
				"en-US":"will visit"
			} 
		},
		"object": {
			"objectType": "Activity",
			"id":"http://example.com/website",
			"definition": { 
				"name" : {
					"en-US":"Some Awesome Website"
				}
			}
		}
	}
}
```


<a name="245-result"></a>
#### 2.4.5 Result

<a name="description-10"></a>
###### 설명 (Description)

이 속성이 포함된 Statement와 관련된, 측정된 결과(outcome)를 나타내는 선택적 속성이다.

<a name="details-12"></a>
###### 세부 사항 (Details)

다음 표는 Result Object의 속성을 담고 있다.

<table border="1">
<tr><th>Property</th><th>Type</th><th>설명</th><th>필수 여부</th></tr>
<tr>
	<td>score</td>
	<td>Object</td>
	<td>경험의 성공 또는 품질과 관련된 Agent의 점수. 
	<a href ="#2451-score">참고: Score</a></td>
	<td>선택</td>
</tr>
<tr>
	<td>success</td>
	<td>Boolean</td>
	<td>Activity에 대한 시도가 성공했는지 여부를 나타낸다.</td>
	<td>선택</td>
</tr>
<tr>
	<td>completion</td>
	<td>Boolean</td>
	<td>Activity가 완료되었는지 여부를 나타낸다.</td>
	<td>선택</td>
</tr>
<tr>
	<td>response</td>
	<td>String</td>
	<td>해당 Activity에 맞게 형식화된 응답.</td>
	<td>선택</td>
</tr>
<tr>
	<td>duration</td>
	<td><a href="#46-iso-8601-durations">Duration</a></td>
	<td>Statement가 발생한 기간.</td>
	<td>선택</td>
</tr>
<tr>
	<td>extensions</td>
	<td>Object</td>
	<td>필요에 따라 추가하는 기타 속성의 맵.
	<a href="#41-extensions">참고: Extensions</a></td>
	<td>선택</td>
</tr>
</table>


<a name="2451-score"></a>
##### 2.4.5.1 Score

<a name="description-11"></a>
###### 설명 (Description)
Agent가 채점된 Activity에서 달성한 결과를 나타내는 선택적 속성이다.

<a name="details-13"></a>
###### 세부 사항 (Details)

아래 표는 Score Object를 정의한다. 

<table border ="1">
	<tr><th>Property</th><th>Type</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>scaled</td>
		<td>-1 이상 1 이하의 십진수(Decimal number)</td>
		<td>스케일링(scaling) 및/또는 정규화(normalization)를 거쳐 조정된, 경험과 관련된 점수. 
		</td>
		<td>권장</td>
	</tr>
	<tr>
		<td>raw</td>
		<td>min 이상 max 이하의 십진수(Decimal number) (min/max가 있는 경우. 없으면 제한 없음)</td>
		<td>Statement가 기술하는 경험에서 Actor가 얻은 점수. 이 값은 
		어떠한 스케일링이나 정규화로도 조정되지 않는다.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>min</td>
		<td>max보다 작은 십진수(Decimal number) (max가 있는 경우)</td>
		<td>Statement가 기술하는 경험에서 가능한 최저 점수.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>max</td>
		<td>min보다 큰 십진수(Decimal number) (min이 있는 경우)</td>
		<td>Statement가 기술하는 경험에서 가능한 최고 점수.</td>
		<td>선택</td>
	</tr>
</table>

Score Object의 속성은 SCORM 2004 4th Edition에 정의된 `cmi.score`의 대응 속성을 기반으로 한다. 
서로 다른 실천 공동체(Community of Practice) 내의 Learning Record Provider가 스케일링과 정규화를 서로 다르게 
적용할 수 있으므로, "scaled"와 "raw" 속성이 반드시 직접적으로 연관되는 것은 아니다. 스케일링과 정규화는 
이 스펙의 범위를 벗어난다.

<a name="requirements-9"></a>
###### 요구사항 (Requirements)

* 논리적인 백분율 기반 점수를 알고 있다면 Score Object는 "scaled"를 포함해야 한다(SHOULD).
* Score Object는 진행도(progress)나 완료(completion)와 관련된 점수에 사용하지 않아야 한다(SHOULD NOT). 대신 
(가급적 기존에 확립된 실천 공동체(Community of Practice)의) extension 사용을 고려한다.


<a name="246-context"></a>
#### 2.4.6 Context

<a name="description-12"></a>
###### 설명 (Description)
Statement에 맥락 정보를 추가할 수 있는 공간을 제공하는 선택적 속성이다. 모든 "context" 속성은 선택 사항이다.

<a name="rationale-5"></a>
###### 근거 (Rationale)
"context" 속성은 Statement에 맥락 정보를 추가할 수 있는 공간을 제공한다. 예를 들어 경험의 강사(instructor), 
해당 경험이 팀 기반 Activity의 일부로 이루어졌는지 여부, 또는 경험이 더 넓은 활동 안에서 어떻게 
자리 잡는지와 같은 정보를 저장할 수 있다.

<a name="details-14"></a>
###### 세부 사항 (Details)

다음 표는 Context Object의 속성을 담고 있다.

<table border="1">
<tr><th>Property</th><th>Type</th><th>설명</th><th>필수 여부</th></tr>
<tr>
	<td>registration</td>
	<td>UUID</td>
	<td>Statement가 연관된 registration(등록).</td>
	<td>선택</td>
</tr>
<tr>
	<td>instructor</td>
	<td>Agent (Group일 수 있음(MAY))</td>
	<td>Statement의 Actor로 포함되지 않은 경우, Statement와 관련된 강사.</td>
	<td>선택</td>
</tr>
<tr>
	<td>team</td>
	<td>Group</td>
	<td>Statement의 Actor로 포함되지 않은 경우, 이 Statement와 관련된 팀.</td>
	<td>선택</td>
</tr>
<tr>
	<td>contextActivities</td>
	<td>contextActivities Object</td>
	<td>이 Statement와 관련된 학습 활동 맥락 유형의 맵.
	유효한 맥락 유형은 <code>parent</code>, <code>"grouping"</code>, <code>"category"</code>, <code>"other"</code>이다.</td>
	<td>선택</td>
</tr>
<tr>
	<td>revision</td>
	<td>String</td>
	<td>이 Statement와 연관된 학습 활동의 개정판(revision). 형식은 자유롭다.
	<td>선택</td>
</tr>
<tr>
	<td>platform</td>
	<td>String</td>
	<td>이 학습 활동을 경험하는 데 사용된 플랫폼. </td>
	<td>선택</td>
</tr>
<tr>
	<td>language</td>
	<td>String (<a href="http://tools.ietf.org/html/rfc5646">RFC 5646</a>에 정의된 형식)</td>
	<td>해당되고 알려진 경우, 이 Statement에 기록된 경험이 
	(주로) 이루어진 언어를 나타내는 코드.
	</td>
	<td>선택</td>
</tr>
<tr>
	<td>statement</td>
	<td><a href="#statement-references">Statement Reference</a></td>
	<td>이 Statement의 맥락으로 간주할 다른 Statement. </td>
	<td>선택</td>
</tr>
<tr>
	<td>extensions</td>
	<td>Object</td>
	<td>이 Statement와 관련된 기타 도메인별 맥락의 맵. 예를 들어 
	비행 시뮬레이터에서는 고도, 대기 속도, 바람, 자세, GPS 좌표가 모두 
	관련될 수 있다 (<a href="#41-extensions">Extensions 참고</a>)</td>
	<td>선택</td>
</tr>

</table>

<a name="requirements-10"></a>
###### 요구사항 (Requirements)

* "revision" 속성은 반드시 Statement의 Object가 Activity인 경우에만 사용해야 한다(MUST).
* "platform" 속성은 반드시 Statement의 Object가 Activity인 경우에만 사용해야 한다(MUST).
* "language" 속성은 해당되지 않거나 알 수 없는 경우 사용해서는 안 된다(MUST NOT).
* "revision" 속성은 (철자 오류 같은) 사소한 문제의 수정을 추적하는 데 사용해야 한다(SHOULD).
* Activity의 학습 목표, 교수법(pedagogy), 자산(asset)에 큰 변경이 있는 경우에는 "revision" 속성을 
사용하지 않아야 한다(SHOULD NOT). (대신 새로운 Activity id를 사용한다.)

__참고:__ revision은 xAPI의 범위 내에서 동작상의 의미를 갖지 않는다. 단지 (예: 데이터를 해석하고 표시하는 데)
활용할 수 있도록 저장될 뿐이다.


<a name="2461-registration-property"></a>
##### 2.4.6.1 Registration 속성 (Registration Property)

<a name="rationaledetails"></a>
###### 근거/세부 사항 (Rationale/Details)

LRS가 LMS의 필수 구성 요소인 경우, 해당 LMS는 registration(등록) 개념을 지원할 가능성이 높다. 
Experience API는 registration 개념을 더 폭넓게 적용한다. registration은 하나의 시도(attempt)나 세션(session)으로 
간주될 수도 있고, 여러 Activity에 걸쳐 있을 수도 있다. Activity를 완료한다고 해서 registration이 
끝나는 것으로 기대되지는 않는다. 또한 registration이 반드시 단일 Agent에 국한되는 것도 아니다.

Registration은 State Resource에 (예: 북마크를 위해) Document를 저장할 때에도 사용된다. 
일반적으로 동일한 학습 경험과 관련된 Statement Resource와 State Resource에 대한 요청에는 
같은 registration을 사용하여, 그 경험에 대해 기록된 모든 데이터가 일관되도록 한다. 


<a name="2462-contextactivities-property"></a>
##### 2.4.6.2 ContextActivities 속성 (ContextActivities Property)

<a name="description-13"></a>
###### 설명 (Description)

이 Statement와 관련된 학습 활동 맥락 유형의 맵이다.

<a name="rationale-6"></a>
###### 근거 (Rationale)

많은 Statement는 초점이 되는 하나의 (Object) Activity만 다루는 것이 아니라, 맥락상 관련된 다른 
Activity와도 연관된다. "contextActivities" 속성은 이러한 관련 Activity를 구조화된 방식으로 표현할 수 있게 해 준다.

<a name="details-15"></a>
###### 세부 사항 (Details)

유효한 맥락 유형은 네 가지이다. 하나의 Statement에서 이들을 모두, 일부만 사용하거나 전혀 사용하지 않을 수 있다(MAY).

* __Parent__: Statement의 Object인 Activity와 직접적인 관계를 갖는 Activity이다. 
거의 모든 경우 합당한 parent는 하나뿐이거나 없으며, 여러 개인 경우는 드물다. 예: 퀴즈 문항에 대한 Statement는
그 퀴즈를 parent Activity로 갖는다.
 
* __Grouping__: Statement의 Object인 Activity와 간접적인 관계를 갖는 Activity이다. 
예: 어떤 자격 과정(qualification)의 일부인 코스(course)가 있다. 이 코스에는 여러 수업(class)이 있다. 코스는 수업에 대해 
parent로 관련되고, 자격 과정은 수업에 대해 grouping으로 관련된다.

* __Category__: Statement를 분류하는 데 사용되는 Activity이다. "태그(Tags)"와 같은 의미로 볼 수 있다. 
Category는 다른 분류뿐만 아니라 xAPI 동작의 profile을 나타내는 데 사용해야 한다(SHOULD). 예: Anna가 
생물학 시험을 치르고, 해당 Statement는 cmi5 profile을 사용하여 추적된다. Statement의 Activity는 시험을 가리키고, 
category는 cmi5 profile이다.

* __Other__: 다른 속성 중 어디에도 맞지 않는 contextActivity이다. 예: Anna가 
생물학 시험을 위해 교과서로 공부한다. Statement의 Activity는 교과서를 가리키고, 시험은 
`other` 유형의 contextActivity이다.

0.95 Statement가 1.0.0과 호환되도록, 단일 Activity Object도 값으로 허용된다.

__참고:__ 이 절의 값들은 Statement Object가 가진 모든 관계를 표현하기 위한 것이 아니다. 대신 
특정 Statement에 적합한 관계를 표현하기 위한 것이다(다만 이를 판단할 때 Object의 성격이 중요한 경우가 많다). 
예를 들어, 시험에 관한 Statement에서 그 시험이 속한 코스를 "parent"로 포함하는 것은 적절하지만, 
그 코스가 속할 수 있는 모든 학위 프로그램을 grouping 값에 포함하는 것은 적절하지 않다.

<a name="requirements-11"></a>
###### 요구사항 (Requirements)
* contextActivities Object의 모든 키는 반드시 parent, grouping, category, other 중 하나여야 한다(MUST).
* contextActivities Object의 모든 값은 반드시 단일 Activity Object이거나 Activity Object의 배열이어야 한다(MUST).
* LRS는 contextActivities Object의 모든 값을, 단일 Activity Object로 들어왔더라도 반드시 배열로 반환해야 한다(MUST).
* LRS는 단일 Activity Object를 반드시 동일한 Activity를 담은 길이 1의 배열로 반환해야 한다(MUST).
* Learning Record Provider는 contextActivities Object의 모든 값이 단일 Activity Object가 아닌 
Activity Object의 배열이 되도록 해야 한다(SHOULD).

<a name="example-6"></a>
###### 예제 (Example)

다음과 같은 계층 구조를 생각해 보자. "문항 1~6(Questions 1 to 6)"은
"시험 1(Test 1)"의 일부이며, "시험 1"은 다시 "대수학 1(Algebra 1)" 코스에 속한다.
여섯 개의 문항은 "Test 1"을 parent로 선언함으로써 해당 시험의 일부로
등록된다. 또한 계층 구조를 완전히 반영하기 위해 "Algebra 1"에 관한 다른 Statement와
함께 그룹화된다. 이는 Statement의 Object가 Activity가 아니라 Agent일 때
특히 유용하다.
"Andrew가 Algebra I 맥락에서 Ben을 멘토링했다(Andrew mentored Ben with context Algebra I)".

```
{
    "parent" : [
        {
            "id" : "http://example.adlnet.gov/xapi/example/test1"
        }
    ],
    "grouping" : [
        {
            "id" : "http://example.adlnet.gov/xapi/example/Algebra1"
        }
    ]
}
```


<a name="247-timestamp"></a>
#### 2.4.7 Timestamp

<a name="description-14"></a>
###### 설명 (Description)

경험이 발생한 시각이다.

<a name="details-16"></a>
###### 세부 사항 (Details)

"timestamp" 속성은 [Timestamp](#45-iso-8601-timestamps) 타입이다. ISO 8601의 일반 형식에 따라 형식화되며, 
이 Statement에 기술된 이벤트가 발생한 시각에 해당한다. Statement를 LRS에 제출할 때 이 속성이 포함되지 
않았다면, LRS는 [Stored](#248-stored)에 사용할 값과 동일한 값으로 이를 채운다.

Statement의 "timestamp 속성"은 ["stored" 속성](#248-stored)(Statement가 저장된 시각)과 
다를 수 있다. 즉, 경험이 발생한 시점과 LRS가 해당 Statement를 수신한 시점 사이에는 
지연이 있을 수 있다. 

경험이 일정 기간에 걸쳐 일어나는 경우, "timestamp" 속성은 경험의 시작, 끝 또는 경험 중의 어느 시점이든 
나타낼 수 있다. 실천 공동체(Community of Practice)가 서로 다른 경험에 대해 timestamp를 기록할 적절한 시점을 
정의할 것으로 기대된다. 예를 들어, 식당에서 식사한 경험을 기록할 때는 경험의 시작 시각을 timestamp로 
기록하는 것이 가장 적절할 수 있고, 자격 과정을 이수한 경험을 기록할 때는 경험의 종료 시각을 
timestamp로 기록하는 것이 가장 적절할 수 있다.
이 예시는 설명을 위한 것일 뿐이며 규범적인 의도는 없다.

<a name="requirements-12"></a>
###### 요구사항 (Requirements)

* Timestamp 데이터 타입과 관련된 요구사항은 [4.5절 ISO 8601 Timestamp](#45-iso-8601-timestamps)를 참고한다.
* "timestamp" 속성이 제공되지 않은 경우, LRS는 이를 ["stored" 속성](#248-stored)의 
값으로 설정해야 한다(SHOULD*).
* "timestamp" 속성은 경험의 시작이나 끝에 국한되지 않고 경험 중의 어느 시점이든 
나타낼 수 있다(MAY). 
* Learning Record Provider는 Statement의 "timestamp" 속성에 미래 시각을 사용해서는 안 된다(MUST NOT).
* SubStatement는 미래 시각인 "timestamp" 속성을 가질 수 있다(MAY).
* 시계 오차로 인한 문제를 방지하기 위해, LRS는 timestamp가 현재 시각보다 크다는 이유로 이를 
거부하지 않아야 한다(SHOULD* NOT).


<a name="248-stored"></a>
#### 2.4.8 Stored

<a name="description-15"></a>
###### 설명 (Description)

LRS가 Statement를 저장한 시각이다. 이는 LRS가 Statement를 수신한 시점부터 저장소에 기록하는 시점 사이의 
어느 시각이든 될 수 있다. 

<a name="details-17"></a>
###### 세부 사항 (Details)

"stored" 속성은 [Timestamp](#45-iso-8601-timestamps) 타입이다. "stored" 속성은 Statement가 저장된 실제 시각이다. 

<a name="requirements-13"></a>
###### 요구사항 (Requirements)

* Timestamp 데이터 타입과 관련된 요구사항은 아래의 [ISO 8601 Timestamp](#45-iso-8601-timestamps)를 참고한다.
* "stored" 속성은 반드시 LRS가 설정해야 한다(MUST). LRS는 수신한 Statement의 "stored" 속성에 이미 들어 있는 
값을 검증한 뒤(SHOULD) 반드시 덮어써야 한다(MUST).
* "stored" 속성은 현재 또는 과거 시각이어야 한다(SHOULD).


<a name="249-authority"></a>
#### 2.4.9 Authority

<a name="description-16"></a>
###### 설명 (Description)

authority 속성은 누가 또는 무엇이 이 Statement가 참임을 주장(assert)하는지에 대한 정보를 제공한다. 

<a name="details-18"></a>
###### 세부 사항 (Details)

주장하는 authority는 인증된 사용자 또는 어떤 시스템이나 애플리케이션을 나타낸다.

<a name="requirements-14"></a>
###### 요구사항 (Requirements)

* Authority는 반드시 Agent여야 한다(MUST). 단, 3-legged OAuth에서는 반드시 두 개의 Agent로 구성된 Group이어야 한다(MUST). 
두 Agent는 애플리케이션과 사용자를 함께 나타낸다.
* 사용자가 (HTTP Basic Authentication을 사용하여) 직접 연결하거나 Group의 일부로 포함된 경우, 
LRS는 반드시 해당 사용자를 Agent로서 authority 전체로 포함해야 한다(MUST). 
* LRS는 저장되는 모든 Statement가 authority를 갖도록 반드시 보장해야 한다(MUST).
* LRS는 Statement를 전송하는 데 사용된 자격 증명(credential)에 근거하여, 
저장하는 모든 Statement의 authority를 덮어써야 한다(SHOULD).
* LRS는 제출된 authority를 변경하지 않고 그대로 둘 수 있지만(MAY), 강한 신뢰 관계가 
확립된 경우에만 극도로 주의하여 그렇게 해야 한다(SHOULD).
* 사용자가 (HTTP Basic Authentication을 사용하여) 직접 연결하거나 3-legged OAuth의 일부로 연결한 경우, 
LRS는 적법한 식별 속성 중 어느 것으로든 사용자를 식별할 수 있다(MAY). 

<a name="oauth-credentials-as-authority"></a>
##### Authority로서의 OAuth 자격 증명 (OAuth Credentials as Authority)

<a name="description-17"></a>
###### 설명 (Description)

이것은 OAuth 사용을 위한 워크플로이다. 2-legged와 3-legged OAuth 모두 지원된다.

<a name="details-19"></a>
###### 세부 사항 (Details)

이 워크플로는 Statement가 검증된 OAuth 연결을 통해 저장되고, LRS가 Statement의 
authority 속성을 생성하거나 수정한다고 가정한다.

3-legged OAuth 워크플로에서는 인증에 OAuth consumer와 OAuth 서비스 제공자(service provider)의 
사용자가 모두 관여한다. 예를 들어, 사용자의 Facebook 계정에서 인가된 Twitter 플러그인이 보내는 
요청에는 Client 애플리케이션으로서의 Twitter나 사용자 개인에게만 국한된 것이 아니라, 
둘의 고유한 조합에 특화된 자격 증명이 포함된다.

<a name="requirements-15"></a>
###### 요구사항 (Requirements)

* authority는 반드시 OAuth consumer를 나타내는 Agent Object를, 단독으로 또는 
3-legged OAuth의 경우 Group의 일부로 포함해야 한다(MUST).
* OAuth consumer를 나타내는 Agent는 반드시 account로 식별되어야 한다(MUST).
* OAuth consumer를 나타내는 Agent는 반드시 consumer key를 account의 
"name" 속성 값으로 사용해야 한다(MUST).
* OAuth consumer를 나타내는 Agent가 등록된 애플리케이션이라면, 반드시 token request 엔드포인트를 
account의 "homePage" 속성 값으로 사용해야 한다(MUST).
* OAuth consumer를 나타내는 Agent가 등록되지 않은 애플리케이션이라면, 반드시 temporary 
credentials 엔드포인트를 account의 "homePage" 속성 값으로 사용해야 한다(MUST).
* account name이 등록되지 않은 애플리케이션과 동일한 출처에서 온 경우, LRS는 authority 중 
애플리케이션 부분을 신뢰해서는 안 된다(MUST NOT). (여러 등록되지 않은 애플리케이션이 동일한 consumer key를 선택할 수 있다. 
그 결과, 이러한 임시 자격 증명과 account name의 조합을 일관되게 검증할 방법이 없다.) 
* 등록되지 않은 각 consumer는 고유한 consumer key를 사용해야 한다(SHOULD).

<a name="example-7"></a>
###### 예시 (Example)

OAuth 소비자(consumer)와 사용자의 쌍.

```
"authority": {
	"objectType" : "Group",
	"member": [
		{
			"account": {
				"homePage":"http://example.com/xAPI/OAuth/Token",
				"name":"oauth_consumer_x75db"
			}
		},
		{ 
			"mbox":"mailto:bob@example.com" 
		}
	]
}
```


<a name="2410-version"></a>
#### 2.4.10 Version
<a name="description-18"></a>
###### 설명 (Description)

Statement의 버전 정보는 Learning Record Consumer가 상황을 파악하는 데 도움을 준다. Statement
데이터 모델은 모든 1.0.x 버전에 걸쳐 일관성이 보장되므로, 이러한 LRS들 사이의 데이터 흐름을
지원하기 위해 LRS는 수용하는 Statement 버전에 대해 어느 정도의 유연성을 갖는다.

<a name="requirements-16"></a>
###### 요구사항 (Requirements)

* Version은 반드시 [버전 관리(Versioning)](./xAPI-Communication.md#33-versioning)에서 API 버전 헤더에 대해 정한 형식을 따라야 한다(MUST).

<a name="lrs-requirements-2"></a>
###### LRS 요구사항 (LRS Requirements)

* LRS는 version이 `1.0.`으로 시작하는 모든 Statement를, 그 밖의 검증을 통과한다면 반드시 수락해야 한다(MUST).
* LRS는 `1.0.`으로 시작하지 않는 version이 지정된 모든 Statement를 반드시 거부해야 한다(MUST).
* LRS가 반환하는 Statement는 반드시 수락될 때의 version을 유지해야 한다(MUST). Statement에
version이 없으면 version은 반드시 `1.0.0`으로 설정되어야 한다(MUST).


<a name="learning-record-provider-requirements-2"></a>
###### Learning Record Provider 요구사항 (Learning Record Provider Requirements)

* Learning Record Provider가 Statement version을 설정한다면, 반드시 `1.0.0`으로 설정해야 한다(MUST).
* Learning Record Provider는 Statement version을 설정하지 않아야 한다(SHOULD NOT).

__참고:__ "version" 속성이 최신 패치 버전이 아니라 `1.0.0` 값을 담도록 한 요구사항은 의도적인 것이다.
1.0.x의 어느 버전의 Statement든 1.0.0 데이터 모델을 따르기 때문이다. 실제로 하나의 Statement가 시간이 지나면서
여러 요청에 포함될 수 있으며, 각 요청은 명세의 서로 다른 패치 버전을 따를 수 있다. 따르고 있는 명세의
패치 버전은 각 요청에서 사용되는 ["X-Experience-API-Version" 헤더](./xAPI-Communication.md#33-versioning)로 확인할 수 있다. 

<a name="2411-attachments"></a>
#### 2.4.11 Attachments

<a name="rationale-7"></a>
###### 근거 (Rationale)

경우에 따라 Attachment는 논리적으로 학습 기록(Learning Record)의 중요한 부분이 된다. 에세이나 동영상 등이 그 예이다. 
이러한 Attachment의 또 다른 예로는 어떤 경험의 결과로 수여된 증명서(의 이미지)가 있다. 
이러한 Attachment를 LRS에 저장하고 LRS에서 조회할 수 있는 방법이 있으면 유용하다. 

<a name="details-20"></a>
###### 세부 사항 (Details)

아래 표는 Attachment Object의 모든 속성을 나열한다.

<table>
	<tr><th>속성</th><th>타입</th><th>설명</th><th>필수 여부</th><th>대응하는 요청 파라미터</th></tr>
	<tr>
		<td><a name="attachmentUsage"></a>usageType</td>
		<td>IRI</td>
		<td>이 Attachment의 용도를 식별한다. 예를 들어, Attachment의 예상되는 사용 사례 중 하나는
		"완료 증명서(completion certificate)"를 포함하는 것이다. 이 용도에 대응하는 IRI를
		반드시 새로 만들어(coin) 완료 증명서 Attachment에 사용해야 한다(MUST).</td>
		<td>필수</td>
		<td></td>
	</tr>
	<tr>
		<td>display</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>이 Attachment의 표시 이름(제목).</td>
		<td>필수</td>
		<td></td>
	</tr>
	<tr>
		<td>description</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>Attachment에 대한 설명.</td>
		<td>선택</td>
		<td></td>
	</tr>
	<tr>
		<td>contentType</td>
		<td><a href="https://www.ietf.org/rfc/rfc2046.txt?number=2046">Internet Media Type</a></td>
		<td>Attachment의 콘텐츠 타입.</td>
		<td>필수</td>
		<td>Content-Type</td>
	</tr>
	<tr>
		<td>length</td>
		<td>Integer</td>
		<td>Attachment 데이터의 길이(옥텟 단위).</td>
		<td>필수</td>
		<td>Content-Length</td>
	</tr>
	<tr>
		<td>sha2</td>
		<td>String</td>
		<td>Attachment 데이터의 SHA-2 해시. <br/>
		fileURL이 함께 지정된 경우에도 이 속성은 항상 필수이다. 
		</td>
		<td>필수</td>
		<td>X-Experience-API-Hash</td>
	</tr>
	<tr>
		<td>fileUrl</td>
		<td>IRL</td>
		<td>Attachment 데이터를 가져올 수 있는, 또는 과거에 가져올 수 있었던 
		IRL. </td>
        <td>선택</td>
		<td></td>
	</tr>
</table>

SubStatement에 Attachment를 포함하려는 경우에는, 해당 Attachment를 Statement의 Attachment 객체에 포함하고 
페이로드도 Statement에서 평소 하듯이 포함할 것을 강력히 권장한다.

<a name="25-retrieval-of-statements"></a>
### 2.5 Statement 조회 (Retrieval of Statements)

<a name="description-19"></a>
###### 설명 (Description)

Statement 리소스(Statement Resource)에 쿼리를 수행하여 Statement 모음을 조회할 수 있다. 
자세한 내용은 [Statement Resource](./xAPI-Communication.md#21-statement-resource)를 참고한다. 

<a name="details-21"></a>
###### 세부 사항 (Details)

다음 표는 Statement 리소스에 대한 쿼리 결과의 데이터 구조를 보여 준다.
<table>
	<tr><th>속성</th><th>타입</th><th>설명</th><th>필수 여부</th></tr>
	<tr><td>statements</td><td>Array of Statements</td>
		<td>Statement 목록. 반환된 목록이 (페이지네이션으로 인해) 제한되었고 
			결과가 더 있는 경우, 나머지 결과는 이 Statement 결과 Object의 
			"more" 속성이 제공하는 IRL에 위치한 컨테이너 안의 
			"statements" 속성에 있다.
			일치하는 Statement가 없으면 이 속성은 빈 배열을 담는다.
		</td>
		<td>필수</td>
	</tr>
	<tr><td>more</td><td>IRL</td>
		<td>더 많은 결과를 가져오는 데 사용할 수 있는 상대 IRL로, 전체 경로와 
			선택적으로 쿼리 문자열을 포함하지만 scheme, host, port는 제외한다. 
			더 가져올 결과가 없으면 빈 문자열이다.
		</td>
		<td>반환된 목록이 제한된 경우 필수, 그 외에는 선택.</td>
	</tr>
</table>

<a name="requirements-17"></a>
###### 요구사항 (Requirements)

* "more" 속성에서 얻은 IRL은 LRS가 반환한 후 최소 24시간 동안 반드시 사용 가능해야 한다(MUST). 
* LRS는 IRL과 관련 쿼리 데이터를 저장할 필요가 없도록, 쿼리를 계속하는 데 필요한 모든 정보를 
"more" 속성 IRL 안에 포함할 수 있다(MAY).
* LRS는 "more" 속성에 지나치게 긴 IRL을 생성하지 않아야 한다(SHOULD NOT).
* LRS는 "more" 속성에서 얻은 IRL에 접근하는 시점에 쿼리를 다시 실행할 수 있다(MAY). 이 경우 조회되는 배치는 
원래 쿼리가 실행된 시점에 LRS에 존재했다면 그 배치에 포함되었을 Statement를 포함하고, 그 이후 무효화된 Statement는 
그 배치에서 제외한다. 
* 또는 LRS는 "more" 속성에서 반환할 Statement 목록을 캐시하여, 반환되는 Statement 배치가 원래 쿼리가 
실행되었을 때 반환되었을 Statement와 일치하도록 할 수 있다(MAY). 
* 이 방법을 사용하는 경우, LRS는 캐시된 Statement 목록에서 무효화된 Statement를 제거할 수 있다(MAY). 
* Learning Record Consumer는 "more" 속성에서 반환된 IRL로부터 어떤 의미도 해석하려 하지 
않아야 한다(SHOULD NOT).

<a name="26-signed-statements"></a>
### 2.6 서명된 Statement (Signed Statements)

<a name="description-20"></a>
##### 설명 (Description)

Statement는 [디지털 서명(digital signature)](https://en.wikipedia.org/wiki/Digital_signature)을 포함하여 
Statement의 진위성(authenticity)과 무결성(integrity)에 대한 강력하고 지속적인 증거를 제공할 수 있다.

<a name="rationale-8"></a>
##### 근거 (Rationale)

일부 Statement는 규제상 또는 법적 의미를 가지거나, 그 밖의 이유로 진위성과 무결성에 대한 강력하고
지속적인 증거를 필요로 한다. 이러한 Statement를 처음 기록된 환경을 신뢰하지 않고, 혹은 그 환경에
접근하지 않고도 검증해야 할 수 있다. 디지털 서명을 사용하면 제3자가 이러한 Statement를 검증할 수 있다.

<a name="details-22"></a>
##### 세부 사항 (Details)

서명된 Statement는 JSON 웹 서명(JSON web signature, JWS)을 Attachment로 포함한다. 이를 통해
Statement의 원래 직렬화(serialization)를 서명과 함께 포함할 수 있다.
상호운용성을 위해 "RSA + SHA" 계열의 JWS 알고리즘이 선택되었으며,
서명자를 식별할 수 있도록(discoverability) X.509 인증서를 사용해야 한다(SHOULD).

<a name="signature-requirements"></a>
##### 서명 요구사항 (Signature Requirements)
* 서명된 Statement는 다음에 정의된 JSON 웹 서명(JWS)을:
http://tools.ietf.org/html/rfc7515, usageType이 `http://adlnet.gov/expapi/attachments/signature`이고
contentType이 `application/octet-stream`인 Attachment로 반드시 포함해야 한다(MUST).
* JSON 웹 서명을 생성할 때는 JWS Compact Serialization을 사용해야 한다(SHOULD*). JWS JSON Serialization의 
사용은 강력히 권장되지 않으며, 다른 시스템과 상호운용되지 않을 가능성이 높고, 이 명세의 향후 버전에서는 
금지될 것이다. 
* JWS 서명은 반드시 서명이 추가되기 전 완전한 Statement의 유효한 JSON 직렬화를 
페이로드로 가져야 한다(MUST).
* JWS 서명은 반드시 "RS256", "RS384", "RS512" 중 하나의 알고리즘을 사용해야 한다(MUST).
* JWS 서명은 X.509 인증서와 연결된 개인 키(private key)를 기반으로
생성되어야 한다(SHOULD).
* 서명에 X.509를 사용했다면, JWS 헤더에 관련 인증서 체인을 담은 "x5c" 속성을
포함해야 한다(SHOULD).

<a name="lrs-requirements-3"></a>
##### LRS 요구사항 (LRS Requirements)
* LRS는 형식이 잘못된(malformed) 서명을 포함한 Statement를 저장하려는 요청을 `400 Bad Request`로 반드시 거부해야 한다(MUST).
* LRS는 거부된 Statement에 대한 응답에 메시지를 포함해야 한다(SHOULD). 
* 서명이 올바른 형식인지 검증하기 위해 LRS는 반드시 다음을 수행해야 한다(MUST):
    * JWS 서명을 디코딩하고, JWS 서명 페이로드에서 Statement의 서명된 직렬화를
      불러온다.
    * 원래 Statement가 수신된 Statement와 논리적으로 동등한지 검증한다. 
    [Statement 비교 요구사항](#statement-comparision-requirements)을 참고한다.
    * JWS 헤더에 X.509 인증서가 포함되어 있으면, JWS에 정의된 대로 해당 인증서에 대해
    서명을 검증한다.
    * 위에 설명한 서명 요구사항이 충족되었는지 검증한다. 

__참고:__ 포함된 X.509 인증서에 대해 검증하는 단계는 보안 조치가 아니라 서명의 실수를
잡아내기 위한 방법으로 의도된 것이다. 서명된 Statement를 인증하는 단계는 요구되는 확실성의
정도에 따라 달라지며 이 명세의 범위를 벗어난다.

<a name="client-requirements-1"></a>
##### 클라이언트 요구사항 (Client Requirements)

* 클라이언트는 위에 설명한 서명 요구사항을 반드시 따라야 한다(MUST).
* 클라이언트는 LRS가 서명을 수락했다는 이유만으로 서명이 유효하다고 가정해서는 안 된다(MUST NOT).

<a name="example-8"></a>
##### 예시 (Example)

예시는 [부록 D: 서명된 Statement 예시](#appendix-d-example-signed-statement)를 참고한다.


<a name="30-metadata"></a>
## 3.0 메타데이터 (Metadata)

메타데이터는 리소스에 대한 추가 정보이다. 메타데이터는 의사결정, 검색, 발견 가능성(discoverability)을 가능하게 한다. 
xAPI에서 메타데이터는 다양한 위치에서 활용될 수 있다. 가장 일반적인 위치는 [Activity Definition](#activity-definition) 안이다.


<a name="31-iri-requirements"></a>
### 3.1 IRI 요구사항 (IRI Requirements)

xAPI는 식별자로 IRI를 사용한다. IRI를 사용하면 고유성이 보장되고 해석 가능성(resolvability)이 높아진다. LRS와 
Learning Record Provider는 아래에 설명한 대로 각 IRI에 관해 각자의 책임을 진다. Activity Definition에는 추가 규칙이 
있으며 [여기](#activity-definition)에서 확인할 수 있다.

<a name="metadata-provider-requirements"></a>
##### 메타데이터 제공자 요구사항 (Metadata Provider Requirements)

이 요구사항은 새 IRI를 정의하는 Learning Record Provider에도 적용된다. 

* 새 IRI를 정의하는 [메타데이터 제공자(Metadata Provider)](./xAPI-About.md#def-metadata-provider)는 자신이 통제하는 IRI 
또는 통제자(controller)로부터 사용 허가를 받은 IRI만 사용해야 한다(SHOULD*).
* 새 Verb IRI를 정의하는 메타데이터 제공자는 반드시 자신이 통제하는 IRI 
또는 통제자로부터 사용 허가를 받은 IRI만 사용해야 한다(MUST).
* 적절한 식별자가 이미 존재하는 경우, 메타데이터 제공자는 해당 기존 식별자를 사용해야 하며(SHOULD) 
새 식별자를 만들지 않아야 한다(SHOULD NOT).
* 기존 식별자를 재사용할 때, 메타데이터 제공자는 문자 단위로 정확히 동일한 
IRI를 사용하도록 해야 한다(SHOULD*). 
* 적절한 식별자가 아직 존재하지 않는 경우, 메타데이터 제공자는 자신만의 식별자를 만들 수 있다(MAY).
* 식별자를 정의할 때, 메타데이터 제공자는 하나의 페이지에 여러 식별자의 정의를 담을 수 있도록 
앵커를 포함한 IRI를 사용할 수 있다(MAY). 예: `http://example.com/xapi/verbs#defenestrated`
* 식별자를 정의할 때, 메타데이터 제공자는 소문자 IRI를 사용해야 한다(SHOULD). 

<a name="lrs-requirements-4"></a>
##### LRS 요구사항 (LRS Requirements)

* IRI를 저장하거나 비교할 때, LRS는 
[RFC 3987의 5.3.1(단순 문자열 비교, Simple String Comparison)과 5.3.2(구문 기반 정규화, Syntax-Based Normalization)](https://tools.ietf.org/html/rfc3987#section-5.3)에 설명된 접근 방식 중 하나 이상만을 사용하여 처리해야 하며(SHOULD*), 
[같은 RFC의 5.3.3(스킴 기반 정규화, Scheme-Based Normalization) 또는 5.3.4(프로토콜 기반 정규화, Protocol-Based Normalization)](https://tools.ietf.org/html/rfc3987#section-5.3)에 설명된 접근 방식이나 
그 밖의 다른 접근 방식으로 처리하지 않아야 한다(SHOULD* NOT).
* LRS는 IRI를 담도록 정의된 파라미터와 필드의 모든 IRI에 동일한 IRI 비교 및 정규화 규칙을 
적용해야 한다(SHOULD*).


<a name="32-hosted-metadata"></a>
### 3.2 호스팅된 메타데이터 (Hosted Metadata)

<a name="description-21"></a>
##### 설명 (Description)

식별자에 대한 추가 정보는 Statement 안에서 제공될 수 있고, 식별자 IRI가 가리키는 위치에 
호스팅될 수도 있다. Statement에 메타데이터를 포함하면 IRI를 해석(resolve)하지 않고도 IRI에 대한
메타데이터를 표현할 수 있다. IRI 위치에 메타데이터를 호스팅하면 IRI의 소유자가 해당 IRI에 대한
정규(canonical) 메타데이터를 정의할 수 있다. 

<a name="details-23"></a>
##### 세부 사항 (Details)

이 명세에서 사용하는 IRI 식별자에는 여러 유형이 있다:

* [Verb](#243-verb)
* [Activity id](#activity-id-requirements)
* [Activity type](#acttype)
* [확장 키(extension key)](#41-extensions)
* [Attachment 용도 타입(attachment usage type)](#attachmentUsage)

Activity id에 대한 호스팅된 메타데이터의 구조는 [Activity Definition Object](#2441-when-the-objecttype-is-activity)를 참고한다.

그 밖의 모든 식별자에 대한 호스팅된 메타데이터의 구조는 아래 형식을 참고한다:

<table>
	<tr><th>속성</th><th>타입</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>name</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>사람이 읽을 수 있는/시각적 이름. Verb의 경우 Statement의 "display" 속성에 해당한다.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>description</td>
		<td><a href="#42-language-maps">Language Map</a></td>
		<td>설명</td>
		<td>선택</td>
	</tr>
</table>

호스팅된 메타데이터는 위에 설명한 JSON 객체를 담은 문서로 구성된다. 이 호스팅된 메타데이터가 제공되면, 
그것이 설명하는 식별자에 대한 정규 정보 출처가 된다. xAPI를 구현하는 사람은 Activity id를 제외한 모든 유형의 
IRI 식별자에 대해, 확립되어 널리 채택된 식별자를 찾아 사용할 것을 권장한다.

<a name="metadata-provider-requirements-1"></a>
##### 메타데이터 제공자 요구사항 (Metadata Provider Requirements)

* 메타데이터는 식별자와 함께 제공될 수 있다(MAY).
* 메타데이터를 제공하는 경우, "name"과 "description"을 모두 포함해야 한다(SHOULD).
* 위의 모든 식별자 IRI에 대해, 메타데이터 제공자는 의도된 용도에 대한 사람이 읽을 수 있는 설명을 
해당 IRI에서 접근할 수 있도록 해야 한다(SHOULD).
* 위의 모든 식별자 IRI에 대해, 메타데이터 제공자는 해당 IRI가 요청되고 Content-Type으로 `application/json`이 
요청될 때 이 JSON 메타데이터를 그 IRI에서 이용할 수 있도록 해야 한다(SHOULD).
* IRI가 Activity를 나타내는 경우, 메타데이터 제공자는 Statement에서 사용되는 
[Activity Definition](#activity-definition) JSON 형식을 사용하여 Content-Type `application/json`으로 메타데이터를 호스팅할 수 있다(MAY).

<a name="lrs-requirements-5"></a>
##### LRS 요구사항 (LRS Requirements)

* LRS는 [메타데이터 소비자(Metadata Consumer)](./xAPI-About.md#def-metadata-consumer)로서 동작하여 식별자 IRI의 해석을 시도할 수 있다(MAY).
* Activity IRI가 URL이면, LRS는 해당 URL에 GET 요청을 시도해야 하며(SHOULD), 이때 HTTP
헤더에 `Accept: application/json, */*`를 포함한다. 이는 LRS가 해당 Activity id를 처음 접한 뒤
가능한 한 빨리 수행해야 한다(SHOULD).
* Activity id로 사용된 URL에서 유효한 Activity Definition인 JSON을 불러오면,
 LRS는 불러온 정의를 해당 Activity의 정규 정의에 통합해야 하며(SHOULD),
이때 불러온 정의에 포함되지 않은 이름이나 정의는 보존한다.
* Activity id로 사용된 URL에서 LRS가 Activity Definition을 파싱할 수 있는 문서를
불러온 경우, LRS는 해당 Activity 정의의 정규 표현을 결정할 때
이 정의를 고려할 수 있다(MAY).

<a name="metadata-consumer-requirements"></a>
##### 메타데이터 소비자 요구사항 (Metadata Consumer Requirements)

* 메타데이터 소비자가 IRI에서 메타데이터를 얻은 경우, 해당 IRI에서 발견된 메타데이터가 그 메타데이터에 
포함된 속성과 언어에 관해서는 권위 있는(authoritative) 것이라고 강하게 추정해야 한다(SHOULD). 
* 메타데이터 소비자는 번역 등 누락된 세부 정보를 채우기 위해 다른 정보 출처를 사용할 수 있으며(MAY), 
호스팅된 메타데이터가 제공되지 않았거나, 불러올 수 없거나, 메타데이터 소비자가 이를 신뢰하지 않는 경우에는 
다른 출처가 호스팅된 메타데이터를 완전히 대신할 수도 있다. 다른 정보 출처에는 식별자의 IRI에 저장된 
다른 형식의 메타데이터가 포함될 수 있으며(MAY), 특히 해당 식별자가 이 명세에서 사용하기 위해 만들어진 것이 아닌 경우에 그러하다.



<a name="40-special-data-types-and-rules"></a>
## 4.0 특수 데이터 타입과 규칙 (Special Data Types and Rules)

다음은 이 명세에서 흔히 등장하며 추가 규칙이 필요한 데이터 타입이다.


<a name="41-extensions"></a>
### 4.1 Extensions

<a name="description-22"></a>
##### 설명 (Description)

Extension은 Activity Definition의 일부로, Statement의 "context" 속성의 일부로, 또는 Statement의 
"result" 속성의 일부로 사용할 수 있다. 각 경우에 Extension은 특수한 용도를 위해 해당 속성을 자연스럽게 
확장하는 방법을 제공하기 위한 것이다. 이러한 Extension의 내용은 단 하나의 애플리케이션에만 가치 있는 것일 
수도 있고, 실천 공동체(Community of Practice) 전체가 사용하는 관례일 수도 있다.

<a name="details-24"></a>
##### 세부 사항 (Details)

Extension은 맵으로 정의되며, 논리적으로 자신이 위치한 Statement의 부분과 관련된다. Extension의 값은 
어떤 JSON 값이나 데이터 구조든 될 수 있다. "context" 속성의 Extension은 핵심 경험에 대한 맥락을 제공하고, 
"result" 속성의 Extension은 어떤 결과(outcome)와 관련된 요소를 제공한다. Activity 안에서 Extension은 특정 
맞춤 애플리케이션이나 실천 공동체 내에서 Activity를 정의하는 데 도움이 되는 추가 정보를 제공한다. IRI 키 아래에 
있는 Extension 값의 의미와 구조는 해당 IRI를 통제하는 사람이 정의한다.

<a name="requirements-18"></a>
##### 요구사항 (Requirements)

* extensions 맵의 키는 반드시 IRI여야 한다(MUST).
* LRS는 extensions 맵의 값을 근거로 Statement를 거부해서는 안 된다(MUST NOT).
* Learning Record Provider는 Experience API에 적합한 도구 간의 상호운용성을 활용할 수 있도록, 
가능한 한 많은 정보를 내장 요소에 매핑하도록 항상 노력해야 한다(SHOULD).
* 모든 Extension IRI에는 통제자(controller)가 있어야 한다(SHOULD).
* IRL Extension 키의 통제자는 해당 IRL이 지원하는 Extension의 의도된 의미에 대한 사람이 읽을 수 있는 
설명을 그 IRL에서 접근할 수 있도록 해야 한다(SHOULD).

__참고:__ 전적으로 Extension에 의해 정의된 Statement는 다른 어떤 시스템도 이해할 수 없으므로 무의미해진다. 


<a name="42-language-maps"></a>
### 4.2 언어 맵 (Language Maps)

<a name="description-23"></a>
##### 설명 (Description)

언어 맵은 키가 [RFC 5646 언어 태그(Language Tag)](http://tools.ietf.org/html/rfc5646)이고, 
값이 해당 태그가 지정한 언어로 된 문자열인 딕셔너리이다. 이 맵은 해당 문자열의 여러 언어 버전에 대해 
알고 있는 바를 바탕으로 가능한 한 완전하게 채워야 한다(SHOULD). 

각 언어 문자열에는 일반적으로 유효한 가장 짧은 언어 코드가 선호된다. 
[ISO 639 언어 코드](https://www.loc.gov/standards/iso639-2/php/code_list.php)와 
[ISO 3166-1 국가 코드](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)를 조합하면
기본 언어(예: 스페인어는 `es`)와 지역(예: 멕시코에서 사용되는 스페인어 방언인
`es-MX`)을 지정할 수 있다. ISO 639 언어 코드만 확실히 알고 있다면, 
가능한 ISO 3166-1 국가 코드를 추측하지 않는다. 예를 들어
기본 언어(예: 영어)만 알고 있다면 `en-US`가 아닌 최상위
언어 태그 `en`을 사용한다. 구체적인 지역 변형을 알고 있다면 전체 언어 코드를 사용한다.

__참고:__ 중국어의 경우, `zh`가 나타내는 상당한 언어적 다양성 때문에 ISO 639 언어 
코드만으로는 일반적으로 충분하지 않다.

언어 맵 안의 문자열 내용은 일반 텍스트(plain text)이다. HTML 태그나 마크다운 같은 서식 코드는 
렌더링되지 않으며, 이 문자열이 최종 사용자에게 표시될 때 코드 그대로 표시될 것으로 예상된다. 중요한 예외는 
언어 맵 Object가 Extension에서 사용되고, 해당 Extension IRI의 소유자가 특정 형태의 코드가 렌더링된다고 
명시적으로 밝힌 경우이다.


<a name="43-iris"></a>
### 4.3 IRIs

국제화 리소스 식별자(Internationalized Resource Identifiers, IRI)는 해석 가능(resolvable)할 수도 있는 고유 식별자이다. 
해석 가능성은 요구사항이 아니므로 IRL/URL 대신 IRI/URI를 사용한다. 식별자에 사용되는 문자에 최대한의 
유연성을 허용하기 위해 URI 대신 IRI를 사용하는데, IRI는 ASCII 문자 집합 밖의 일부 문자를 
포함할 수 있기 때문이다. 

[메타데이터](#30-metadata)를 참고한다. 


<a name="44-uuids"></a>
### 4.4 UUIDs

범용 고유 식별자(Universally Unique Identifiers, UUID)는 전역적으로 고유한 128비트 값이다. IRI와 달리 UUID는 
완전히 다른 형식을 가지므로 해석 가능성은 기대되지 않는다. UUID는 반드시 표준 
문자열 형식이어야 한다(MUST). [RFC 4122](http://tools.ietf.org/html/rfc4122)의 variant 2를 사용할 것을 권장한다.


<a name="45-iso-8601-timestamps"></a>
### 4.5 ISO 8601 타임스탬프 (ISO 8601 Timestamps)

Timestamp는 특정 시점을 나타내는 형식 타입이다. Timestamp는 ISO 8601의 일반 형식에 따라 형식화된다. 
LRS로 전송된 Statement는 최소 밀리초 단위까지 정밀도가 유지될 것으로 기대할 수 있다 

<a name="requirements-19"></a>
###### 요구사항 (Requirements)
* Timestamp는 반드시 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601#Combined_date_and_time_representations)에 따라 형식화되어야 한다(MUST).
* Timestamp는 ISO 8601의 프로파일인 [RFC 3339](https://www.ietf.org/rfc/rfc3339.txt)에 설명된 형식으로 표현해야 한다(SHOULD*). 
* Timestamp는 반드시 최소 밀리초(초 이하 소수점 3자리)까지 정밀도를 유지해야 한다(MUST).  
* Timestamp는 시간대(time zone)를 포함해야 한다(SHOULD*).
* Timestamp가 시간대를 포함하는 경우, LRS는 참조하는 시점이 영향을 받지 않는 한 Statement에서 원래 사용된 
것과 다른 시간대로 Timestamp를 반환할 수 있다(MAY). 
* LRS는 Timestamp를 UTC 시간대로 반환해야 한다(SHOULD*). 
* Timestamp는 초 단위 소수점 최소 3자리의 정밀도로 잘라내거나(truncate) 반올림할 수 있다(MAY). 


<a name="46-iso-8601-durations"></a>
### 4.6 ISO 8601 기간 (ISO 8601 Durations)

Duration은 어떤 일에 걸린 시간의 양을 나타내는 문자열이다.

<a name="requirements-20"></a>
###### 요구사항 (Requirements)

* Duration은 반드시 ISO 8601:2004(E) 4.4.3.2절의 Duration 형식을 사용하여 표현해야 한다(MUST).
대체 형식(시점에 사용되는 형식에 맞추어 ISO 8601:2004(E) 4.4.3.3절에 설명된 형식)은 
사용해서는 안 된다(MUST NOT).
* Learning Record Provider는 최대 0.01초의 정밀도를 제공해야 한다(SHOULD). 
* Learning Record Provider는 더 낮은 정밀도를 제공할 수 있다(MAY). 예를 들어 대학 학위를 
취득하는 경우라면 정밀도는 월 또는 연 단위일 수 있다. 
* 0.01초보다 높은 정밀도의 Duration을 수신한 경우, LRS는 요청을 거부하지 않아야 하며(SHOULD* NOT), 
"duration" 속성을 0.01초 정밀도로 잘라낼 수 있다(MAY). 
* Duration을 비교할 때, 0.01초를 넘는 정밀도는 비교에 
포함하지 않아야 한다(SHOULD* NOT).

<a name="examples-1"></a>
###### 예시 (Examples)

아래 표는 ISO 8601 Duration의 몇 가지 예시를 보여 준다. 이 목록은 모든 경우를 망라하려는 것이 아니다. 

<table>
	<tr><th>예시</th><th>설명</th></tr>
	<tr>
		<td>PT4H35M59.14S</td>
		<td>4시간 35분 59.14초.</td>
	</tr>
	<tr>
		<td>PT16559.14S</td>
		<td>위와 같은 기간을 초 단위로 표현한 것. 
		(참고: 해당 기간에 윤초가 포함되어 있다면 이 변환은 부정확하다)</td>
	</tr>
	<tr>
		<td>P3Y1M29DT4H35M59.14S</td>
		<td>연, 월, 일도 포함한 Duration.</td>
	</tr>
	<tr>
		<td>P3Y</td>
		<td>약 3년. 예: 자격(qualification) 취득 완료.</td>
	</tr>
	<tr>
		<td>P4W</td>
		<td>4주. 주(week)는 다른 기간 단위와 결합할 수 없다는 점에 유의한다. 'P4W1D'는 유효하지 않다.</td>
	</tr>
</table>

Duration은 기록된 형식 그대로 표시될 것으로 예상된다. 예를 들어 Duration을 초(또는 초의 소수) 단위로
추적한다면, 이를 시, 분, 초로 변환할 필요가 없다. 

<a name="appendices"></a>
## 부록 (Appendices) 
 
<a name="appendix-a-example-statements"></a>
### 부록 A: Statement 예시 (Appendix A: Example Statements)

간단한 Statement 예시(줄바꿈은 표시 목적으로만 사용됨):  
```
{
	"id":"fd41c918-b88b-4b20-a0a5-a4c32391aaa0",
	"timestamp": "2015-11-18T12:17:00+00:00",
	"actor":{
		"objectType": "Agent",
		"name":"Project Tin Can API",
		"mbox":"mailto:user@example.com"
	},
	"verb":{
		"id":"http://example.com/xapi/verbs#sent-a-statement",
		"display":{ 
			"en-US":"sent" 
		}
	},
	"object":{
		"id":"http://example.com/xapi/activity/simplestatement",
		"definition":{
			"name":{ 
				"en-US":"simple statement" 
			},
			"description":{ 
				"en-US":"A simple Experience API statement. Note that the LRS 
				does not need to have any prior information about the Actor (learner), the 
				verb, or the Activity/object." 
			}
		}
	}
}
```   
Verb 이름이 "attempted"이고 Duration을 초 단위로 표현한(분과 초로 변환하지 않은) 완료 예시:  
```
{
	"id":"7ccd3322-e1a5-411a-a67d-6a735c76f119",
	"timestamp": "2015-12-18T12:17:00+00:00",
	"actor":{
        "objectType": "Agent",
		"name":"Example Learner",
		"mbox":"mailto:example.learner@adlnet.gov"
	},
	"verb":{
		"id":"http://adlnet.gov/expapi/verbs/attempted",
		"display":{
			"en-US":"attempted"
		}
	},
	"object":{
		"id":"http://example.adlnet.gov/xapi/example/simpleCBT",
		"definition":{
			"name":{
				"en-US":"simple CBT course"
			},
			"description":{
				"en-US":"A fictitious example CBT course."
			}
		}
	},
	"result":{
		"score":{
			"scaled":0.95
		},
		"success":true,
		"completion":true,
		"duration": "PT1234S"
	}
}
```  
사용 가능한 대부분의 속성을 보여 주는 긴 Statement 예시. 이 예시는 LRS가 설정한
"authority" 및 "stored" 속성을 포함하여 LRS가 반환한 Statement를 보여 준다:  
```
{
    "id": "6690e6c9-3ef0-4ed3-8b37-7f3964730bee",
    "actor": {
        "name": "Team PB",
        "mbox": "mailto:teampb@example.com",
        "member": [
            {
                "name": "Andrew Downes",
                "account": {
                    "homePage": "http://www.example.com",
                    "name": "13936749"
                },
                "objectType": "Agent"
            },
            {
                "name": "Toby Nichols",
                "openid": "http://toby.openid.example.org/",
                "objectType": "Agent"
            },
            {
                "name": "Ena Hills",
                "mbox_sha1sum": "ebd31e95054c018b10727ccffd2ef2ec3a016ee9",
                "objectType": "Agent"
            }
        ],
        "objectType": "Group"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/attended",
        "display": {
            "en-GB": "attended",
            "en-US": "attended"
        }
    },
    "result": {
        "extensions": {
            "http://example.com/profiles/meetings/resultextensions/minuteslocation": "X:\\meetings\\minutes\\examplemeeting.one"
        },
        "success": true,
        "completion": true,
        "response": "We agreed on some example actions.",
        "duration": "PT1H0M0S"
    },
    "context": {
        "registration": "ec531277-b57b-4c15-8d91-d292c5b2b8f7",
        "contextActivities": {
            "parent": [
                {
                    "id": "http://www.example.com/meetings/series/267",
                    "objectType": "Activity"
                }
            ],
            "category": [
                {
                    "id": "http://www.example.com/meetings/categories/teammeeting",
                    "objectType": "Activity",
                    "definition": {
			            "name": {
			                "en": "team meeting"
			            },
			            "description": {
			                "en": "A category of meeting used for regular team meetings."
			            },
			            "type": "http://example.com/expapi/activities/meetingcategory"
			        }
                }
            ],
            "other": [
                {
                    "id": "http://www.example.com/meetings/occurances/34257",
                    "objectType": "Activity"
                },
                {
                    "id": "http://www.example.com/meetings/occurances/3425567",
                    "objectType": "Activity"
                }
            ]
        },
        "instructor" :
        {
        	"name": "Andrew Downes",
            "account": {
                "homePage": "http://www.example.com",
                "name": "13936749"
            },
            "objectType": "Agent"
        },
        "team":
        {
        	"name": "Team PB",
        	"mbox": "mailto:teampb@example.com",
        	"objectType": "Group"
        }, 
        "platform" : "Example virtual meeting software",
        "language" : "tlh",
        "statement" : {
        	"objectType":"StatementRef",
        	"id" :"6690e6c9-3ef0-4ed3-8b37-7f3964730bee"
        }
        
    },
    "timestamp": "2013-05-18T05:32:34.804+00:00",
    "stored": "2013-05-18T05:32:34.804+00:00",
    "authority": {
        "account": {
            "homePage": "http://cloud.scorm.com/",
            "name": "anonymous"
        },
        "objectType": "Agent"
    },
    "version": "1.0.0",
    "object": {
        "id": "http://www.example.com/meetings/occurances/34534",
        "definition": {
            "extensions": {
                "http://example.com/profiles/meetings/activitydefinitionextensions/room": {"name": "Kilby", "id" : "http://example.com/rooms/342"}
            },
            "name": {
                "en-GB": "example meeting",
                "en-US": "example meeting"
            },
            "description": {
                "en-GB": "An example meeting that happened on a specific occasion with certain people present.",
                "en-US": "An example meeting that happened on a specific occasion with certain people present."
            },
            "type": "http://adlnet.gov/expapi/activities/meeting",
            "moreInfo": "http://virtualmeeting.example.com/345256"
        },
        "objectType": "Activity"
    }
}
```  

<a name="appendix-b-examples-of-statements-objects-of-different-types"></a>
### 부록 B: 다양한 유형의 Statement Object 예시 (Appendix B: Examples of Statement's Objects of different types)

Statement의 Object는 Activity, Agent, Group 또는 Statement일 수 있다. 
이 부록은 각각에 대해 하나씩 예시를 제공한다. 

<a name="object-is-activity"></a>
###### Object가 Activity인 경우 (Object is Activity)
```
{
    "id": "http://www.example.co.uk/exampleactivity",
    "definition": {
        "name": {
            "en-GB": "example activity",
            "en-US": "example activity"
        },
        "description": {
            "en-GB": "An example of an activity",
            "en-US": "An example of an activity"
        },
        "type": "http://www.example.co.uk/types/exampleactivitytype"
    },
    "objectType": "Activity"
}
```

<a name="object-is-agent"></a>
###### Object가 Agent인 경우 (Object is Agent)
```
{
    "name": "Andrew Downes",
    "mbox": "mailto:andrew@example.co.uk",
    "objectType": "Agent"
}
```

<a name="object-is-group"></a>
###### Object가 Group인 경우 (Object is Group)

이 예시는 구성원(member)이 있는 Identified Group(식별된 Group)을 보여준다. 
```
{
    "name": "Example Group",
    "account" : {
    	"homePage" : "http://example.com/homePage",
    	"name" : "GroupAccount"
    },
    "objectType": "Group",
    "member": [
        {
            "name": "Andrew Downes",
            "mbox": "mailto:andrew@example.com",
            "objectType": "Agent"
        },
        {
            "name": "Aaron Silvers",
            "openid": "http://aaron.openid.example.org",
            "objectType": "Agent"
        }
    ]
}
```


<a name="object-is-statement"></a>
###### Object가 Statement인 경우 (Object is Statement)

이 예시는 Object가 Statement Reference(StatementRef)인 SubStatement Object를 보여준다.

```
{
    "objectType": "SubStatement",
    "actor" : {
        "objectType": "Agent", 
        "mbox":"mailto:agent@example.com" 
    },
    "verb" : { 
        "id":"http://example.com/confirmed", 
        "display":{
            "en":"confirmed"
        } 
    },
    "object": {
        "objectType":"StatementRef",
		"id" :"9e13cefd-53d3-4eac-b5ed-2cf6693903bb"
    }
}
```


<a name="appendix-c-example-definitions-for-activities-of-type-cmiinteraction"></a>
### 부록 C: `cmi.interaction` 유형 Activity의 정의 예시 (Appendix C: Example definitions for Activities of type `cmi.interaction`)

<a name="true-false"></a>
###### true-false

```
"definition": {
	"description": {
		"en-US": "Does the xAPI include the concept of statements?"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "true-false",
	"correctResponsesPattern": [
		"true"
	]
}
```

<a name="choice"></a>
###### choice
```
"definition": {
	"description": {
		"en-US": "Which of these prototypes are available at the beta site?"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "choice",
	"correctResponsesPattern": [
		"golf[,]tetris"
	],
	"choices": [
		{
			"id": "golf", 
			"description": {
				"en-US": "Golf Example"
			}
		},
		{
			"id": "facebook", 
			"description": {
				"en-US": "Facebook App"
			}
		},
		{
			"id": "tetris", 
			"description": {
				"en-US": "Tetris Example"
			}
		},
		{
			"id": "scrabble", 
			"description": {
				"en-US": "Scrabble Example"
			}
		}
	]
}
```

<a name="fill-in"></a>
###### fill-in
```
"definition": {
	"description": {
		"en-US": "Ben is often heard saying: "
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "fill-in",
	"correctResponsesPattern": [
		"Bob's your uncle"
	]
}
```

<a name="long-fill-in"></a>
###### long-fill-in
```
"definition": {
	"description": {
		"en-US": "What is the purpose of the xAPI?"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "long-fill-in",
	"correctResponsesPattern": [
		"{case_matters=false}{lang=en}To store and provide access to learning experiences."
	]
}
```

<a name="likert"></a>
###### likert
```
"definition": {
	"description": {
		"en-US": "How awesome is Experience API?"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "likert",
	"correctResponsesPattern": [
		"likert_3"
	],
	"scale": [
		{
			"id": "likert_0", 
			"description": {
				"en-US": "It's OK"
			}
		},
		{
			"id": "likert_1", 
			"description": {
				"en-US": "It's Pretty Cool"
			}
		},
		{
			"id": "likert_2", 
			"description": {
				"en-US": "It's Damn Cool"
			}
		},
		{
			"id": "likert_3", 
			"description": {
				"en-US": "It's Gonna Change the World"
			}
		}
	]
}
```

<a name="matching"></a>
###### matching
```
"definition": {
	"description": {
		"en-US": "Match these people to their kickball team:"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "matching",
	"correctResponsesPattern": [
		"ben[.]3[,]chris[.]2[,]troy[.]4[,]freddie[.]1"
	],
	"source": [
		{
			"id": "ben",
			"description": {
				"en-US": "Ben"
			}
		},
		{
			"id": "chris",
			"description": {
				"en-US": "Chris"
			}
		},
		{
			"id": "troy",
			"description": {
				"en-US": "Troy"
			}
		},
		{
			"id": "freddie",
			"description": {
				"en-US": "Freddie"
			}
		}
	],
	"target": [
		{
			"id": "1",
			"description": {
				"en-US": "Swift Kick in the Grass"
			}
		},
		{
			"id": "2",
			"description": {
				"en-US": "We got Runs"
			}
		},
		{
			"id": "3",
			"description": {
				"en-US": "Duck"
			}
		},
		{
			"id": "4",
			"description": {
				"en-US": "Van Delay Industries"
			}
		}
	]
}
```

<a name="performance"></a>
###### performance
```
"definition": {
	"description": {
		"en-US": "This interaction measures performance over a day of RS sports:"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "performance",
	"correctResponsesPattern": [
		"pong[.]1:[,]dg[.]:10[,]lunch[.]"
	],
	"steps": [
		{
			"id": "pong", 
			"description": {
				"en-US": "Net pong matches won"
			}
		},
		{
			"id": "dg", 
			"description": {
				"en-US": "Strokes over par in disc golf at Liberty"
				}
			},
		{
			"id": "lunch", 
			"description": {
				"en-US": "Lunch having been eaten"
			}
		}
	]
}
```

<a name="sequencing"></a>
###### sequencing
```
"definition": {
	"description": {
		"en-US": "Order players by their pong ladder position:"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "sequencing",
	"correctResponsesPattern": [
		"tim[,]mike[,]ells[,]ben"
	],
	"choices": [
		{
			"id": "tim", 
			"description": {
				"en-US": "Tim"
			}
		},
		{
			"id": "ben", "description": {
				"en-US": "Ben"
			}
		},
		{
			"id": "ells", 
			"description": {
				"en-US": "Ells"
			}
		},
		{
			"id": "mike", 
			"description": {
				"en-US": "Mike"
			}
		}
	]
}
```

<a name="numeric"></a>
###### numeric
```
"definition": {
	"description": {
		"en-US": "How many jokes is Chris the butt of each day?"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "numeric",
	"correctResponsesPattern": [
		"4[:]"
	]
}
```

이 예시에서 최소 정답은 `4`이며 최댓값은 없다. `5`, `6`, `976`은 모두 정답이 된다. 

<a name="other"></a>
###### other
```
"definition": {
	"description": {
		"en-US": "On this map, please mark Franklin, TN"
	},
	"type": "http://adlnet.gov/expapi/activities/cmi.interaction",
	"interactionType": "other",
	"correctResponsesPattern": [
		"(35.937432,-86.868896)"
	]
}
```


<a name="appendix-d-example-signed-statement"></a>
### 부록 D: 서명된 Statement 예시 (Appendix D: Example Signed Statement)

[2.6절 서명된 Statement (Signed Statements)](#26-signed-statements)에서 설명한 서명된 Statement의 예시이다.

서명 대상이 되는 원본 Statement 직렬화(serialization)이다. 이 예시의 줄바꿈은
CR+LF(0x0D + 0x0A)로 포함되어 있다.

```
{
    "version": "1.0.0",
    "id": "33cff416-e331-4c9d-969e-5373a1756120",
    "actor": {
        "mbox": "mailto:example@example.com",
        "name": "Example Learner",
        "objectType": "Agent"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/experienced",
        "display": {
            "en-US": "experienced"
        }
    },
    "object": {
        "id": "https://www.youtube.com/watch?v=xh4kIiH3Sm8",
        "objectType": "Activity",
        "definition": {
            "name": {
                "en-US": "Tax Tips & Information : How to File a Tax Return "
            },
            "description": {
                "en-US": "Filing a tax return will require filling out either a 1040, 1040A or 1040EZ form"
            }
        }
    },
    "timestamp": "2013-04-01T12:00:00Z"
}
```

서명에 사용할 X.509 인증서의 개인 키(private key) 예시:
```
-----BEGIN RSA PRIVATE KEY-----
MIICXAIBAAKBgQDjxvZXF30WL4oKjZYXgR0ZyaX+u3y6+JqTqiNkFa/VTnet6Ly2
OT6ZmmcJEPnq3UnewpHoOQ+GfhhTkW13j06j5iNn4obcCVWTL9yXNvJH+Ko+xu4Y
l/ySPRrIPyTjtHdG0M2XzIlmmLqm+CAS+KCbJeH4tf543kIWC5pC5p3cVQIDAQAB
AoGAOejdvGq2XKuddu1kWXl0Aphn4YmdPpPyCNTaxplU6PBYMRjY0aNgLQE6bO2p
/HJiU4Y4PkgzkEgCu0xf/mOq5DnSkX32ICoQS6jChABAe20ErPfm5t8h9YKsTfn9
40lAouuwD9ePRteizd4YvHtiMMwmh5PtUoCbqLefawNApAECQQD1mdBW3zL0okUx
2pc4tttn2qArCG4CsEZMLlGRDd3FwPWJz3ZPNEEgZWXGSpA9F1QTZ6JYXIfejjRo
UuvRMWeBAkEA7WvzDBNcv4N+xeUKvH8ILti/BM58LraTtqJlzjQSovek0srxtmDg
5of+xrxN6IM4p7yvQa+7YOUOukrVXjG+1QJBAI2mBrjzxgm9xTa5odn97JD7UMFA
/WHjlMe/Nx/35V52qaav1sZbluw+TvKMcqApYj5G2SUpSNudHLDGkmd2nQECQFfc
lBRK8g7ZncekbGW3aRLVGVOxClnLLTzwOlamBKOUm8V6XxsMHQ6TE2D+fKJoNUY1
2HGpk+FWwy2D1hRGuoUCQAXfaLSxtaWdPtlZTPVueF7ZikQDsVg+vtTFgpuHloR2
6EVc1RbHHZm32yvGDY8IkcoMfJQqLONDdLfS/05yoNU=
-----END RSA PRIVATE KEY-----
```

공개 X.509 인증서(public X.509 certificate) 예시
```
-----BEGIN CERTIFICATE-----
MIIDATCCAmqgAwIBAgIJAMB1csNuA6+kMA0GCSqGSIb3DQEBBQUAMHExCzAJBgNV
BAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUgQ29t
cGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBsZUBl
eGFtcGxlLmNvbTAeFw0xMzA0MDQxNTI4MzBaFw0xNDA0MDQxNTI4MzBaMIGWMQsw
CQYDVQQGEwJVUzESMBAGA1UECBMJVGVubmVzc2VlMREwDwYDVQQHEwhGcmFua2xp
bjEYMBYGA1UEChMPRXhhbXBsZSBDb21wYW55MRAwDgYDVQQLEwdFeGFtcGxlMRAw
DgYDVQQDEwdFeGFtcGxlMSIwIAYJKoZIhvcNAQkBFhNleGFtcGxlQGV4YW1wbGUu
Y29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDjxvZXF30WL4oKjZYXgR0Z
yaX+u3y6+JqTqiNkFa/VTnet6Ly2OT6ZmmcJEPnq3UnewpHoOQ+GfhhTkW13j06j
5iNn4obcCVWTL9yXNvJH+Ko+xu4Yl/ySPRrIPyTjtHdG0M2XzIlmmLqm+CAS+KCb
JeH4tf543kIWC5pC5p3cVQIDAQABo3sweTAJBgNVHRMEAjAAMCwGCWCGSAGG+EIB
DQQfFh1PcGVuU1NMIEdlbmVyYXRlZCBDZXJ0aWZpY2F0ZTAdBgNVHQ4EFgQUVs3v
5afEdOeoYeVajAQE4v0WS1QwHwYDVR0jBBgwFoAUyVIc3yvra4EBz20I4BF39IAi
xBkwDQYJKoZIhvcNAQEFBQADgYEAgS/FF5D0Hnj44rvT6kgn3kJAvv2lj/fyjztK
IrYS33ljXGn6gGyA4qtbXA23PrO4uc/wYCSDICDpPobh62xTCd9qObKhgwWOi05P
SBLqUu3mwfAe15LJBJBqPVZ4K0kppePBU8m6aIZoH57L/9t4OoaL8yKs/qjKFeI1
OFWZxvA=
-----END CERTIFICATE-----
```

인증 기관(CA) 인증서 예시
```
-----BEGIN CERTIFICATE-----
MIIDNzCCAqCgAwIBAgIJAMB1csNuA6+jMA0GCSqGSIb3DQEBBQUAMHExCzAJBgNV
BAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUgQ29t
cGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBsZUBl
eGFtcGxlLmNvbTAeFw0xMzA0MDQxNTI1NTNaFw0yMzA0MDIxNTI1NTNaMHExCzAJ
BgNVBAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUg
Q29tcGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBs
ZUBleGFtcGxlLmNvbTCBnzANBgkqhkiG9w0BAQEFAAOBjQAwgYkCgYEA1sBnBWPZ
0f7WJUFTJy5+01SlS5Z6DDD6Uye9vK9AycgV5B3+WC8HC5u5h91MujAC1ARPVUOt
svPRs45qKNFIgIGRXKPAwZjawEI2sCJRSKV47i6B8bDv4WkuGvQaveZGI0qlmN5R
1Eim2gUItRj1hgcC9rQavjlnFKDY2rlXGukCAwEAAaOB1jCB0zAdBgNVHQ4EFgQU
yVIc3yvra4EBz20I4BF39IAixBkwgaMGA1UdIwSBmzCBmIAUyVIc3yvra4EBz20I
4BF39IAixBmhdaRzMHExCzAJBgNVBAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUx
GDAWBgNVBAoTD0V4YW1wbGUgQ29tcGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAG
CSqGSIb3DQEJARYTZXhhbXBsZUBleGFtcGxlLmNvbYIJAMB1csNuA6+jMAwGA1Ud
EwQFMAMBAf8wDQYJKoZIhvcNAQEFBQADgYEADhwTebGk735yKhm8DqCxvNnEZ0Nx
sYEYOjgRG1yXTlW5pE691fSH5AZ+T6fpwpZcWY5QYkoN6DnwjOxGkSfQC3/yGmcU
DKBPwiZ5O2s9C+fE1kUEnrX2Xea4agVngMzR8DQ6oOauLWqehDB+g2ENWRLoVgS+
ma5/Ycs0GTyrECY=
-----END CERTIFICATE-----
```

JWS 헤더(JWS Header). 알고리즘을 지정하는 것과 함께, 서명 인증서의 인증서 체인(certificate chain)도
포함되어 있다는 점에 유의한다.
```
{
    "alg": "RS256",
    "x5c": [
        "MIIDATCCAmqgAwIBAgIJAMB1csNuA6+kMA0GCSqGSIb3DQEBBQUAMHExCzAJBgNVBAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUgQ29tcGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBsZUBleGFtcGxlLmNvbTAeFw0xMzA0MDQxNTI4MzBaFw0xNDA0MDQxNTI4MzBaMIGWMQswCQYDVQQGEwJVUzESMBAGA1UECBMJVGVubmVzc2VlMREwDwYDVQQHEwhGcmFua2xpbjEYMBYGA1UEChMPRXhhbXBsZSBDb21wYW55MRAwDgYDVQQLEwdFeGFtcGxlMRAwDgYDVQQDEwdFeGFtcGxlMSIwIAYJKoZIhvcNAQkBFhNleGFtcGxlQGV4YW1wbGUuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDjxvZXF30WL4oKjZYXgR0ZyaX+u3y6+JqTqiNkFa/VTnet6Ly2OT6ZmmcJEPnq3UnewpHoOQ+GfhhTkW13j06j5iNn4obcCVWTL9yXNvJH+Ko+xu4Yl/ySPRrIPyTjtHdG0M2XzIlmmLqm+CAS+KCbJeH4tf543kIWC5pC5p3cVQIDAQABo3sweTAJBgNVHRMEAjAAMCwGCWCGSAGG+EIBDQQfFh1PcGVuU1NMIEdlbmVyYXRlZCBDZXJ0aWZpY2F0ZTAdBgNVHQ4EFgQUVs3v5afEdOeoYeVajAQE4v0WS1QwHwYDVR0jBBgwFoAUyVIc3yvra4EBz20I4BF39IAixBkwDQYJKoZIhvcNAQEFBQADgYEAgS/FF5D0Hnj44rvT6kgn3kJAvv2lj/fyjztKIrYS33ljXGn6gGyA4qtbXA23PrO4uc/wYCSDICDpPobh62xTCd9qObKhgwWOi05PSBLqUu3mwfAe15LJBJBqPVZ4K0kppePBU8m6aIZoH57L/9t4OoaL8yKs/qjKFeI1OFWZxvA=",
        "MIIDNzCCAqCgAwIBAgIJAMB1csNuA6+jMA0GCSqGSIb3DQEBBQUAMHExCzAJBgNVBAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUgQ29tcGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBsZUBleGFtcGxlLmNvbTAeFw0xMzA0MDQxNTI1NTNaFw0yMzA0MDIxNTI1NTNaMHExCzAJBgNVBAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUgQ29tcGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBsZUBleGFtcGxlLmNvbTCBnzANBgkqhkiG9w0BAQEFAAOBjQAwgYkCgYEA1sBnBWPZ0f7WJUFTJy5+01SlS5Z6DDD6Uye9vK9AycgV5B3+WC8HC5u5h91MujAC1ARPVUOtsvPRs45qKNFIgIGRXKPAwZjawEI2sCJRSKV47i6B8bDv4WkuGvQaveZGI0qlmN5R1Eim2gUItRj1hgcC9rQavjlnFKDY2rlXGukCAwEAAaOB1jCB0zAdBgNVHQ4EFgQUyVIc3yvra4EBz20I4BF39IAixBkwgaMGA1UdIwSBmzCBmIAUyVIc3yvra4EBz20I4BF39IAixBmhdaRzMHExCzAJBgNVBAYTAlVTMRIwEAYDVQQIEwlUZW5uZXNzZWUxGDAWBgNVBAoTD0V4YW1wbGUgQ29tcGFueTEQMA4GA1UEAxMHRXhhbXBsZTEiMCAGCSqGSIb3DQEJARYTZXhhbXBsZUBleGFtcGxlLmNvbYIJAMB1csNuA6+jMAwGA1UdEwQFMAMBAf8wDQYJKoZIhvcNAQEFBQADgYEADhwTebGk735yKhm8DqCxvNnEZ0NxsYEYOjgRG1yXTlW5pE691fSH5AZ+T6fpwpZcWY5QYkoN6DnwjOxGkSfQC3/yGmcUDKBPwiZ5O2s9C+fE1kUEnrX2Xea4agVngMzR8DQ6oOauLWqehDB+g2ENWRLoVgS+ma5/Ycs0GTyrECY="
    ]
}
```

JWS 서명(JWS signature)
```
ew0KICAgICJhbGciOiAiUlMyNTYiLA0KICAgICJ4NWMiOiBbDQogICAgICAgICJNSUlEQVRDQ0FtcWdBd0lCQWdJSkFNQjFjc051QTYra01BMEdDU3FHU0liM0RRRUJCUVVBTUhFeEN6QUpCZ05WQkFZVEFsVlRNUkl3RUFZRFZRUUlFd2xVWlc1dVpYTnpaV1V4R0RBV0JnTlZCQW9URDBWNFlXMXdiR1VnUTI5dGNHRnVlVEVRTUE0R0ExVUVBeE1IUlhoaGJYQnNaVEVpTUNBR0NTcUdTSWIzRFFFSkFSWVRaWGhoYlhCc1pVQmxlR0Z0Y0d4bExtTnZiVEFlRncweE16QTBNRFF4TlRJNE16QmFGdzB4TkRBME1EUXhOVEk0TXpCYU1JR1dNUXN3Q1FZRFZRUUdFd0pWVXpFU01CQUdBMVVFQ0JNSlZHVnVibVZ6YzJWbE1SRXdEd1lEVlFRSEV3aEdjbUZ1YTJ4cGJqRVlNQllHQTFVRUNoTVBSWGhoYlhCc1pTQkRiMjF3WVc1NU1SQXdEZ1lEVlFRTEV3ZEZlR0Z0Y0d4bE1SQXdEZ1lEVlFRREV3ZEZlR0Z0Y0d4bE1TSXdJQVlKS29aSWh2Y05BUWtCRmhObGVHRnRjR3hsUUdWNFlXMXdiR1V1WTI5dE1JR2ZNQTBHQ1NxR1NJYjNEUUVCQVFVQUE0R05BRENCaVFLQmdRRGp4dlpYRjMwV0w0b0tqWllYZ1IwWnlhWCt1M3k2K0pxVHFpTmtGYS9WVG5ldDZMeTJPVDZabW1jSkVQbnEzVW5ld3BIb09RK0dmaGhUa1cxM2owNmo1aU5uNG9iY0NWV1RMOXlYTnZKSCtLbyt4dTRZbC95U1BScklQeVRqdEhkRzBNMlh6SWxtbUxxbStDQVMrS0NiSmVINHRmNTQza0lXQzVwQzVwM2NWUUlEQVFBQm8zc3dlVEFKQmdOVkhSTUVBakFBTUN3R0NXQ0dTQUdHK0VJQkRRUWZGaDFQY0dWdVUxTk1JRWRsYm1WeVlYUmxaQ0JEWlhKMGFXWnBZMkYwWlRBZEJnTlZIUTRFRmdRVVZzM3Y1YWZFZE9lb1llVmFqQVFFNHYwV1MxUXdId1lEVlIwakJCZ3dGb0FVeVZJYzN5dnJhNEVCejIwSTRCRjM5SUFpeEJrd0RRWUpLb1pJaHZjTkFRRUZCUUFEZ1lFQWdTL0ZGNUQwSG5qNDRydlQ2a2duM2tKQXZ2MmxqL2Z5anp0S0lyWVMzM2xqWEduNmdHeUE0cXRiWEEyM1ByTzR1Yy93WUNTRElDRHBQb2JoNjJ4VENkOXFPYktoZ3dXT2kwNVBTQkxxVXUzbXdmQWUxNUxKQkpCcVBWWjRLMGtwcGVQQlU4bTZhSVpvSDU3TC85dDRPb2FMOHlLcy9xaktGZUkxT0ZXWnh2QT0iLA0KICAgICAgICAiTUlJRE56Q0NBcUNnQXdJQkFnSUpBTUIxY3NOdUE2K2pNQTBHQ1NxR1NJYjNEUUVCQlFVQU1IRXhDekFKQmdOVkJBWVRBbFZUTVJJd0VBWURWUVFJRXdsVVpXNXVaWE56WldVeEdEQVdCZ05WQkFvVEQwVjRZVzF3YkdVZ1EyOXRjR0Z1ZVRFUU1BNEdBMVVFQXhNSFJYaGhiWEJzWlRFaU1DQUdDU3FHU0liM0RRRUpBUllUWlhoaGJYQnNaVUJsZUdGdGNHeGxMbU52YlRBZUZ3MHhNekEwTURReE5USTFOVE5hRncweU16QTBNREl4TlRJMU5UTmFNSEV4Q3pBSkJnTlZCQVlUQWxWVE1SSXdFQVlEVlFRSUV3bFVaVzV1WlhOelpXVXhHREFXQmdOVkJBb1REMFY0WVcxd2JHVWdRMjl0Y0dGdWVURVFNQTRHQTFVRUF4TUhSWGhoYlhCc1pURWlNQ0FHQ1NxR1NJYjNEUUVKQVJZVFpYaGhiWEJzWlVCbGVHRnRjR3hsTG1OdmJUQ0JuekFOQmdrcWhraUc5dzBCQVFFRkFBT0JqUUF3Z1lrQ2dZRUExc0JuQldQWjBmN1dKVUZUSnk1KzAxU2xTNVo2RERENlV5ZTl2SzlBeWNnVjVCMytXQzhIQzV1NWg5MU11akFDMUFSUFZVT3RzdlBSczQ1cUtORklnSUdSWEtQQXdaamF3RUkyc0NKUlNLVjQ3aTZCOGJEdjRXa3VHdlFhdmVaR0kwcWxtTjVSMUVpbTJnVUl0UmoxaGdjQzlyUWF2amxuRktEWTJybFhHdWtDQXdFQUFhT0IxakNCMHpBZEJnTlZIUTRFRmdRVXlWSWMzeXZyYTRFQnoyMEk0QkYzOUlBaXhCa3dnYU1HQTFVZEl3U0JtekNCbUlBVXlWSWMzeXZyYTRFQnoyMEk0QkYzOUlBaXhCbWhkYVJ6TUhFeEN6QUpCZ05WQkFZVEFsVlRNUkl3RUFZRFZRUUlFd2xVWlc1dVpYTnpaV1V4R0RBV0JnTlZCQW9URDBWNFlXMXdiR1VnUTI5dGNHRnVlVEVRTUE0R0ExVUVBeE1IUlhoaGJYQnNaVEVpTUNBR0NTcUdTSWIzRFFFSkFSWVRaWGhoYlhCc1pVQmxlR0Z0Y0d4bExtTnZiWUlKQU1CMWNzTnVBNitqTUF3R0ExVWRFd1FGTUFNQkFmOHdEUVlKS29aSWh2Y05BUUVGQlFBRGdZRUFEaHdUZWJHazczNXlLaG04RHFDeHZObkVaME54c1lFWU9qZ1JHMXlYVGxXNXBFNjkxZlNINUFaK1Q2ZnB3cFpjV1k1UVlrb042RG53ak94R2tTZlFDMy95R21jVURLQlB3aVo1TzJzOUMrZkUxa1VFbnJYMlhlYTRhZ1ZuZ016UjhEUTZvT2F1TFdxZWhEQitnMkVOV1JMb1ZnUyttYTUvWWNzMEdUeXJFQ1k9Ig0KICAgIF0NCn0.ew0KICAgICJ2ZXJzaW9uIjogIjEuMC4wIiwNCiAgICAiaWQiOiAiMzNjZmY0MTYtZTMzMS00YzlkLTk2OWUtNTM3M2ExNzU2MTIwIiwNCiAgICAiYWN0b3IiOiB7DQogICAgICAgICJtYm94IjogIm1haWx0bzpleGFtcGxlQGV4YW1wbGUuY29tIiwNCiAgICAgICAgIm5hbWUiOiAiRXhhbXBsZSBMZWFybmVyIiwNCiAgICAgICAgIm9iamVjdFR5cGUiOiAiQWdlbnQiDQogICAgfSwNCiAgICAidmVyYiI6IHsNCiAgICAgICAgImlkIjogImh0dHA6Ly9hZGxuZXQuZ292L2V4cGFwaS92ZXJicy9leHBlcmllbmNlZCIsDQogICAgICAgICJkaXNwbGF5Ijogew0KICAgICAgICAgICAgImVuLVVTIjogImV4cGVyaWVuY2VkIg0KICAgICAgICB9DQogICAgfSwNCiAgICAib2JqZWN0Ijogew0KICAgICAgICAiaWQiOiAiaHR0cHM6Ly93d3cueW91dHViZS5jb20vd2F0Y2g_dj14aDRrSWlIM1NtOCIsDQogICAgICAgICJvYmplY3RUeXBlIjogIkFjdGl2aXR5IiwNCiAgICAgICAgImRlZmluaXRpb24iOiB7DQogICAgICAgICAgICAibmFtZSI6IHsNCiAgICAgICAgICAgICAgICAiZW4tVVMiOiAiVGF4IFRpcHMgJiBJbmZvcm1hdGlvbiA6IEhvdyB0byBGaWxlIGEgVGF4IFJldHVybiAiDQogICAgICAgICAgICB9LA0KICAgICAgICAgICAgImRlc2NyaXB0aW9uIjogew0KICAgICAgICAgICAgICAgICJlbi1VUyI6ICJGaWxpbmcgYSB0YXggcmV0dXJuIHdpbGwgcmVxdWlyZSBmaWxsaW5nIG91dCBlaXRoZXIgYSAxMDQwLCAxMDQwQSBvciAxMDQwRVogZm9ybSINCiAgICAgICAgICAgIH0NCiAgICAgICAgfQ0KICAgIH0sDQogICAgInRpbWVzdGFtcCI6ICIyMDEzLTA0LTAxVDEyOjAwOjAwWiINCn0.FWuwaPhwUbkk7h9sKW5zSvjsYNugvxJ-TrVaEgt_DCUT0bmKhQScRrjMB6P9O50uznPwT66oF1NnU_G0HVhRzS5voiXE-y7tT3z0M3-8A6YK009Bk_digVUul-HA4Fpd5IjoBBGe3yzaQ2ZvzarvRuipvNEQCI0onpfuZZJQ0d8
```

서명된 Statement (Signed Statement)
```
{
    "version": "1.0.0",
    "id": "33cff416-e331-4c9d-969e-5373a1756120",
    "actor": {
        "mbox": "mailto:example@example.com",
        "name": "Example Learner",
        "objectType": "Agent"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/experienced",
        "display": {
            "en-US": "experienced"
        }
    },
    "object": {
        "id": "https://www.youtube.com/watch?v=xh4kIiH3Sm8",
        "objectType": "Activity",
        "definition": {
            "name": {
                "en-US": "Tax Tips & Information : How to File a Tax Return "
            },
            "description": {
                "en-US": "Filing a tax return will require filling out either a 1040, 1040A or 1040EZ form"
            }
        }
    },
    "timestamp": "2013-04-01T12:00:00Z",
    "attachments": [
        {
            "usageType": "http://adlnet.gov/expapi/attachments/signature",
            "display": { "en-US": "Signature" },
            "description": { "en-US": "A test signature" },
            "contentType": "application/octet-stream",
            "length": 4235,
            "sha2": "672fa5fa658017f1b72d65036f13379c6ab05d4ab3b6664908d8acf0b6a0c634"
        }
    ]
}
```

__참고(Note):__ 첨부된 서명은 여기에 표시하지 않았다. Attachment 메시지 형식은 [Attachments](#2411-attachments)를 참조한다.

