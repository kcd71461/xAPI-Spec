[English](../xAPI-About.md) | **한국어** · [한국어 README](./README.md) · [용어집](./GLOSSARY.md)

> 이 문서는 xAPI 1.0.3 스펙의 **비공식 한국어 번역**입니다. 원문과 번역의 내용이 다를 경우 [영어 원문](../xAPI-About.md)이 우선합니다.

<a name="experience-api"></a>
# Experience API
<a name="advanced-distributed-learning-adl-co-laboratories"></a>
## Advanced Distributed Learning (ADL) Co-Laboratories

>#### 라이선스 (License)

>"Copyright 2013 Advanced Distributed Learning (ADL) Initiative, U.S. Department of Defense

>Apache License, Version 2.0(이하 "라이선스")에 따라 사용이 허가된다. 라이선스를 준수하지 않는 한 
>이 파일을 사용할 수 없다. 라이선스 사본은 다음에서 얻을 수 있다.
>http://www.apache.org/licenses/LICENSE-2.0

>관련 법률에서 요구하거나 서면으로 합의하지 않는 한, 라이선스에 따라 배포되는 소프트웨어는 명시적이든 
>묵시적이든 어떠한 종류의 보증이나 조건 없이 "있는 그대로(AS IS)" 배포된다. 라이선스에 따른 권한과 
>제한 사항을 규정하는 구체적인 내용은 라이선스를 참조한다."

>이 문서는 국방부 차관보실(준비태세, Office of the Deputy Assistant Secretary of Defense (Readiness)) 
>산하 Advanced Distributed Learning (ADL) Initiative를 지원하기 위해 Experience API 작업 그룹(Working Group) 
>구성원들([CONTRIBUTING.md](../CONTRIBUTING.md#contributors)의 목록 참조)이 작성했다. 
>모든 의견과 문의는 helpdesk@adlnet.gov 로 보내 주기 바란다.  

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

<a name="part-one-about-the-experience-api"></a>
# 1부: Experience API 소개 (Part One: About the Experience API)

<a name="10-introduction"></a>
## 1.0 소개 (Introduction)

Experience API(xAPI)는 학습 경험의 기록과 전달을 용이하게 하는 것을 목표로 하는 기술 스펙이다. 
xAPI는 학습 경험을 기술하기 위한 구조를 명세하고, 이러한 기술 내용을 전자적으로 교환하는 방법을 
정의한다.  

xAPI는 Advanced Distributed Learning (ADL) Initiative의 성과물이다. ADL은 미국의 훈련 및 교육 관리와 
제공을 표준화하고 현대화하기 위해 1997년에 설립되었다. 그 이후로, 공식적이고 구조화된 컴퓨터 기반 훈련을 넘어 
개인의 학습 경험을 추적할 필요성에 대한 인식이 점점 커져 왔다. 
지원자가 어떤 직위에 적합한지, 또는 다양한 업무를 수행할 역량이 있는지를 평가할 때에는 온라인과 오프라인을 
아우르는 폭넓은 공식·비공식 학습 경험을 고려할 필요가 있다. 그런데 이러한 정보는 
대개 매우 다양한 출처에 흩어져 있다.

이러한 필요성에 대한 인식에서 xAPI 커뮤니티와 스펙이 탄생했다. xAPI는 다음을 전제로 한다.
  * 다양한 출처, 플랫폼, 기술에 분산된 학습 경험과 그 성과에 관한 정보를 분석할 수 있어야 할 
  필요가 있다.
  * 이러한 정보를 수집, 저장, 교환하기 위한 공통으로 받아들여지는 프레임워크를 개발하는 것이 
  이를 달성하는 최선의 방법이다.

xAPI의 목표는 다음과 같다.

* 다양한 맥락, 플랫폼, 기술에 걸쳐 기록된 학습 경험과 그 성과를 더 쉽게 이해하고 비교할 수 있도록 
한다.
* 학습 경험에 관한 정보를 생성, 수집, 저장, 처리하는 서비스 간의 상호운용성을 극대화한다.
* 이 스펙을 따르고 구현하는 애플리케이션을 만들고자 하는 사람들에게 지침을 제공한다.
* 이 스펙에 대한 적합성(conformance)을 테스트할 수 있는 기준을 제공한다.

이어지는 문서는 이러한 목표를 달성하도록 설계된 xAPI 스펙을 기술한다. 

<a name="20-how-to-use-this-document"></a>
## 2.0 이 문서의 사용법 (How to Use This Document)

이 문서는 Experience API를 어떻게 구현해야 하는지를 기술하는 공식 문서이다.
이 문서는 이 기술을 구현하는 개인과 조직을 위해 특별히 작성된 기술 문서로, 그러한 개인이 서로 독립적이면서도 
상호운용 가능한 도구, 시스템, 서비스를 개발하도록 하는 것을 의도로 한다. 

다양한 도구, 시스템, 서비스가 아래에 기술된 스펙 집합을 기반으로 하기 때문에, 이 문서에서 사용하는 언어와 
형식은 가능한 한 비기술 독자를 *배려*하고자 한다. 이러한 이유로, Experience API의 특정 측면에 대한 
*상위 수준의 개요*를 제공하는 절에는 **설명**(description) 또는 
**근거**(rationale)라는 표시가 붙어 있다. 이 문서에서 **요구사항**(requirements), **세부 사항**(details), **예제**(examples)로 표시된 항목은 보다 기술적인 내용이다.

이 스펙은 세 부분으로 나뉜다. 1부는 지금 읽고 있는 소개이다. 1부는 배경 지식과 
상위 수준의 요약, 그리고 스펙의 나머지 부분을 읽는 방법에 대한 안내를 제공한다. 

이 스펙의 2부는 이 스펙에서 사용하는 다양한 데이터 객체의 데이터 모델을 정의한다. 
xAPI 데이터 모델에서 가장 중요한 객체는 "Statement" 객체이다. 이 스펙은 Statement 객체의 속성 
("Actor", "Verb", "Object", "Result", "Context" 포함)과 그 속성 값의 구문 규칙 및 
표현 방식을 정의한다. 2부는 스펙을 구현하는 서비스가 일관된 데이터 구조를 따르도록 
보장하는 데 도움이 된다.

이 스펙의 3부는 스펙을 준수하는 서비스 간에 학습 경험에 관한 정보를 주고받을 때 반드시 사용해야 하는 
전송 방법을 기술한다. 여기에는 요청 형식과 예상되는 응답이 포함된다. xAPI의 통신은 
"Learning Record Store"(LRS)가 "콘텐츠"로부터 데이터를 받는 것에 국한되지 않는다는 점에 유의한다. LRS는 
"Learning Record Provider"부터 "Learning Record Consumer", 다른 LRS에 이르기까지 다양한 서비스와 통신할 수 있다. 
xAPI는 REST 소프트웨어 아키텍처 스타일의 지침을 따르므로, 데이터는 HTTP 요청과 응답을 통해 전송된다. 
3부는 또한 LRS와 신뢰할 수 있는 "Client" 간의 신뢰할 수 있는 정보 교환을 가능하게 하는 보안 방법도 정의한다.

<a name="21-must--should--may"></a>
### 2.1 MUST / SHOULD / MAY 
xAPI 스펙에 대한 적합성과 관련하여 MUST, SHOULD, MAY라는 용어로 구분되는 
세 가지 의무 수준이 있다. MUST(또는 MUST NOT) 요구사항을 구현하지 않은 서비스나 시스템은 부적합(non-conformant)하다. 
SHOULD 요구사항을 충족하지 않는 것은 적합성 위반은 아니지만, 스펙의 권고에 어긋난다. 
MAY는 선택 사항을 나타내며, 적합성에 아무런 영향 없이 개발자가 결정할 수 있다. 요구사항을 기술하는 문장 
밖에서 이 용어들을 사용하는 것은 요구사항을 의미하지 않으며, 가능한 한 피한다. 
MUST, SHOULD, MAY, MUST NOT, SHOULD NOT의 완전한 정의는 [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt)에 있다.

SHOULD 뒤에 별표(*)를 붙인 것은 매우 강력한 권고를 나타낸다. 이러한 권고는 향후 버전에서 
MUST 요구사항이 될 예정이다. 이러한 권고를 따르지 않으면 상호운용성이 위협받거나, 
권고의 구체적인 내용에 따라 그 밖의 여러 문제가 발생할 수 있다. 
이러한 권고를 이번 버전에서 MUST 요구사항으로 만들 수 없는 이유는 그렇게 하면 호환성을 깨는 변경(breaking change)이 되기 때문이다. 
xAPI 작업 그룹(Working Group)은 도입자들이 이러한 요구사항을 MUST 요구사항인 것처럼 구현하되, 
그렇게 하지 않을 수도 있는 다른 도입자들도 계속 지원할 것을 강력히 권장한다.

<a name="22-guidelines-for-interpreting-descriptive-text-and-tables"></a>
### 2.2 설명 텍스트와 표의 해석 지침 (Guidelines for Interpreting Descriptive Text and Tables)
경험적으로, 지침이 기술적으로 보이거나 요구사항처럼 보이면 요구사항으로 
해석한다. 이는 특히 길고 상세한 설명과 표에 해당하는데, 이들은 모두 요구사항 목록으로 
분해하면 직관적이지 않거나 길어지기 때문이다.

이 스펙 전반에서 속성, 파라미터 등의 목록에 대한 요구사항을 정의하는 데 표를 사용한다.
표는 어떤 속성이 필수, 권장, 선택인지를 정의한다. 일반적으로 "선택(optional)"이라는 개념은 
객체를 생성하는 서비스에 관한 것이며, 객체를 수신하고 해석하는 서비스는 그 객체의 모든 
속성을 해석할 수 있어야 한다. 속성이 선택인 경우가 많은 것은 해당 데이터가 모든 맥락에서 관련 있는 것은 아니기 때문이다. 
특정 맥락에서 데이터가 관련이 있다면, 해당 속성을 채울 것으로 기대한다.

선택 속성이나 파라미터가 권장 또는 필수 속성을 가진 객체를 포함하는 경우, 
그 속성들은 이를 포함하는 속성이나 파라미터가 사용될 때에만 권장/필수가 된다.

구현 방법을 보여 주기 위해 스펙 전반과 부록에 예제를 제공한다. 이 예제의 내용은 
스펙의 요구사항을 설명하기 위한 가상의 것이며, 예제에서 사용한 특정 학습 경험을 추적하는 
모범 사례를 항상 보여 주는 것은 아니다. 예제는 
요구사항을 해석하는 데 참고할 수 있지만, 요구사항보다 우선하지는 않는다. 

스펙에 구현의 특정 측면에 관한 요구사항이 없는 경우, 
해당 세부 사항은 이 스펙의 범위 밖에 있는 것으로 간주할 수 있다. 합리적인 접근 방식을 정하는 것은 
구현자의 몫이다. 이 스펙은 모호함을 피하려 하며, 특정 영역에 요구사항이 없더라도 
대개 그 근거를 제시한다.

<a name="30-serialization-and-javascript-object-notation-json"></a>
## 3.0 직렬화와 JSON (Serialization and JavaScript Object Notation (JSON))

직렬화(serialization)란 데이터 객체와 구조를 저장이나 전송을 위한 형식으로 변환하되, 그 직렬화 결과로부터 
원래의 데이터 객체를 다시 만들어 낼 수 있도록 하는 과정이다. 경우에 따라 하나의 데이터를 둘 이상의 방식으로 
직렬화할 수도 있다. 예를 들어, 참(true)에 해당하는 값을 가진 boolean 속성은 사용하는 직렬화 방식에 따라 
`true` 또는 `1`로 표현될 수 있다. 

xAPI는 직렬화에 JSON의 규칙을 따른다(따라서 boolean 값은 `true` 또는 `false`로 표현된다). 이 스펙에서 
정의하는 객체를 XML 같은 다른 직렬화 방식으로 표현하는 것도 가능할 수 있다. 그러나 이는 
이 스펙의 범위 밖이며, 이 스펙에서 정의하는 객체를 JSON 이외의 방식으로 표현하는 것은 
적합하지 않다(not conformant). 

JSON의 규칙 안에서도 데이터를 직렬화하는 방식에는 여러 변형이 있을 수 있으며, 특히 시간에 관한 데이터가 
그렇다. xAPI의 여러 기능은 시스템이 두 Statement가 동등한지 판단할 수 있다는 것에 의존하므로 
이 점은 중요하다. 이로 인해 영향을 받는 Statement 속성에 관한 자세한 내용은 [불변성과 예외](./xAPI-Data.md#231-statement-immutability)를 
참조한다. 

JSON에서는 객체의 속성이 빈 객체를 포함하는 것을 허용한다. xAPI에서는 이를 권장하지 않는다. Statement가 
어떤 속성에 관한 데이터를 담을 의도가 없다면, 해당 속성을 아예 사용하지 않을 것으로 기대한다. 
모든 필수 속성은 반드시 값을 포함해야 한다. 


<a name="40-definitions"></a>
## 4.0 정의 (Definitions)  

* [Activity (활동)](#def-activity)
* [Activity Provider (AP) (액티비티 제공자)](#def-activity-provider)
* [Actor (행위자)](#def-actor)
* [Application Programming Interface (API) (응용 프로그래밍 인터페이스)](#def-api)
* [Authentication (인증)](#def-authentication)
* [Authorization (인가)](#def-authorization)
* [Community of Practice (실천 공동체)](#def-community-of-practice)
* [Document Profile Resource (Document Profile 리소스)](#def-document-profile)
* [Endpoint (엔드포인트)](#def-endpoint)
* [Experience API (xAPI) (경험 API)](#def-experience-api)
* [Immutable (불변)](#def-immutable)
* [Internationalized Resource Identifier (IRI) (국제화 자원 식별자)](#def-iri)
* [Internationalized Resource Locator (IRL) (국제화 자원 위치 지정자)](#def-irl)
* [Inverse Functional Identifier (역함수 식별자)](#def-inverse-functional-identifier)
* [Learning Experience (학습 경험)](#def-learning-experience)
* [Learning Management System (LMS) (학습 관리 시스템)](#def-learning-management-system)
* [Learning Record (학습 기록)](#def-learning-record)
* [Learning Record Consumer (LRC) (학습 기록 소비자)](#def-learning-record-consumer)
* [Learning Record Provider (LRP) (학습 기록 제공자)](#def-learning-record-provider)
* [Learning Record Store (LRS) (학습 기록 저장소)](#def-learning-record-store)
* [Metadata Consumer (메타데이터 소비자)](#def-metadata-consumer)
* [Metadata Provider (메타데이터 제공자)](#def-metadata-provider)
* [Persona (페르소나)](#def-persona)
* [Profile (프로파일)](#def-profile)
* [Registration (등록)](#def-registration)
* [Representational State Transfer (REST) (표현 상태 전송)](#def-rest)
* [Service (서비스)](#def-service)
* [Statement (진술문)](#def-statement)
* [Tin Can API (TCAPI) (틴 캔 API)](#def-tcapi)
* [Verb (동사)](#def-verb)
* [Vocabulary (어휘)](#def-vocabulary)

<a name="def-activity"></a>

__Activity (활동)__: "나는 이것을 했다(I did this)"에서 "이것(this)"에 해당하는 Object의 한 유형으로, 
Actor가 상호작용한 대상이다. Activity는 Verb와 의미 있게 결합하여 추적되는 교육, 경험, 수행의 
단위일 수 있다. Activity는 넓게 해석되므로, 
의자(실제 또는 가상)와 같은 유형의 물체도 Activity가 될 수 있다. "Anna가 
케이크 레시피를 시도했다"라는 Statement에서 xAPI Statement 관점의 Activity는 레시피이다. 
Activity의 다른 예로는 책, e-러닝 과정, 하이킹, 회의 등이 있다.

<a name="def-activity-provider"></a>

__Activity Provider (AP) (액티비티 제공자)__: 현재는 Learning Record Provider라고 부른다. 이 명칭 변경은 
활동 자체가 항상 소프트웨어의 책임인 것은 아니며, 소프트웨어는 추적 부분만 책임진다는 점을 구분하기 위한 것이다. 

<a name="def-actor"></a>

__Actor (행위자)__: Statement를 사용해 추적되는, Activity 안에서 행동을 수행하는 개인 또는 그룹의 
표현이다. "나는 이것을 했다(I did this)"에서 "나(I)"에 해당한다.

<a name="def-api"></a>

__Application Programming Interface (API) (응용 프로그래밍 인터페이스)__: 소프트웨어 애플리케이션이나 도구에 
접근할 수 있도록 만들어진 규칙과 표준의 집합이다.  

<a name="def-authentication"></a>

__Authentication (인증)__: 신원을 확인하는 개념이다. 인증을 통해 "신뢰할 수 있는" 
두 당사자 간의 상호작용이 가능해진다.

<a name="def-authorization"></a>

__Authorization (인가)__: 역할에 기반하여 권한을 부여하는 것으로, 한 당사자가 다른 당사자로부터 
"신뢰받게" 만드는 과정이다.

<a name="def-client"></a>

__Client (클라이언트)__: 요청을 통해 상호작용할 수 있는 모든 개체를 가리킨다. 예로는 
Learning Record Provider, Learning Record Consumer, Learning Record Store(LRS), Learning 
Management System(LMS) 등이 있다.

<a name="def-community-of-practice"></a>

__Community of Practice (CoP) (실천 공동체)__: 공통의 대의, 역할 또는 목적으로 연결되어 공통의 방식으로 활동하는 
실무자 그룹이다. CoP는 특정 지식 도메인이나 사용 사례 안에서 xAPI를 구현하는 데 초점을 맞춘다. CoP나 독립 개발자는 
도메인별 어휘(vocabulary), 프로파일(profile), 레시피(recipe)를 만들 수 있다. 이러한 실천에는 대개 사용 사례를 정의하고, 
CoP 안에서 선호될 수 있는 다양한 어휘 용어, 동의어, 기타 관련 메타데이터를 선별·관리(curating)하는 작업이 포함된다. 또한 
다른 CoP나 xAPI 커뮤니티 참여자가 이미 발행한 기존 어휘, 프로파일, 레시피를 재사용할 수도 있다.

<a name="def-document-profile"></a>

__Document Profile Resource (Document Profile 리소스)__: 학습자나 Activity에 관한 정보를 보관하는 구성 요소로, 일반적으로 
교육 시스템 구성 요소에 의미가 있는 이름/문서 쌍의 형태로 보관한다. [Profile](#def-profile)과 혼동하지 않도록 주의한다.

<a name="def-endpoint"></a>

__Endpoint (엔드포인트)__: 서비스 지향 아키텍처(service-oriented-architecture)에서의 진입점이다. xAPI는 통신이 이루어지는 
IRI를 엔드포인트로 정의함으로써 리소스에 이 접근 방식을 그대로 반영한다.

<a name="def-experience-api"></a>

__Experience API (xAPI) (경험 API)__: 독립적인 소프트웨어 프로그램들이 학습 경험에 관한 정보를 교환하고 활용할 수 있도록, 
학습 경험을 정의하고 형식화하고 교환하는 방법을 결정하는, 이 문서에 명시된 규칙의 
모음이다.

<a name ="def-immutable"></a>

__Immutable (불변)__: 변경할 수 없는 것을 기술하는 형용사이다. 일부 예외를 제외하면 xAPI의 Statement는 
불변이다. 이를 통해 Statement가 여러 LRS 간에 공유될 때 Statement의 여러 사본이 동일하게 유지되도록 보장한다.

<a name="def-iri"></a>

__Internationalized Resource Identifier  (IRI) (국제화 자원 식별자)__: IRL일 수도 있는 고유 식별자이다. Verb, Activity, 
Activity 유형(activity type) 같은 객체를 식별하는 데 사용된다. URI와 달리, IRI는 국제 언어를 지원하기 위해 
ASCII 문자 집합 밖의 일부 문자를 포함할 수 있다. 

IRI는 항상 스킴(scheme)을 포함한다. 이는 이 표준의 요구사항이 아니라 
[RFC 3987](http://www.ietf.org/rfc/rfc3987.txt)에 따른 IRI 정의의 일부이다. 때때로 "상대 IRI(relative IRI)"라고 불리는 것은 IRI가 아니다.

<a name="def-irl"></a>

__Internationalized Resource Locator (IRL) (국제화 자원 위치 지정자)__: 이 문서의 맥락에서 IRL은 (IRI를 URI로 변환하는 
규칙에 따라) URI로 변환했을 때 URL이 되는 IRI이다. 

<a name="def-inverse-functional-identifier"></a>

__Inverse Functional Identifier (역함수 식별자)__: 특정 페르소나(persona)나 Group에 고유한 식별자이다.

<a name="def-learning-experience"></a>

__Learning Experience (학습 경험)__: 학습과 관련된 사건이다. 그 형태는 매우 다양하다.  
예로는 책 읽기, 온라인 과정 수강, 현장 학습 참가, 자기 주도적 연구 수행, 
수료한 과정의 수료증 취득 등이 있다.

<a name="def-learning-management-system"></a>

__Learning Management System (LMS) (학습 관리 시스템)__: "하나 이상의 과정을 한 명 이상의 학습자에게 운영하는 데 사용되는 소프트웨어 패키지. 
LMS는 일반적으로 학습자가 스스로 인증하고, 과정에 등록하고, 과정을 이수하고, 평가를 
치를 수 있게 해 주는 웹 기반 시스템이다"(Learning Systems Architecture Lab의 정의). 이 문서에서 LMS는 
시스템 안에서 사용자가 어떻게 "신뢰할 수 있는" 사용자로 식별되어 그 시스템의 학습 경험에 접근할 수 있는지를 보여 주는 예로 사용된다.

<a name="def-learning-record"></a>

__Learning Record (학습 기록)__: xAPI의 규칙에 따라 형식화된 학습 경험의 기록이다. Learning Record는
Statement, 문서(document) 및 그 일부를 포함하여 여러 형태를 띤다. 이 정의는 모든 것을 포괄하도록 의도되었다.

<a name="def-learning-record-consumer"></a>

__Learning Record Consumer (LRC) (학습 기록 소비자)__: 해석, 분석, 변환, 배포, 집계 등 데이터를 처리할 목적으로 
Learning Record Store의 데이터에 접근하는 xAPI Client이다.

<a name="def-learning-record-provider"></a>

__Learning Record Provider (LRP) (학습 기록 제공자)__: Learning Record Store로 데이터를 전송하는 xAPI Client이다. Learning Record 
Provider는 학습 경험(Learning Experience)의 일부로서 학습자를 관찰하면서 Learning Record를 생성하는 경우가 많다.

<a name="def-learning-record-store"></a>

__Learning Record Store (LRS) (학습 기록 저장소)__: Learning Record를 수신하고 저장하며 Learning Record에 대한 접근을 제공하는 
책임을 지는 서버(즉, 웹 요청을 수신하고 처리할 수 있는 시스템)이다.

<a name="def-metadata-consumer"></a>

__Metadata Consumer (메타데이터 소비자)__: 이 스펙 안에서 사용되는 IRI가 나타내는 의미를 알아내려 하거나, IRI에 관한 메타데이터를 
조회하는 사람, 조직, 소프트웨어 프로그램 또는 그 밖의 것이다. LRS는 메타데이터 소비자일 수도 있고 아닐 수도 있다. 

<a name="def-metadata-provider"></a>

__Metadata Provider (메타데이터 제공자)__: 이 스펙 안에서 사용될 IRI를 새로 만들거나, IRI에 관한 메타데이터를 
호스팅하는 사람, 조직, 소프트웨어 프로그램 또는 그 밖의 것이다. 

<a name="def-persona"></a>

__Persona (페르소나)__: Actor를 고유하게 정의하는 하나 이상의 표현의 집합이다. 개념적으로 이는 
"집 이메일"과 "회사 이메일"을 가지는 것과 비슷하다. 둘 다 같은 사람이지만, 데이터나 연관 관계 등이 서로 다르다.

<a name="def-profile"></a>

__Profile (프로파일)__: 특정 맥락에서 xAPI를 구현하기 위한 구체적인 규칙과 문서의 집합이다. 프로파일은 일반적으로 
특정 용어 어휘를 제공하는데, 그중 일부는 해당 프로파일을 위해 특별히 만들어지고 일부는 다른 어휘에서 참조된다. 
때로는 하나의 프로파일이 상황에 따라 여러 어휘를 제공하기도 하고, 때로는 누군가가 프로파일을 만들지 않고 
여러 출처에서 어휘를 선별·관리(curate)하기도 한다. [Document Profile Resource](#def-document-profile)와 혼동하지 않도록 주의한다.

<a name="def-registration"></a>

__Registration (등록)__: Actor가 특정 Activity를 경험하는 하나의 인스턴스이다.

<a name="def-rest"></a>

__Representational State Transfer (REST) (표현 상태 전송)__: 네트워크 기반 웹 서비스를 설계하기 위한 아키텍처이다.
HTTP 메서드에 의존하며, 현재의 웹 모범 사례를 활용한다.

<a name="def-service"></a>

__Service (서비스)__: 분산 학습 프로세스의 하나 이상의 측면을 담당하는 소프트웨어 구성 요소이다. 
LMS는 일반적으로 여러 서비스를 결합하여 완전한 학습 경험을 설계한다.

<a name="def-statement"></a>

__Statement (진술문)__: xAPI에서 Learning Record로 추적할 모든 종류의 경험이나 사건에 대한 증거를 보여 주는 
데이터 구조이다. 각각 특정 시점의 사건을 나타내는 여러 Statement의 집합을 사용하여 
학습 경험의 전체 세부 내용을 추적할 수 있다.  

<a name="def-tcapi"></a>

__Tin Can API (TCAPI) (틴 캔 API)__: 이 문서에서 정의하는 API의 이전 이름으로, Experience API를 비공식적으로 
지칭할 때 자주 사용된다.  

<a name="def-verb"></a>

__Verb (동사)__: Statement 안에서 Actor가 Activity 안에서 수행하는 행동이다. 
Verb는 "나는 이것을 했다(I did this)"에서 "했다(did)"를 나타낸다.

<a name="def-vocabulary"></a>

__Vocabulary (어휘)__: 특정 도메인에서 정보에 이름을 붙이거나 분류하기 위해 CoP가 사용하는 용어의 목록 또는 모음이다. 
어휘를 사용하면 모든 사람이 같은 의미를 나타내기 위해 같은 단어를 사용하도록 보장할 수 있다. 어휘에 관한 자세한 
정보는 [xAPI Vocabulary Companion Specification](https://github.com/adlnet/companion-specification-for-xapi-vocabularies/blob/master/SUMMARY.md)을 참조한다.


<a name="50-xapi-components"></a>
## 5.0 xAPI 구성 요소 (xAPI Components)

이 절에서는 xAPI의 여러 구성 요소가 어떻게 맞물리는지를 설명하고 그림으로 보여 준다.  

<a name="tracking-experiences"></a>
##### 경험 추적 (Tracking Experiences)

<a name="figure-1-data-flow-in-xapi"></a>
###### 그림 1: xAPI의 데이터 흐름 (Figure 1: Data Flow in xAPI)
![xAPI의 데이터 흐름](../xAPIDataFlow.jpg)

<details>
<summary>그림 속 문구 번역</summary>

1. 학습자가 학습 경험을 한다 (THE LEARNER HAS A LEARNING EXPERIENCE)
2. 이 경험은 Learning Record Provider(학습 기록 제공자)가 추적하며 (WHICH IS TRACKED BY A LEARNING RECORD PROVIDER)
3. Learning Record Provider는 기록을 생성해 Learning Record Store(학습 기록 저장소)로 전송하고 (WHICH CREATES AND SENDS RECORDS TO THE LEARNING RECORD STORE)
4. Learning Record Store는 학습자에 관한 이 기록들을 저장한다 (WHICH STORES THESE RECORDS ABOUT THE LEARNER)
5. Learning Record Consumer(학습 기록 소비자)는 LRS에 접근해 학습 기록을 가져올 수 있다 (A LEARNING RECORD CONSUMER CAN ACCESS THE LRS TO ACQUIRE LEARNING RECORDS)

</details>

그림 1은 학습 경험의 추적을 보여 준다. 학습자가 어떤 학습 경험을 한다. 이 경험은 
온라인 과정에서 일어날 수도 있고, 업무 중에 일어날 수도 있으며, 여가 활동의 일부일 수도 있다. 사실상 무엇이든 될 수 있다. 이 경험은 
학습자를 대신하여, 신뢰할 수 있는 Learning Record Provider(LRP)가 추적한다. Learning Record Provider는 경험과 학습자 
사이의 신뢰 관계를 책임질 수도 있다. 여기에는 학습자를 위해 콘텐츠를 실행(launch)하고 
콘텐츠와 관련된 디지털 권리를 관리하는 것까지 포함될 수 있다.  

Learning Record Provider는 Learning Record를 생성하여 하나 이상의 Learning Record Store(LRS)로 전송한다. LRS는
Learning Record를 저장하고, 인가된 모든 Client가 이를 이용할 수 있게 한다. Learning Record Consumer(LRC)는 
Learning Record에 접근하여 이를 활용하는 Client의 한 유형이다.

<a name="activity-data-and-metadata"></a>
##### Activity 데이터와 메타데이터 (Activity Data and Metadata)

<a name="figure-2-xapi-activity-data-and-metadata"></a>
###### 그림 2: xAPI Activity 데이터와 메타데이터 (Figure 2: xAPI Activity Data and Metadata)
![xAPI Activity 데이터와 메타데이터](../xAPIMetadata.jpg)

<details>
<summary>그림 속 문구 번역</summary>

* **xAPI Statement**: Actor | Verb | Activity | 추가 속성 (Additional Properties)
* Activity → **Metadata**(메타데이터): Statement 안에 포함할 수 있다 (May include)
* Activity → **Authoritative Metadata**(권위 있는 메타데이터): 참조할 수 있다 (May reference)
* **Metadata Provider**(메타데이터 제공자) → Authoritative Metadata: 관리 권한을 가진다 (Has control over)
* Authoritative Metadata → LRS의 **Activity Definition**: 갱신하는 데 사용될 수 있다 (Can be used to update)
* **Metadata Consumer**(메타데이터 소비자) → Authoritative Metadata, LRS의 **Activities Resource**: 접근한다 (Accesses)
* **Learning Record Store**: Activity Definition, Activities Resource, Statements Resource

</details>

(IRI로 고유하게 식별되는) 하나의 Activity가 어떻게 정의되고 기술되는지를 이해하는 것은 xAPI의 핵심 개념이다. 
그림 2는 이 과정을 보여 준다. (Statement의 일부로서) Activity는 Statement 자체 안에서 채울 수 있는 
메타데이터 속성을 가진다. 이는 Statement의 Activity Definition에서 이루어진다. 각 Activity의 id는 IRI이며, 
그 IRI가 가리키는(resolve) 위치에도 메타데이터가 있을 수 있다. IRI가 가리키는 위치의 메타데이터는 모두 Metadata 
Provider의 통제 아래에 있다. Metadata Provider는 또한 IRI가 영구적이며 올바르게 해석(resolve)되도록 보장할 책임이 있다.

IRI가 가리키는 위치에 있는 메타데이터는 모두 권위 있는(authoritative) 메타데이터 출처이며, Statement로부터 받은 것보다 우선하여 
LRS가 보유한 Activity 메타데이터의 정규(canonical) 버전(LRS의 Activity Definition)을 채우는 데 사용될 수 있다. 
Metadata Consumer는 권위 있는 버전을 얻기 위해 IRI를 통해 메타데이터에 접근하거나, 정규 버전을 얻기 위해 Activities 리소스(Activities Resource)를 
조회할 수 있다.

<a name="agent-and-persona-management"></a>
##### Agent와 페르소나 관리 (Agent and Persona Management)

<a name="figure-3-xapi-agent-and-persona-management"></a>
###### 그림 3: xAPI Agent와 페르소나 관리 (Figure 3: xAPI Agent and Persona Management)
![xAPI Agent와 페르소나 관리](../xAPIPersonas.jpg)

<details>
<summary>그림 속 문구 번역</summary>

* **학습자(LEARNER)**: 학습자는 학습하는 동안 여러 기기로 다양한 계정에 접근한다 (The Learner accesses a variety of accounts using different devices as they learn)
* 여러 애플리케이션과 계정에서 나온 xAPI 데이터는 서로 다른 "페르소나"에서 온 것으로 LRS에 전송된다 (xAPI data, from different applications and accounts, is sent to the LRS as coming from different "personas")
* **Learning Record Store**: Agents Resource, Agent Profile Resource, Statements Resource
* LRS는 각 페르소나의 데이터가 묶여 있도록 Statement를 (Actor별로) 정리한다 (The LRS organizes Statements (by Actor) to keep each persona's data bundled)
* **LRS에 담긴 STATEMENTS** (STATEMENTS contained in the LRS): 소셜(Social) / 업무(Work) / 여가(Recreation)
* LRS는 서로 다른 페르소나를 다시 하나의 Person Object로 결합할 수 있다 (The LRS can combine the different personas back into a single Person Object)
* **PERSON OBJECT**: 소셜(Social) / 업무(Work) / 여가(Recreation)

</details>

xAPI는 자신의 개인 데이터에 대한 선택적 접근을 허용하기 위한 프레임워크를 제공한다. 이는 
페르소나(persona)라고 부르는 것을 관리함으로써 이루어진다. xAPI에서 각 페르소나는 "나는 이것을 했다(I did this)"의 "나(I)"를 나타내며, 
논리적으로 Statement의 주어이다. xAPI의 각 
Agent 또는 Group은 하나의 페르소나에 대응한다. LRS로 Learning Record를 전송하는 학습자는 자신과 연관된 여러 페르소나(Agent)를 
가질 수 있다. 

그림 3에서 학습자는 여러 서비스에 접근한다. 이 중 일부는 직장에서, 다른 일부는 집에서 사용된다. 일부는 
사교적 목적으로, 다른 일부는 교육적 또는 직업적 목적으로 사용된다. 따라서 이러한 서비스 안에서는 여러 페르소나가 
함께 작동하고 있다. 이 서비스들은 각각 LRS로 데이터를 전송한다. 그 결과, 같은 학습자의 서로 다른 
세 페르소나로부터 나온 Statement가 존재하게 된다. 

LRS는 각 페르소나의 모든 정보를 하나의 "Person" Object로 집계할 수 있다. 이 객체는 
[Agents 리소스](./xAPI-Communication.md#24-agents-resource)를 통해 LRS에서 조회할 수 있다. 이러한 
여러 페르소나가 한 사람에게 속한다는 것을 LRS가 어떻게 아는지는 이 스펙의 범위 밖이며, LRS가 취할 수 있는
여러 가지 접근 방식이 있다. 일부 LRS에는 페르소나를 연관시키는 메커니즘이 전혀 없을 수도 있다. 


<a name="60-extending-xapi"></a>
## 6.0 xAPI 확장 (Extending xAPI)

xAPI는 몇 가지 방법으로 확장할 수 있다. 가장 주목할 만한 것은 Statement 확장(extension)으로, Statement 안에서 큰 유연성을 제공한다. 
실천 공동체(Community of Practice)는 각자의 특정 사용 사례에서 확장을 어떻게 사용할지 합의하고, 가능한 한 
프로파일을 활용하는 것이 권장된다. 구현 세부 사항은 [4.1 Extensions](./xAPI-Data.md#41-extensions)에서 다룬다.

About 리소스(About Resource)는 xAPI가 확장을 지원하는 또 다른 사례이다. LRS는 이 스펙을 넘어서는 기능이나 
동작을 알리는 것이 유용하다고 판단할 수 있다. LRS는 About 리소스에 대한 확장을 사용하여 이러한 소통을 원활하게 할 수 있다.

마지막으로, 구현되는 리소스의 집합이 이 문서에 의해 제한될 것으로 예상하지 않는다. 이 스펙에 나열된 것 
이외의 리소스도 구현할 수 있으며, 이 스펙에서 정의한 리소스와 공존할 수 있다.


<a name="70-profiles-vocabularies-and-communities-of-practice"></a>
## 7.0 프로파일, 어휘, 실천 공동체 (Profiles, Vocabularies, and Communities of Practice)

xAPI는 Statement의 구조를 엄격하게 정의하지만, 그 구조의 내용에 대해서는 매우 유연하다. 예를 들어, 
스펙은 모든 Statement가 "verb" 속성을 가지도록 요구하지만, 그 속성의 값은 제한하지 않는다. 어떤 Verb든 
사용할 수 있다. 이러한 유연성 덕분에 xAPI는 스펙 작성자가 예상하지 못한 미래의 사용 사례를 포함하여 
어떤 맥락에서든 사용될 수 있다.

[실천 공동체(Communities of Practice, CoP)](#def-community-of-practice)는 해당되는 곳마다 고유 식별자를 제공함으로써, 
자신의 프로파일에서 사용할 Verb, Activity 유형, 맥락 관계(contextual relationship), 확장 등을 
정의하는 것으로 의도되어 있다. CoP는 이러한 식별자와 
그 메타데이터를 [어휘(Vocabulary)](#def-vocabulary)로 정의한다. 프로파일은 다루고자 하는 특정 사용 사례를 위해 
xAPI에 더하여 구현할 규칙과 어휘의 집합이다. 이러한 공동체가 존재하고 모범 사례를 공유하는 것은 매우 중요하다. 
어휘 발행에 관한 자세한 정보는 [Vocabulary Companion Specification](https://adl.gitbooks.io/companion-specification-for-xapi-vocabularies/content)과 [Vocabulary Primer](https://adl.gitbooks.io/experience-xapi-vocabulary-primer/content/) 문서를 참조한다.

프로파일은 해당 프로파일을 구현하는 모든 Statement를 가리키기 위해 Statement의 context 안에서 고유한 "category"를 
사용하는 것이 권장된다. 프로파일의 한 예로 [cmi5](https://github.com/AICC/CMI-5_Spec_Current)가 있으며, 
이는 전통적인 단일 학습자, 단일 온라인 학습 사용 사례를 위해 설계되었다. cmi5 Statement 예제는 
[부록 B: cmi5 예제](#appendix-b-cmi5-example)에서 볼 수 있다.

같은 문제를 해결하는 방법을 너무 많이 만들면 유사한 도메인에서 파편화가 일어나 상호운용성을 해칠 수 있으므로, 
노력의 중복을 피하기 위해 CoP를 적극 권장한다. 의료 분야 CoP의 
예로는 [MedBiquitous Learning Experience Working Group](http://groups.medbiq.org/medbiq/display/XIG/Learning+Experience+Group+Home)이 있다.


<a name="appendices"></a>
## 부록 (Appendices)

<a name="appendix-a-revision-history"></a>
### 부록 A: 개정 이력 (Appendix A: Revision History)
<a name="08-project-tin-can-api-deliverable-to-09-march-31-2012"></a>
###### 0.8(Project Tin Can API 산출물)에서 0.9로 (2012년 3월 31일) (0.8 (Project Tin Can API Deliverable) to 0.9 (March 31, 2012))  
  
Project Tin Can API를 납품한 Rustici Software는 2012년 4월 킥오프 회의(Kickoff Meeting) 이전에 
API를 수정했다. 이 회의에서 그 변경 사항을 현재 스펙에 반영하고 
0.9로 개정하기로 의결했다.

<a name="090-to-095-august-31-2012"></a>
###### 0.90에서 0.95로 (2012년 8월 31일) (0.90 to 0.95 (August 31, 2012))  

"핵심(Core)" Verb와 Activity 유형이 스펙에서 제거되었다. 결과(result), 맥락(context), 
상호작용(interaction), Activity Definition에서 이러한 Verb를 참조하던 부분도 
제거되었다. 구현자는 자체 Verb를 만들기보다 커뮤니티에서 정의한 
Verb를 우선 사용하도록 권장되었다.
- Verb, Activity 유형, 확장 키가 이제 URI이다.
- 그 밖의 일부 구현 세부 사항과 범위에 관한 문구를 재구성하고 추가했다.
- Agent를 사람 중심(person-centric) 관점에서 페르소나 중심(persona-centric) 관점으로 바꾸었다.
- FOAF(Friend of a Friend) Agent 병합 요구사항이 제거되었다.
- Agent Object는 이제 고유 식별 속성을 최소 1개가 아니라 정확히 1개 가진다.

<a name="095-to-100-april-26-2013"></a>
###### 0.95에서 1.0.0으로 (2013년 4월 26일) (0.95 to 1.0.0 (April 26, 2013)) 
다음을 포함한 다양한 개선과 명확화:
- Attachment 추가
- Activity 메타데이터를 이제 XML이 아닌 JSON으로 저장
- Statement 무효화(voiding) 방식 변경
- Document API(이후 Document 리소스로 이름 변경)의 명확화 및 명명
- Statement API 조회 방식 변경
- 서명된 Statement(Signed Statements)

[0.95...1.0.0](https://github.com/adlnet/xAPI-Spec/compare/0.95-spec...1.0.0)

<a name="100-to-101-october-1-2013"></a>
###### 1.0.0에서 1.0.1로 (2013년 10월 1일) (1.0.0 to 1.0.1 (October 1, 2013))
다음을 포함한 명확화와 추가 예제:
- 여러 오타 수정
- 부록에 추가 예제 수록

[1.0.0...1.0.1](https://github.com/adlnet/xAPI-Spec/compare/1.0.0...1.0.1)

<a name="101-to-102-october-1-2014"></a>
###### 1.0.1에서 1.0.2로 (2014년 10월 1일) (1.0.1 to 1.0.2 (October 1, 2014))
- 표에 선택/필수(optional/required) 표시 추가
- Interaction 구성 요소(component)에 누락된 표 제목 추가
- attachments에서 예/아니오(yes/no)를 필수/선택(required/optional)으로 변경
- 'moreInfo' 속성의 의도 명확화

[1.0.1...1.0.2](https://github.com/adlnet/xAPI-Spec/compare/1.0.1...1.0.2)

<a name="102-to-103-september-21-2016"></a>
###### 1.0.2에서 1.0.3으로 (2016년 9월 21일) (1.0.2 to 1.0.3 (September 21, 2016))
- 문서를 세 부분으로 전면 재구성
- 매우 많은 부분의 명확화
- 정의를 약간 수정하고 대폭 명확화
- SCORM에 대한 역참조 제거
- 설명 텍스트와 다이어그램 추가
- Statement API와 Document API의 이름을 Statement 리소스(Statement Resource)와 Document 리소스(Document Resources)로 변경

[1.0.2...1.0.3](https://github.com/adlnet/xAPI-Spec/compare/1.0.2...1.0.3)

<a name="appendix-b-cmi5-example"></a>
### 부록 B: cmi5 예제 (Appendix B: cmi5 Example) 

다음 예제는 cmi5 실천 공동체(Community of Practice)를 따르는 Statement를 보여 준다. 확장(extensions)과 
"category" contextActivities의 사용법을 보여 준다.

```
{  
  "id":"2a41c918-b88b-4220-20a5-a4c32391a240",
  "actor":{  
    "objectType":"Agent",
    "name":"Gert Frobe",
    "account":{  
      "homePage":"http://example.adlnet.gov",
      "name":"1625378"
    }
  },
  "verb":{  
    "id":"http://adlnet.gov/expapi/verbs/failed",
    "display":{  
      "en-US":"failed"
    }
  },
  "object":{  
    "id":"https://example.adlnet.gov/AUidentifier",
    "objectType":"Activity"
  },
  "result":{  
    "score":{  
      "scaled":0.65,
      "raw":65,
      "min":0,
      "max":100
    },
    "success":false,
    "duration":"PT30M",
    "extensions":{  
      "https://w3id.org/xapi/cmi5/result/extensions/progress":100
    }
  },
  "context":{  
    "registration":"ec231277-b27b-4c15-8291-d29225b2b8f7",
    "contextActivities":{  
      "category":[  
        {  
       	  "id":"https://w3id.org/xapi/cmi5/context/categories/moveon"
        },
        {  
          "id":"https://w3id.org/xapi/cmi5/context/categories/cmi5"
        }
      ]
    },
    "extensions":{  
      "https://w3id.org/xapi/cmi5/context/extensions/sessionid":"458240298378231"
    }
  },
  "timestamp":"2012-06-01T19:09:13.245+00:00"
}
```

