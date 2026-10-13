[English](../xAPI-Communication.md) | **한국어** · [한국어 README](./README.md) · [용어집](./GLOSSARY.md)

> 이 문서는 xAPI 1.0.3 스펙의 **비공식 한국어 번역**입니다. 원문과 번역의 내용이 다를 경우 [영어 원문](../xAPI-Communication.md)이 우선합니다.

<a name="experience-api"></a>
# Experience API
<a name="advanced-distributed-learning-adl-co-laboratories"></a>
## Advanced Distributed Learning (ADL) Co-Laboratories

>#### 라이선스 (License)

>"Copyright 2013 Advanced Distributed Learning (ADL) Initiative, 미국 국방부(U.S. Department of Defense)

>Apache License, Version 2.0(이하 "라이선스")에 따라 라이선스가 부여된다. 라이선스를 준수하지 않는 한 
>이 파일을 사용할 수 없다. 라이선스 사본은 다음에서 얻을 수 있다.
>http://www.apache.org/licenses/LICENSE-2.0

>관련 법률에서 요구하거나 서면으로 합의하지 않는 한, 라이선스에 따라 배포되는 소프트웨어는 
>명시적이든 묵시적이든 어떠한 종류의 보증이나 조건 없이 "있는 그대로(AS IS)" 배포된다. 라이선스에 따른 
>권한 및 제한을 규율하는 구체적인 내용은 라이선스를 
>참고한다."

>이 문서는 Experience API 작업 그룹(Experience API Working Group) 구성원들이 작성했으며(구성원 
>목록은 [CONTRIBUTING.md](../CONTRIBUTING.md#contributors) 참고), 미국 국방부 차관보 대리실(Office of the Deputy Assistant Secretary of 
>Defense (Readiness)) Advanced Distributed Learning (ADL) Initiative를 지원하기 위한 것이다. 
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

<a name="part-three-data-processing-validation-and-security"></a>
# 3부: 데이터 처리, 검증 및 보안 (Part Three: Data Processing, Validation, and Security)

이 세 번째 부분에서는 Experience API의 보다 기술적인 측면, 즉 Statement가 Learning Record Provider와 LRS 사이에서 
어떻게 전송되는지를 자세히 설명한다. 이 부분의 스펙을 처리해 주는 라이브러리가 (JavaScript를 포함한) 다양한 기술용으로 
제공되고 있다. 따라서 Learning Record Provider가 이 부분의 모든 세부 사항을 완전히 
이해할 필요는 없을 수도 있다.


<a name="10-requests"></a>
## 1.0 요청 (Requests)

xAPI 추적은 Learning Record Provider(클라이언트)에서 LRS(서버)로 보내는 HTTP 요청을 통해 이루어진다. 이 
스펙은 이 통신의 일부 측면에 대해 지침을 제공한다. 지침이 제공되지 않는 부분에 대해서는 
xAPI를 구현하는 이들이 현재의 업계 모범 사례를 따를 것을 권장한다.


<a name="11-head-request-implementation"></a>
### 1.1 HEAD 요청 구현 (HEAD Request Implementation)

<a name="description"></a>
###### 설명 (Description)
PUT, POST, GET, DELETE 요청에 대한 LRS의 동작은 아래 [리소스](#20-resources)에서 설명한다. 
GET 요청을 지원하는 모든 리소스는 HEAD도 지원한다.
LRS는 HEAD 요청에 대해 실제 문서는 반환하지 않고, HTTP 헤더를 사용하여 메타 정보만 
반환하는 방식으로 응답한다.  

<a name="rationale"></a>
###### 근거 (Rationale)

LRS에 접근하는 클라이언트는 특정 Statement가 존재하는지 확인하거나, State, Activity Profile, Agent Profile 리소스에 
있는 것과 같은 Document의 수정 날짜를 알아내야 할 수 있다. 특히 
크기가 큰 Document의 경우, 수정 날짜만 확인하기 위해 Document 전체를 가져오지 않는 편이 더 효율적이다.

<a name="lrs-requirements"></a>
###### LRS 요구사항 (LRS Requirements)
* LRS는 모든 HTTP HEAD 요청에 대해, 그 외에는 동일한 HTTP GET 요청에 응답했을 방식과 똑같이 
반드시 응답해야 한다(MUST). 단, 다음은 예외이다.
    * 메시지 본문(message-body)은 반드시 생략해야 한다(MUST).
    * LRS 자원의 낭비를 피하기 위해 Content-Length 헤더는 생략할 수 있다(MAY).


<a name="12-headers"></a>
### 1.2 헤더 (Headers)

<a name="header-parameters"></a>
##### 헤더 파라미터 (Header Parameters)
xAPI 데이터 전송에 사용되는 헤더 파라미터 중 일부는 
[표준 HTTP 헤더](http://en.wikipedia.org/wiki/List_of_HTTP_header_fields)이다. 나머지는 이
 스펙에 고유한 것이다. 다음 요청 헤더는 이 스펙에서 설명하는 요청 유형과 상황의 전부 또는 일부에서 
 Learning Record Provider가 사용할 것으로 예상된다.

* Accept
* Accept-Encoding
* Accept-Language
* Authorization
* Content-Type
* Content-Length
* Content-Transfer-Encoding
* If-Match
* If-None-Match
* X-Experience-API-Version 

다음 응답 헤더는 LRS가 사용할 것으로 예상된다. 마찬가지로 이 헤더들이 모든 요청 유형이나 
상황에 다 적용되는 것은 아니다.

* Content-Type
* Content-Length
* Last-Modified
* ETag
* Status
* X-Experience-API-Version
* X-Experience-API-Consistent-Through

위 목록은 모든 것을 망라하려는 것이 아니다. 자세한 내용은 이 문서 전반의 요구사항을 참고한다.


<a name="13-alternate-request-syntax"></a>
### 1.3 대체 요청 구문 (Alternate Request Syntax)


<a name="description-1"></a>
###### 설명 (Description)

xAPI의 목표 중 하나는 교차 도메인(cross-domain) 추적을 가능하게 하는 것이며, xAPI는 브라우저 이외의 애플리케이션에서도 
추적이 가능하도록 하려 하지만 브라우저 역시 여전히 지원해야 한다. 예를 들어 Internet Explorer 8과 9는 
Cross Origin Resource Sharing을 구현하지 않고 자체적인 Cross Domain Request API를 사용하는데, 이 API는 
"GET"과 "POST"만 지원하고 HTTP 헤더 설정을 허용하지 않기 때문에 위에서 설명한 xAPI를 모두 사용할 수는 없다.  

<a name="detailsrequirements"></a>
###### 세부 사항/요구사항 (Details/Requirements)

다음은 위에서 언급한 제약 때문에 특정 호출에서 일반 구문을 사용할 수 없을 때에만 사용하는 대체 구문을 
설명한다. 이 대체 구문은 쿼리 문자열 길이 제한 때문에 Statement를 GET할 때에도 사용할 수 있다.  

예제는 [부록 C: 교차 도메인 요청 예제](#appendix-c-cross-domain-request-example)를 참고한다. 

<a name="requirements"></a>
###### 요구사항 (Requirements)

__메서드(Method)__:  
* 발행되는 모든 xAPI 요청은 반드시 POST여야 한다(MUST). 
* 의도한 xAPI 메서드는 반드시 "method" 쿼리 
문자열 파라미터의 값으로 포함해야 한다(MUST). 
* Learning Record Provider는 요청에 다른 쿼리 문자열 파라미터를 포함해서는 안 된다(MUST NOT).

예: http://example.com/xAPI/statements?method=PUT  

__콘텐츠(Content)__:  
* xAPI 호출이 콘텐츠 전송을 수반하는 경우, Learning Record Provider는 반드시 그 콘텐츠를 URL 인코딩하여 
"content"라는 이름의 폼 파라미터로 포함해야 한다(MUST). 
* LRS는 반드시 이 콘텐츠를 UTF-8 문자열로 해석해야 한다(MUST). 이 구문으로는 바이너리 데이터 저장을 지원하지 않는다.  

__헤더(Headers)__:  
* Learning Record Provider는 이 스펙에서 요구하는 헤더 파라미터 중 HTTP 헤더에 나타날 것으로 
예상되는 파라미터를 같은 이름의 폼 파라미터로 포함할 수 있다(MAY). 이는 
다음 파라미터에 적용된다: Authorization, X-Experience-API-Version, Content-Type, Content-Length,
If-Match, If-None-Match. Content-Transfer-Encoding에는 적용되지 않는다.
* LRS는 반드시 위에 나열한 폼 파라미터를 헤더 파라미터로 취급해야 한다(MUST). 
* Learning Record Provider는 위에 나열되지 않은 그 밖의 헤더 파라미터를 반드시 평소처럼 HTTP 헤더에 포함해야 한다(MUST). 
* Learning Record Provider는 이 유형의 요청에도 여전히 'application/x-www-form-urlencoded' 값을 갖는 
Content-Type 헤더를 (HTTP 헤더에) 포함해야 한다(SHOULD*). 
* Content-Type 폼 파라미터는 content 폼 파라미터에 담긴 콘텐츠의 콘텐츠 유형을 지정해야 한다(SHOULD*). 
* Learning Record Provider는 이 유형의 요청에도 여전히 요청 콘텐츠 전체의 길이를 나타내는 
Content-Length 헤더를 (HTTP 헤더에) 포함해야 한다(SHOULD*). 
* Content-Length 폼 파라미터는 content 폼 파라미터에 담긴 콘텐츠의 길이를 
지정해야 하며(SHOULD*), 따라서 그 값은 Content-Length 헤더에 기재된 길이보다 작은 수가 된다. 

__쿼리 문자열 파라미터(Query string parameters)__:  
* "method" 이외의 모든 쿼리 문자열 파라미터는 반드시 같은 이름의 폼 파라미터로 대신 
포함해야 한다(MUST). 
* LRS는 "content" 또는 위에 나열한 헤더 파라미터 이외의 모든 폼 파라미터를 반드시 
쿼리 문자열 파라미터로 취급해야 한다(MUST). 

__Attachment(Attachments)__: 인코딩과 관련된 문제 때문에 이 구문으로는 
바이너리 데이터 Attachment를 전송할 수 없다는 점에 유의한다. [Attachments](./xAPI-Data.md#2411-attachments)를 참고한다. 

* LRS는 반드시 위 구문을 지원해야 한다(MUST).  

Learning Record Provider가 LRS와 다른 스킴(HTTP 또는 HTTPS)에서 클라이언트 코드가 호스팅되는 
애플리케이션이나 브라우저를 지원해야 하는 경우가 있을 수 있다. 프록시는 IE 9 이하에서 HTTP에서 
HTTPS로의 요청을 지원하려는 경우에만 필요하다. 최신 브라우저를 사용한다면 프록시 없이도 HTTP에서 HTTPS로(또는 HTTPS에서 HTTP로!) 요청할 수 있다. 
간단한 해결책으로는 1) 클라이언트 코드와 같은 스킴에서 LRS로 전달하는 프록시 패스스루를 구성하거나, 2) 클라이언트 코드와 
같은 스킴에 중간 서버 측 LRS를 호스팅하여 Statement를 대상 LRS로 라우팅하는 방법을 생각해 볼 수 있다.

HTTP를 사용하는 구현을 채택하기로 결정하기 전에 보안 위험을 충분히 고려해야 한다.


<a name="14-encoding"></a>
### 1.4 인코딩 (Encoding)

<a name="requirements-1"></a>
###### 요구사항 (Requirements)
* 모든 문자열은 반드시 UTF-8로 인코딩되고 해석되어야 한다(MUST). 

<a name="15-content-types"></a>
### 1.5 콘텐츠 유형 (Content Types)
이 스펙의 요청과 응답은 일반적으로 `application/json` 콘텐츠 유형을 사용한다. 예외는 다음과 같다.

* Document는 어떤 콘텐츠 유형이든 가질 수 있다. 
* 경우에 따라 Attachment를 포함할 수 있는 Statement 요청은 `multipart/mixed` 콘텐츠 유형을 사용한다. 

<a name="151-applicationjson"></a>
#### 1.5.1 Application/JSON
이 스펙의 요청은 일반적으로 `application/json` 콘텐츠 유형을 사용한다. 

<a name="lrs-requirements-1"></a>
###### LRS 요구사항 (LRS Requirements)
* 문서 유형이 `application/json`인 PUT 또는 POST를 수신할 때, LRS는 Attachment Object를 
포함하지 않는 Statement 배치를 반드시 수락해야 한다(MUST).
* 문서 유형이 `application/json`인 PUT 또는 POST를 수신할 때, LRS는 fileUrl이 채워진 
Attachment Object만 포함하는 Statement 배치를 반드시 수락해야 한다(MUST).

<a name="152-multipartmixed"></a>
#### 1.5.2 Multipart/Mixed

`multipart/mixed` 콘텐츠 유형은 Attachment를 포함*할 수도 있는* 요청에 사용된다. 그렇다고 모든 
"multipart/mixed" 요청이 반드시 Attachment를 포함한다는 의미는 아니다.

<a name="procedure-for-the-exchange-of-attachments"></a>
##### Attachment 교환 절차 (Procedure For The Exchange Of Attachments)

* 0개 이상의 Attachment를 포함하는 Statement 요청은 아래 설명에 따라 해석된다.

* Statement는 `multipart/mixed` Content-Type으로 전송된다. Attachment가 있다면 
이러한 전송의 끝부분에 배치된다.

* LRS는 첫 번째 파트의 정보를 바탕으로 Statement를 수락할지 거부할지 결정한다.

* 요청을 수락하는 경우, LRS는 원시 데이터의 SHA-2와 헤더에 선언된 SHA-2를 비교하여 
Attachment의 원시 데이터를 Attachment 헤더와 대응시킬 수 있다. 다른 방식으로 대응시켜서는 안 된다(MUST not).

<a name="requirements-for-attachment-statement-batches"></a>
###### Attachment가 포함된 Statement 배치 요구사항 (Requirements for Attachment Statement Batches)

Attachment를 포함하는 Statement 배치, Statement 결과 또는 단일 Statement를 전송하는 요청은 반드시 다음 
기준 중 하나를 충족해야 한다(MUST).

* 반드시 `application/json` 유형이어야 하며 모든 Attachment에 대해 fileUrl을 포함해야 한다(MUST). 단, "attachments" 필터가 `false`인 
Statement 결과는 예외(EXCEPT)이다.
* 반드시 [RFC 2046](https://www.ietf.org/rfc/rfc2046.txt)의 "multipart/mixed" 정의를 따라야 하며(MUST), 다음을 충족해야 한다.
    * multipart 문서의 첫 번째 파트는 반드시 Statement 자체를 
    `application/json` 유형으로 포함해야 한다(MUST).
    * 추가되는 각 파트에는 Attachment 하나의 원시 데이터가 담기며, 이는 Statement의 논리적 
    일부를 이룬다. 이 기능은 Statement 리소스에 PUT 또는 POST 요청을 보낼 때 사용할 수 있다.
    * 첫 번째(Statement) 파트 이후 각 파트의 헤더에는 반드시 X-Experience-API-Hash 파라미터를 
    포함해야 한다(MUST).
    * 첫 번째(Statement) 파트 이후 각 파트의 헤더에는 반드시 값이 `binary`인 
    Content-Transfer-Encoding 파라미터를 포함해야 한다(MUST).
    * 함께 전송되는 여러 Statement에서 동일한 Attachment가 사용되는 경우, 해당 Attachment 데이터의 
    사본은 하나만 포함해야 한다(SHOULD).
    * 각 파트의 헤더에 Content-Type 파라미터를 포함해야 한다(SHOULD). 첫 번째 파트 
    (Statement를 담은 파트)의 경우 이 값은 반드시 `application/json`이어야 한다(MUST).
   	* 파라미터에 대응하는 속성이 attachment Object 안에 있고 
   	(위 표에 설명됨), 특정 Attachment에 대해 파라미터와 속성이 모두 지정된 경우, 
	이 파라미터와 속성의 값은 반드시 일치해야 한다(MUST). 

<a name="lrs-requirements-2"></a>
###### LRS 요구사항 (LRS Requirements)

* LRS는 클라이언트가 요청한 경우 반드시 위에서 설명한 전송 형식(Transmission Format)으로 Attachment를 
포함해야 한다(MUST) ([Statement 리소스](#21-statement-resource) 참고).
* LRS는 Attachment를 요청하지 않고 다른 LRS에서 Statement를 가져와서는 안 된다(MUST NOT).
* LRS는 수신한 Attachment 데이터가 있다면 그 데이터를 포함하지 않은 채 해당 Statement를 
다른 LRS로 보내서는 안 된다(MUST NOT).
* 문서 유형이 `multipart/mixed`인 PUT 또는 POST를 수신할 때, LRS는 위에서 설명한 전송 형식으로 
Attachment를 포함하는 Statement 배치를 반드시 수락해야 한다(MUST).
* 문서 유형이 `multipart/mixed`인 PUT 또는 POST를 수신할 때, LRS는 fileUrl도 포함하지 않고 해시를 기준으로 
수신된 Attachment 파트와도 일치하지 않는 Attachment가 있는 Statement 배치를 반드시 거부해야 한다(MUST).
* 문서 유형이 `multipart/mixed`인 PUT 또는 POST를 수신할 때, LRS는 Attachment 파트의 
Content-Transfer-Encoding을 binary로 간주해야 한다(SHOULD).
* LRS는 LRS에 설정된 허용 크기보다 큰 Statement(또는 Statement 배치)를 거부할 수 있다(MAY).
* 문서 유형이 `multipart/mixed`인 PUT 또는 POST를 수신할 때, LRS는 Attachment Object를 포함하지 않는 
Statement 배치를 수락해야 한다(SHOULD*).
* 문서 유형이 `multipart/mixed`인 PUT 또는 POST를 수신할 때, LRS는 fileUrl이 채워진 Attachment Object만 
포함하는 Statement 배치를 수락해야 한다(SHOULD*).

__참고(Note):__ "mime/multipart" 형식을 사용하는 Statement 배치가 반드시 Attachment를 포함해야 한다는 요구사항은 없다.

<a name="learning-record-provider-requirements"></a>
###### Learning Record Provider 요구사항 (Learning Record Provider Requirements)

* Learning Record Provider는 위에서 설명한 방식으로 Attachment가 포함된 Statement를 전송할 수 있다(MAY).
* Learning Record Provider는 POST를 사용하는 경우, 일부 또는 전부가 Attachment를 가진 
여러 Statement를 전송할 수 있다(MAY).
* Learning Record Provider는 모든 attachment Object가 fileUrl을 갖는 `application/json` 유형의 배치를 
전송할 수 있으며(MAY), 이때 "multipart/mixed" 형식에 기반한 모든 요구사항은 무시한다.
* Learning Record Provider는 "sha2" 속성을 채울 때 SHA-256, SHA-384 또는 SHA-512를 사용해야 한다(SHOULD).

<a name="file-url"></a>
###### 파일 URL (File URL)
파일 URL(File URL)은 Attachment를 받을 수 있는 위치를 제공하기 위한 것이다.
그러나 Attachment의 소유자가 Attachment 데이터를 해당 위치에서 무기한 제공하거나 
보안 제한 없이 공개적으로 제공해야 한다는 요구사항은 
없다. Attachment 호스팅 방식을 결정할 때, 
"fileUrl" 속성을 사용하여 Statement를 생성하는 이들은 Statement의 최종 수신자의 요구를 고려할 것이 권장되며, 
특히 Attachment 콘텐츠가 Statement와 함께 포함되지 않는 경우에는 더욱 그렇다.

* Attachment 데이터는 fileUrl이 가리키는 URL에서 가져올 수 있어야 한다(SHOULD).
* Attachment의 소유자는 언제든지 이 IRL에서 Attachment 데이터 제공을 중단할 수 있다(MAY). 
* 이 IRL에서 Attachment 데이터에 접근하려는 이들에게 보안 제한을 적용할 수 있다(MAY). 

Attachment를 제공하는 기간과 호스팅된 Attachment에 적용되는 
보안 제한은 이 스펙의 범위를 벗어난다. 

<a name="example"></a>
###### 예제 (Example)

다음은 Attachment가 하나 있는 매우 간단한 Statement의 예제이다. 다음 사항에 유의한다.

* 예제의 경계 문자열(boundary)은 유효한 문자 클래스를 보여 주기 위해 선택되었다.
* 선택한 경계 문자열은 어느 파트에도 나타나지 않는다.
* 가독성을 위해 예제 Attachment는 "text/plain" 유형으로 했다. 설령 "image/jpeg" 같은 
바이너리 유형이었더라도 인코딩은 수행되지 않으며, 원시 옥텟이 그대로 포함된다.
* RFC 2046에 따라, 경계는 `<CRLF>` 다음에 --가 오고, 그 다음에 헤더에 
선언된 경계 문자열이 오는 형태이다.

__참고(Note):__ 이러한 메시지를 만들거나 파싱할 때 ```<CRLF>```를 잊지 않도록 한다.

헤더(Headers):

``` 
Content-Type: multipart/mixed; boundary="abcABC0123'()+_,-./:=?"
X-Experience-API-Version:1.0.0
```
콘텐츠(Content):
```

--abcABC0123'()+_,-./:=?
Content-Type:application/json

{
    "actor": {
        "mbox": "mailto:sample.agent@example.com",
        "name": "Sample Agent",
        "objectType": "Agent"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/answered",
        "display": {
            "en-US": "answered"
        }
    },
    "object": {
        "id": "http://www.example.com/tincan/activities/multipart",
        "objectType": "Activity",
        "definition": {
            "name": {
                "en-US": "Multi Part Activity"
            },
            "description": {
                "en-US": "Multi Part Activity Description"
            }
        }
    },
    "attachments": [
        {
            "usageType": "http://example.com/attachment-usage/test",
            "display": { "en-US": "A test attachment" },
            "description": { "en-US": "A test attachment (description)" },
            "contentType": "text/plain; charset=ascii",
            "length": 27,
            "sha2": "495395e777cd98da653df9615d09c0fd6bb2f8d4788394cd53c56a3bfdcd848a"
        }
    ]
}
--abcABC0123'()+_,-./:=?
Content-Type:text/plain
Content-Transfer-Encoding:binary
X-Experience-API-Hash:495395e777cd98da653df9615d09c0fd6bb2f8d4788394cd53c56a3bfdcd848a

here is a simple attachment
--abcABC0123'()+_,-./:=?--
```

<a name="20-resources"></a>
## 2.0 리소스 (Resources)

LRS와의 상호작용은 이 절에서 설명하는 리소스에 대한 RESTful HTTP 메서드를 통해 이루어진다.
Statement 리소스는 그것만으로도 학습 기록을 추적하는 데 사용할 수 있다. 다른 리소스들은
추가 기능을 제공한다. 

LRS는 이 절에서 설명하는 모든 리소스를 지원한다. 또한 LRS가 아닌 도구가 이 절에서 설명하는 
하나 이상의 리소스와 메서드에 대해 LRS 요구사항을 따르기로 선택하는 것도 
가능하다. 예를 들어 어떤 도구는 LRS가 전달하는 Statement를 수신할 목적으로 
POST Statements를 구현할 수 있다.
이러한 시스템은 LRS나 '부분 LRS'로 간주되지 않으며, 단지 LRS가 아닐 뿐이다. 

__참고(Note):__ 이 스펙에서 xAPI 리소스의 위치를 보여 주는 모든 예제 엔드포인트에서 `http://example.com/xAPI/`는 
LRS의 예제 기본 엔드포인트이다. 그 뒤에 오는 IRI 구문은 사용되는 특정 리소스를 나타낸다. 
엔드포인트의 전체 목록은 [부록 B: 전체 리소스 표](#appendix-b-table-of-all-resources)에 수록되어 있다.

<a name="requirements-2"></a>
###### 요구사항 (Requirements)

* LRS는 반드시 이 절에서 설명하는 모든 리소스를 지원해야 한다(MUST). 
* LRS가 OAuth 1.0을 구현하는 경우, LRS는 [OAuth 인가 범위](#42-oauth-10-authorization-scope)에서 설명하는 
모든 OAuth 리소스도 반드시 지원해야 한다(MUST).
* LRS는 이 스펙에서 설명하지 않는 추가 리소스를 지원할 수 있다(MAY). 
* 이 스펙의 과거, 현재, 미래 버전은 `extensions/`로 시작하는 경로 세그먼트를 갖는 엔드포인트를 정의하지 않으며 
앞으로도 정의하지 않을 것이다. 이 스펙에 정의되지 않은 추가 리소스를 지원하는 LRS는 `extensions/`로 시작하는 
경로 세그먼트로 엔드포인트를 정의해야 한다(SHOULD).


<a name="21-statement-resource"></a>
#### 2.1 Statement 리소스 (Statement Resource)

<a name="description-2"></a>
###### 설명 (Description)

Experience API의 기본 통신 메커니즘이다.  


<a name="211-put-statements"></a>
#### 2.1.1 PUT Statements

<a name="details"></a>
###### 세부 사항 (Details)

엔드포인트 예시: `http://example.com/xAPI/statements`

주어진 id로 단일 Statement를 저장한다. 단일 Statement를 저장할 때는 POST도 사용할 수 있다.

**내용(Content):** 저장할 Statement 객체. 

**반환값(Returns):** `204 No Content`  

<table>
	<tr><th>파라미터</th><th>타입</th><th>기본값</th><th>설명</th><th>필수 여부</th></tr>
	<tr><td>statementId</td><td>String</td><td> 
	<td>기록할 Statement의 Id</td></td><td>필수</td></tr>
</table>

<a name="lrs-requirements-3"></a>
###### LRS 요구사항 (LRS Requirements)

* LRS는 저장된 Statement를 조회할 수 있게 되기 전에 응답할 수 있다(MAY).

* LRS는 이미 Statement를 보유하고 있는 statementId를 가진 Statement를 수신한 경우,
이를 근거로 자신의 상태를 변경해서는 안 된다(MUST NOT). `409 Conflict`로 응답하든 `204 No Content`로 응답하든, 
Statement나 다른 어떤 Object도 수정해서는 안 된다(MUST NOT).

* LRS가 이미 보유한 Statement와 같은 id를 가진 Statement를 수신하면, 수신한 Statement가
기존 Statement와 일치하는지 검증해야 하며(SHOULD), 일치하지 않으면 `409 Conflict`를
반환해야 한다(SHOULD). [Statement 비교 요구사항](./xAPI-Data.md#statement-comparision-requirements)을 참고한다.

* LRS가 같은 id를 가진 Statement를 둘 이상 포함하는 Statement 묶음(batch)을 수신하면, 
해당 묶음을 거부하고 `400 Bad Request`를 반환해야 한다(SHOULD*).



<a name="learning-record-provider-requirements-1"></a>
###### Learning Record Provider 요구사항 (Learning Record Provider Requirements)

* Learning Record Provider는 PUT을 사용하는 대신, Statement의 "id" 속성을 포함하여 
Statement를 POST해야 한다(SHOULD). 
* Statement를 PUT할 때는 Statement의 "id" 속성을 사용해야 한다(SHOULD). 
* Statement의 "id" 속성이 제공된 경우, 그 값은 요청의 "statementId" 파라미터와 반드시 일치해야 한다(MUST). 


<a name="212-post-statements"></a>
#### 2.1.2 POST Statements

<a name="details-1"></a>
###### 세부 사항 (Details)

엔드포인트 예시: `http://example.com/xAPI/statements`

Statement 하나 또는 Statement 집합을 저장한다.

**내용(Content):** 저장할 Statement 배열 또는 단일 Statement. 

**반환값(Returns):** `200 OK`, 저장된 Statement와 같은 순서로 나열된 Statement id(UUID) 배열.  

<a name="requirements-3"></a>
###### 요구사항 (Requirements)

* LRS는 저장된 Statement를 조회할 수 있게 되기 전에 응답할 수 있다(MAY).
* 쿼리 문자열에는 길이 제한이 있으므로, 필요한 경우 GET Statements를 POST와 폼 파라미터를 
사용해 호출할 수 있다(MAY). 자세한 내용은 [대체 요청 구문(Alternate Request Syntax)](#13-alternate-request-syntax)을 참고한다.
* LRS는 전달된 파라미터를 기준으로, Statement를 추가하기 위한 POST와 Statement 목록을 조회하기 위한 
POST를 반드시 구분해야 한다(MUST). 자세한 내용은 [대체 요청 구문(Alternate Request Syntax)](#13-alternate-request-syntax)을 참고한다.
* LRS는 이미 Statement를 보유하고 있는 id를 가진 Statement를 수신한 경우,
이를 근거로 자신의 상태를 변경해서는 안 된다(MUST NOT). `409 Conflict`로 응답하든 `204 No Content`로 응답하든, 
Statement나 다른 어떤 Object도 수정해서는 안 된다(MUST NOT).
* LRS가 이미 보유한 Statement와 같은 id를 가진 Statement를 수신하면, 수신한 Statement가
기존 Statement와 일치하는지 검증해야 하며(SHOULD), 일치하지 않으면 `409 Conflict`를
반환해야 한다(SHOULD). [Statement 비교 요구사항](./xAPI-Data.md#statement-comparision-requirements)을 참고한다.
* LRS가 같은 id를 가진 Statement를 둘 이상 포함하는 Statement 묶음(batch)을 수신하면, 
해당 묶음을 거부하고 `400 Bad Request`를 반환해야 한다(SHOULD*).


<a name="213-get-statements"></a>
#### 2.1.3 GET Statements

<a name="details-2"></a>
###### 세부 사항 (Details)

엔드포인트 예시: `http://example.com/xAPI/statements`

이 메서드는 단일 Statement 또는 여러 Statement를 가져올 때 호출한다. statementId 또는 voidedStatementId 파라미터가 
지정되면 단일 Statement가 반환된다.

그 외의 경우 반환값: [StatementResult](./xAPI-Data.md#25-retrieval-of-statements) Object. 이는 권한과 최대 목록 길이의 제약 아래에서 
"stored" 시각을 기준으로 역시간순 정렬된 Statement 목록이다. 추가 결과가 있으면, 이를 
조회할 수 있는 IRL이 StatementResult Object에 포함된다.

**내용(Content):** 없음.

**반환값(Returns):** `200 OK`, Statement 또는 [Statement Result](./xAPI-Data.md#25-retrieval-of-statements)

<table>
	<tr><th>파라미터</th><th>타입</th><th>기본값</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>statementId</td>
		<td>String</td>
		<td> </td>
		<td>가져올 Statement의 Id</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>voidedStatementId</td>
		<td>String</td>
		<td> </td>
		<td>가져올 무효화된 Statement의 Id. <a href="./xAPI-Data.md#232-voiding">무효화된
		Statement(Voided Statements)</a>를 참고한다</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>agent</td>
		<td>Agent or Identified Group Object (JSON)</td>
		<td> </td>
		<td>필터. 지정된 Agent 또는 Group이 Statement의 
		Actor 또는 Object인 Statement만 반환한다.
			<ul>
				<li> 
					비교하는 각 Object에서 동일한 역함수 식별자(Inverse Functional
					Identifier)가 사용되고 그 역함수 식별자의 값이 같으면,
					Agent 또는 Identified Group은 동일하다.
				</li><li>
					이 필터에서는, 위에서 설명한 역함수 식별자를 기준으로 
					지정된 Agent와 일치하는 구성원(member)을 가진 Group도
					일치하는 것으로 간주한다
				</li>
			</ul>
			<br><br>자세한 내용은 <a href="./xAPI-Data.md#242-actor">agent/group</a> Object 정의를
			참고한다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>verb</td>
		<td>Verb id (IRI)</td>
		<td> </td>
		<td>필터. 지정된 Verb id와 일치하는 Statement만 반환한다.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>activity</td>
		<td>Activity id (IRI)</td>
		<td> </td>
		<td>
			필터. Statement의 Object가 지정된 id를 가진 Activity인 
			Statement만 반환한다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>registration</td>
		<td>UUID</td>
		<td> </td>
		<td>
			필터. 지정된 registration id와 일치하는 Statement만 
			반환한다. 흔히 하나의 Activity에 배정된 하나의 Actor에 대해 
			고유한 registration이 사용되지만, 항상 그렇다고 가정할 수는 없다는 점에 유의한다. 
			특정 Actor 또는 Activity에 대한 Statement만 필요하다면, 
			해당 파라미터도 함께 지정해야 한다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
	<td>related_activities</td>
		<td>Boolean</td>
		<td>false</td>
		<td>
			Activity 필터를 넓게 적용한다. 해당 파라미터의 일반적인 동작 대신, Object,
			context Activity 중 하나, 또는 포함된 SubStatement 안의 이러한 속성 중
			하나가 Activity 파라미터와 일치하는 Statement를 포함한다. 일치 여부는 
			"activity" 파라미터와 같은 방식으로 정의된다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>related_agents</td>
		<td>Boolean</td>
		<td>false</td>
		<td>
			Agent 필터를 넓게 적용한다. 해당 파라미터의 일반적인 동작 대신, 
			Actor, Object, Authority, Instructor, Team,
			또는 포함된 SubStatement 안의 이러한 속성 중 하나가 Agent 파라미터와 일치하는
			Statement를 포함한다. 일치 여부는 "agent" 파라미터와 같은 방식으로
			정의된다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>since</td>
		<td>Timestamp</td>
		<td> </td>
		<td>지정된 Timestamp 이후(해당 시각 미포함)에 저장된 Statement만 반환한다.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>until</td>
		<td>Timestamp</td>
		<td> </td>
		<td>지정된 Timestamp 또는 그 이전에 저장된 Statement만 반환한다.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>limit</td>
		<td>Nonnegative Integer</td>
		<td>0</td>
		<td>
			반환할 Statement의 최대 개수. 0은 서버가 허용하는 
			최대 개수만큼 반환함을 의미한다.
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>format</td>
		<td>String: (<code>ids</code>, <code>exact</code>, or <code>canonical</code>)</td>
		<td>exact</td>
		<td><code>ids</code>이면, Agent, Activity, Verb, Group Object에 이를 식별하는 데 
			필요한 최소한의 정보만 포함한다. Anonymous Group의 경우에는 
			각 구성원을 식별하는 데 필요한 최소한의 정보를 포함한다는 의미이다. 
			<br/><br/>
			<code>exact</code>이면, Agent, Activity, Verb, Group Object를 Statement를 수신했을 때와 
			정확히 동일하게 채워서 반환한다. Statement를 가져오기(import) 위해 
			Statement를 요청하는 LRS는 <a href="./xAPI-Data.md#231-statement-immutability">Statement 불변성(Statement Immutability)</a>을 
			유지하기 위해 "exact" 형식을 사용할 것이다.  
			<br/><br/>
			<code>canonical</code>이면, <a href="#language-filtering-requirements-for-canonical-format-statements">아래에 정의된 언어 필터링 절차</a>를 
			적용한 후 LRS가 결정한 Activity Object의 정규(canonical) 정의와 Verb의 Display로
			Activity Object와 Verb를 채워서 반환하고,
			Agent와 Group Object는 "exact" 모드와 같이 원래대로 반환한다.  
		</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>attachments</td><td>Boolean</td><td>false</td>
		<td><code>true</code>이면, LRS는 multipart 응답 형식을 사용하고 앞서 설명한 대로 모든 
		첨부 파일(attachment)을 포함한다.  <code>false</code>이면, LRS는 Content-Type 
		application/json으로 규정된 응답을 보내며 첨부 데이터는 보내지 않는다.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>ascending</td>
		<td>Boolean</td>
		<td>false</td>
		<td><code>true</code>이면, 저장 시각의 오름차순으로 결과를 반환한다</td>
		<td>선택</td>
	</tr>
</table>

__참고:__ Boolean 파라미터의 값은 JSON에서와 같이 `true` 또는 `false`로 표현한다.
<a name="requirements-4"></a>
###### 요구사항 (Requirements)

* LRS는 statementId와 voidedStatementId 파라미터를 모두 포함하는 이 리소스에 대한 
모든 요청을 `400 Bad Request` 오류로 반드시 거부해야 한다(MUST)

* LRS는 statementId 또는 voidedStatementId 파라미터를 포함하면서 "attachments"나 "format" 외의 
다른 파라미터도 함께 포함하는 이 리소스에 대한 모든 요청을 `400 Bad Request` 오류로 반드시 거부해야 한다(MUST).

* LRS는 사용된 자격 증명(credentials)에 연결된 권한에 따라 추가적인 쿼리 필터
조건을 적용할 수 있다(MAY). 

* 쿼리 필터 조건과 일치하는 Statement가 하나도 없는 경우에도, LRS는 여전히 
`200 OK`와 [StatementResult](./xAPI-Data.md#25-retrieval-of-statements) Object를 반드시 반환해야 한다(MUST). 이 경우 "statements" 속성은 빈 배열을 담는다.

* LRS는 Statement 리소스 요청에 대한 모든 응답에 "X-Experience-API-Consistent-Through" 헤더를 
[ISO 8601 결합 날짜 및 시간(combined date and time)](https://en.wikipedia.org/wiki/ISO_8601#Combined_date_and_time_representations) 형식으로 
반드시 포함해야 한다(MUST). 그 값은 해당 시각 이전의 "stored" 속성을 가지고 있거나 앞으로 갖게 될 모든 Statement가 
조회 가능하다고 합리적으로 확신할 수 있는 시각의 timestamp이다. 이 시각은 과도한 부하처럼 Statement가 
조회 가능해지기까지 지연을 일으킬 수 있는 일시적인 상황을 고려해야 한다(SHOULD). 
최근에 수신한 Statement가 없더라도 이 값은 최근의 timestamp일 것으로 기대된다. 

* GET Statement의 "attachment" 속성이 사용되고 `true`로 설정되면, LRS는 반드시 
multipart 응답 형식을 사용하고 [2부(Part Two)](./xAPI-Data.md#2411-attachments)에서 설명한 대로 모든 Attachment를 포함해야 한다(MUST).

* GET statement의 "attachment" 속성이 사용되고 `false`로 설정되면, LRS는 Attachment 원시 데이터를 
포함해서는 안 되며(MUST NOT) 반드시 `application/json`으로 보고해야 한다(MUST).

* LRS는 Statement의 "stored" Timestamp와 일치하는 "Last-Modified" 헤더를 
포함해야 한다(SHOULD*). 


<a name="filter-conditions-for-statementrefs"></a>
###### StatementRef에 대한 필터 조건 (Filter Conditions for StatementRefs)

이 절에서는 다른 Statement를 대상으로 하는 Statement가, 원래 쿼리의 필터 파라미터와 일치하지 않더라도 
쿼리의 필터 조건을 충족하는 것으로 간주될 수 있는 규칙을 설명한다. 
이 규칙은 "statementId" 또는 "voidedStatementId" 쿼리 파라미터를 사용해 단일 Statement를 조회할 때는 
적용되지 **않는다**.

'Statement를 대상으로 한다(Targeting Statements)'는 것은 한 Statement(대상을 지정하는 Statement)가 다른
Statement(대상이 되는 Statement)의 Statement id를 Statement Reference로서 Statement의 Object에 포함하는 것을 의미한다. 

시간 또는 순서 기반이 아닌 필터 파라미터("since", "until", "limit" 이외의 파라미터)의 경우, 
(StatementRef를 Statement의 Object로 사용하여) 다른 Statement를 대상으로 하는 Statement는 
대상이 되는 Statement가 필터 조건을 충족하면 그 필터 조건을 충족한다.

이 방식에서도 시간 및 순서 기반 파라미터는 여전히 StatementRef를 만드는 Statement에 반드시 적용되어야 한다(MUST). 
이 규칙은 재귀적으로 적용되므로, a가 b를 대상으로 하고 b가 c를 대상으로 하며 위에서 설명한 필터 
조건이 "Statement c"와 일치하면 "Statement a"도 일치한다.

예를 들어, 'Ben passed explosives training'(Ben이 폭발물 훈련을 통과했다)이라는 Statement와 그 후속
Statement인 "Andrew confirmed <StatementRef to original Statement\>"를 생각해 보자. 후속
Statement에는 'Ben'이나 'explosives training'이 언급되지 않지만, 'Ben'이라는 Actor 필터나
'explosives training'이라는 Activity 필터로 Statement를 가져올 때, 두 Statement가 조회 대상
시간 또는 순서 범위에 속하는 한 둘 다 일치하여 반환된다.

__참고:__ Context 안의 "Statement" 속성 값으로 사용된 StatementRef는 Statement가
필터링되는 방식에 영향을 주지 않는다.


<a name="language-filtering-requirements-for-canonical-format-statements"></a>
###### 정규 형식 Statement에 대한 언어 필터링 요구사항 (Language Filtering Requirements for Canonical Format Statements)

* Activity Object는 "name", "description" 및 여러 상호작용 구성 요소(interaction component) 안에 
Language Map Object를 포함한다. LRS는 이러한 각 맵에서 반드시 하나의 언어만 반환해야 한다(MUST). 

* LRS는 언어 맵을 포함하는 객체를 식별하는 모든 IRI에 대해 언어 맵의 정규(canonical) 버전을 유지할 수 있다(MAY).
여기에는 Verb의 "display" 속성에 저장된 언어 맵과, 경우에 따라 extension 안에서 사용되는 
일부 언어 맵이 포함된다. 

* LRS가 언어 맵의 정규 버전을 유지하는 경우, 정규 형식으로 Statement를 조회할 때 
 이 정규 언어 맵을 반환해야 한다(SHOULD*). 

* LRS는 정규 맵을 반환하는 각 언어 맵 안에서 하나의 언어만 반환해야 한다(SHOULD*). 

* 가장 적합한 언어를 선택하기 위해, LRS는 [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) 
(HTTP 1.1)에 설명된 대로 "Accept-Language" 헤더를 반드시 적용해야 한다(MUST). 단, 이 로직은 리소스(Statement 목록) 
전체가 아니라, 포함할 언어 항목을 선택하기 위해 각 언어 맵에 개별적으로 반드시 적용되어야 한다(MUST).


<a name="214-voided-statements"></a>
##### 2.1.4 무효화된 Statement (Voided Statements)
[2부(Part Two)](./xAPI-Data.md#232-voiding)에서는 Statement를 무효화하는 절차를 설명한다. 이 절에서는
쿼리 시 LRS가 무효화된 Statement를 어떻게 처리하는지 설명한다. 

클라이언트는 무효화하는(voiding) Statement의 대상을 통해 무효화된 Statement의 존재와 Statement id를 확인할 수 있다. 
디버깅 도구를 제외하면, 많은 Learning Record Consumer는 무효화하는 Statement를 사용자에게 보여 주기를 원하지 않을 것이며 
activity stream이나 기타 보고서에 이를 표시하지 않을 것이다. 

<a name="requirements-5"></a>
###### 요구사항 (Requirements)

* LRS는 voidedStatementId로 요청된 경우가 아니라면, 무효화된 Statement를 반환해서는 안 된다(MUST NOT). 
[StatementRef에 대한 필터 조건 절](#filter-conditions-for-statementrefs)에서 설명한 절차도 
이 요구사항의 예외가 아니다. 무효화하는 Statement를 조회하는 방법은 각각을 
voidedStatementId로 개별 요청하는 것이다.

* LRS는 [StatementRef에 대한 필터 조건 절](#filter-conditions-for-statementrefs)에서 설명한 절차와 조건에 따라, 
무효화된 Statement를 대상으로 하는 모든 Statement는 여전히 반드시 반환해야 한다(MUST). 여기에는 
무효화될 수 없는, 무효화하는 Statement 자체도 포함된다. 


<a name="22-document-resources"></a>
### 2.2 Document 리소스 (Document Resources) 

<a name="description-3"></a>
##### 설명 (Description)
Experience API는 Learning Record Provider가 Activity, Agent 또는 그 둘의 조합과 관련될 수 있는 
임의의 데이터를 document 형태로 저장할 수 있는 기능을 제공한다.

<a name="details-3"></a>
##### 세부 사항 (Details)
다음 표는 이 명세의 다른 많은 표처럼 JSON Object를 나타내는 것이 아니라 일반적인 속성을 보여 준다는 점에 유의한다. 
id는 IRL에 저장되고, "updated"는 HTTP 헤더 정보이며, 
"contents"는 (Object가 아닌) HTTP 문서 그 자체이다.
<table>
	<tr><th>속성</th><th>타입</th><th>설명</th></tr>
	<tr><td>id</td><td>String</td><td>Learning Record Provider가 설정하며, Agent 또는 Activity의 
	범위 안에서 고유하다.</td></tr>
	<tr><td>updated</td><td>Timestamp</td><td>document가 가장 최근에 수정된 시각.</td></tr>
	<tr><td>contents</td><td>Arbitrary binary data</td><td>document의 내용</td></tr>
</table>

세 가지 Document 리소스는 [document](./xAPI-Data.md#10-documents) 저장 기능을 제공한다.  각 리소스의 세부 사항은 
다음 절들에서 설명하며, 이 절의 정보는 세 리소스 모두에 적용된다.

<a name="details-4"></a>
###### 세부 사항 (Details)

<table>
	<tr>
		<th>리소스</th>
		<th>메서드</th>
		<th>엔드포인트</th>
		<th>예시</th>
	</tr>
	<tr>
		<td>State 리소스</td>
		<td>POST</td>
		<td>activities/state</td>
		<td>http://example.com/xAPI/activities/state</td>
	</tr>
	<tr>
		<td>Activity Profile 리소스</td>
		<td>POST</td>
		<td>activities/profile</td>
		<td>http://example.com/xAPI/activities/profile</td>
	</tr>
	<tr>
		<td>Agent Profile 리소스</td>
		<td>POST</td>
		<td>agents/profile</td>
		<td>http://example.com/xAPI/agents/profile</td>
	</tr>
</table>

<a name="requirements-6"></a>
###### 요구사항 (Requirements)

* Learning Record Provider는 LRS가 사전에 알지 못하는 Activity 및 Agent에 대해서도 
어떤 Document 리소스로든 document를 보낼 수 있다(MAY). 

* LRS는 Activity 및/또는 Agent에 대한 사전 지식이 없다는 이유로 document를 거부해서는 안 된다(MUST NOT).

<a name="last-modified"></a>
##### 최종 수정 시각 (Last Modified)
"Last Modified" 헤더는 GET 요청에 대한 응답으로 단일 또는 여러 document를 반환할 때 LRS가 설정한다. 

<a name="requirements-7"></a>
###### 요구사항 (Requirements)
* 단일 document를 반환할 때, LRS는 해당 document가 마지막으로 수정된 시각을 나타내는
"Last-Modified" 헤더를 포함해야 한다(SHOULD*). 
* 여러 document를 반환할 때, LRS는 가장 최근에 수정된 document가 마지막으로 수정된 시각을 나타내는
"Last-Modified" 헤더를 포함해야 한다(SHOULD*). 

<a name="json-procedure-with-requirements"></a>
###### JSON 처리 절차와 요구사항 (JSON Procedure with Requirements)

Learning Record Provider가 content type이 `application/json`인 document에 변수를 JSON Object로 저장한다면, 
POST를 사용해 이를 변수 집합으로 다룰 수 있다.

다음은 그 절차와 절차상의 요구사항을 단계별로 설명한다.  
예를 들어, 어떤 document가 다음 내용을 담고 있다고 하자: 

```
{
	"x" : "foo",
	"y" : "bar"
}
```  
LRS가 content type이 `application/json`인 기존 document에 대해 content type이 `application/json`인
POST 요청을 받으면, 게시된(posted) document를 기존 document와 반드시 병합해야 한다(MUST). 
이 맥락에서 병합은 다음과 같이 정의된다:
* 각 document가 나타내는 Object를 역직렬화한다.
* 게시되는 Object에 직접 정의된 각 속성에 대해, 기존 Object의 대응하는
속성을 게시된 Object의 값과 같게 설정한다.    
* 기존 Object를 유효한 json으로 직렬화한 결과를 요청에서 참조한 document로 저장한다.

최상위 속성만 병합된다는 점에 유의한다. 최상위 속성이 Object인 경우에도 마찬가지이다. 각 원래 속성의 
전체 내용은 각 새 속성의 전체 내용으로 대체된다.

예를 들어, 위의 기존 document와 같은 id로 다음 document를 POST하면:

```
{
	"x" : "bash",
	"z" : "faz"
}
```  
LRS에 저장되는 결과 document는 다음과 같다:
```
{
	"x" : "bash",
	"y" : "bar",
	"z" : "faz"
}
```

<a name="requirements-8"></a>
###### 요구사항 (Requirements)

* 게시되는 document 또는 기존 document의 Content-Type이 `application/json`이 아니거나, 
둘 중 하나라도 JSON Object로 파싱할 수 없으면, LRS는 반드시 HTTP 상태 코드 `400 Bad Request`로
응답해야 하며(MUST), 이 요청의 결과로 대상 document를 갱신해서는 안 된다(MUST NOT).

* 병합이 성공하면, LRS는 반드시 HTTP 상태 코드 `204 No Content`로 응답해야 한다(MUST).

* Learning Record Provider가 속성을 삭제해야 한다면, 아래에서 설명하는 대로 PUT 요청을 사용해 
document 전체를 교체해야 한다(SHOULD). 


<a name="23-state-resource"></a>
### 2.3 State 리소스 (State Resource)

<a name="description-4"></a>
##### 설명 (Description)

일반적으로 이 리소스는 자체 내부 저장소가 없거나 여러 기기에 걸쳐 상태를 유지해야 하는 
Learning Record Provider를 위한 임시 작업 공간(scratch area)이다. 

<a name="details-5"></a>
##### 세부 사항 (Details)

호출의 의미는 "stateId" 파라미터에 따라 결정된다. 이 파라미터가 포함되면, GET과 DELETE 메서드는 
"stateId"로 식별되는 정의된 단일 state document에 대해 동작한다. 그렇지 않으면 GET은 사용 가능한 id들을 반환하고, 
DELETE는 다른 파라미터로 주어진 맥락의 모든 state를 삭제한다. 이 리소스에는
[동시성 제어(Concurrency)](#31-concurrency)가 적용된다.

<a name="single-document-put--post--get--delete"></a>
###### 단일 Document (Single Document) (PUT | POST | GET | DELETE)

엔드포인트 예시: http://example.com/xAPI/activities/state

지정된 Activity, Agent, registration(지정된 경우)의 맥락에 존재하며 주어진 "stateId"로 지정된 
document를 저장, 변경, 조회 또는 삭제한다.  

**내용(Content) (PUT | POST):** 저장하거나 갱신할 document.  
**내용(Content) (GET | DELETE):** 없음.  

**반환값(Returns) (PUT | POST | DELETE):** `204 No Content`  
**반환값(Returns) (GET):** `200 OK`, State document 
<table>
	<tr><th>파라미터</th><th>타입</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>이 state와 연관된 Activity id.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>agent</td>
		<td>Agent Object (JSON)</td>
		<td>이 state와 연관된 Agent.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>registration</td>
		<td>UUID</td>
		<td>이 state와 연관된 registration.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>stateId</td>
		<td>String</td>
		<td>주어진 맥락 안에서 이 state의 id.</td>
		<td>필수</td>
	</tr>
</table>

<a name="multiple-document-get"></a>
###### 다중 Document GET (Multiple Document GET)

엔드포인트 예시: http://example.com/xAPI/activities/state

이 맥락(Activity + Agent \[ + 지정된 경우 registration\])의 모든 state 데이터에 대한 State id를 가져온다. 
"since" 파라미터가 지정되면, 지정된 timestamp 이후(해당 시각 미포함)에 저장되거나 갱신된 
항목으로 제한된다. 

**내용(Content):** 없음.

**반환값(Returns):** `200 OK`, State id 배열  

<table>
	<tr><th>파라미터</th><th>타입</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>이 state들과 연관된 Activity id.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>이 state들과 연관된 Agent.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>registration</td>
		<td>UUID</td>
		<td>이 state들과 연관된 Registration.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>since</td>
		<td>Timestamp</td>
		<td>지정된 Timestamp 이후(해당 시각 미포함)에 저장된 state의 id만 반환한다.</td>
		<td>선택</td>
	</tr>
</table>

<a name="multiple-document-delete"></a>
###### 다중 Document DELETE (Multiple Document DELETE)

엔드포인트 예시: http://example.com/xAPI/activities/state

이 맥락(Activity + Agent \[+ 지정된 경우 registration\])의 모든 state 데이터를 삭제한다.  

**내용(Content):** 없음.

**반환값(Returns)**: `204 No Content`  
<table>
	<tr><th>파라미터</th><th>타입</th><th>설명</th><th>필수 여부</th></tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>이 state와 연관된 Activity id.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>이 state와 연관된 Agent.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>registration</td>
		<td>UUID</td>
		<td>이 state와 연관된 Registration.</td>
		<td>선택</td>
	</tr>
</table>


<a name="24-agents-resource"></a>
### 2.4 Agents 리소스 (Agents Resource)

Agents 리소스는 디렉터리 서비스와 같은 외부 서비스에서 얻은 Agent 정보를 결합한 특별한 Object를 
조회하는 방법을 제공한다. 이 리소스에는 [동시성 제어(Concurrency)](#31-concurrency)가 적용된다.

<a name="combined-information-get"></a>
###### 통합 정보 GET (Combined Information GET)

<a name="details-6"></a>
###### 세부 사항 (Details)

예시 엔드포인트: http://example.com/xAPI/agents

지정된 Agent에 대한 특수한 Person Object를 반환한다. Person Object는 Agent Object와 매우 유사하지만, 
각 속성이 단일 값을 갖는 대신 배열 값을 가지며, 여러 개의 식별 속성을 포함하는 것이 허용된다. 
이는 FOAF의 person 개념과는 다르다. 여기서 person은 LRS의 Agent 데이터를 사람 중심으로 바라본 관점을 
나타내기 위해 사용되며, Agent는 하나의 페르소나(persona, 하나의 맥락 속에 있는 한 사람)만을 가리킨다.  

"agent" 파라미터는 단일 식별자를 가지며 배열이 없는 일반 Agent Object이다. 
이는 Person Object도 아니고 Group도 아니다. 

**Content:** 없음.

**Returns:** `200 OK`, Person Object

<table>
	<tr><th>파라미터 (Parameter)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>확장된 Agent 정보를 가져오는 데 사용할 Agent 표현.</td>
		<td>필수</td>
	</tr>
</table>

<a name="requirements-9"></a>
###### 요구사항 (Requirements)
* Person Object에 대해 여러 개의 식별 속성을 반환할 수 있는 LRS는 
접속 자격 증명(credentials)에 명시적으로 부여된 상향된 권한을 요구해야 한다(SHOULD). 
* LRS는 권한이 충분하지 않은 요청을 `403 Forbidden`으로 거부해야 한다(SHOULD).
* LRS가 반환할 Agent에 대한 추가 정보를 갖고 있지 않더라도, 
LRS는 조회 시 반드시 Person Object를 반환해야 한다(MUST). 다만 그 Person Object에는 
요청된 Agent와 연관된 정보만 포함된다. 

__참고:__ 이는 LRS가 사전에 알지 못하는 Agent에 대한 요청이 들어오더라도, 
요청에서 받은 Agent 정보를 담은 Person object를 여전히 반환한다는 의미이다. 

<a name="person-properties"></a>
###### Person 속성 (Person Properties)

<a name="details-7"></a>
###### 세부 사항 (Details)

<table>
	<tr><th>속성 (Property)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>objectType</td>
		<td>String</td>
		<td><code>Person</code></td>
		<td>필수</td>
	</tr>
	<tr>
		<td>name</td>
		<td>Array of strings.</td>
		<td>조회된 Agent들의 이름 목록.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td><a href="http://xmlns.com/foaf/spec/#term_mbox">mbox</a></td>
		<td>Array of IRIs in the form "mailto:email address".</td>
		<td>조회된 Agent들의 이메일 주소 목록.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td><a href="http://xmlns.com/foaf/spec/#term_mbox_sha1sum">mbox_sha1sum</a></td>
		<td>Array of strings.</td>
		<td>mailto IRI(mbox 속성에 들어가는 것과 같은)의 SHA1 해시 목록.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>openid*</td>
		<td>Array of strings.</td>
		<td>조회된 Agent들을 고유하게 식별하는 openid 목록.</td>
		<td>선택</td>
	</tr>
	<tr>
		<td>account*</td>
		<td>Array of account objects.</td>
		<td>일치시킬 account 목록. 완전한 account Object(homePage와 name)를 
		반드시 제공해야 한다(MUST).</td>
		<td>선택</td>
	</tr>
</table>

함께 보기: [Agent](./xAPI-Data.md#2421-when-the-actor-objecttype-is-agent).

<a name="requirements-10"></a>
###### 요구사항 (Requirements)

* 모든 배열 속성은 Agent Object에서 이름이 비슷한 속성과 동일한 정의를 따르는 
멤버로 반드시 채워져야 한다(MUST).  

* 여기에 나열되지 않은 추가 속성은 이 객체에 추가하지 않아야 하며(SHOULD* NOT), 각 
속성은 반드시 한 번만 나타나야 한다(MUST). 


<a name="25-activities-resource"></a>
### 2.5 Activities Resource

Activities Resource는 LRS로부터 Activity의 전체 설명을 조회하는 방법을 제공한다. 
이 리소스에는 [동시성 제어(Concurrency)](#31-concurrency)가 적용된다.

<a name="full-activity-object-get"></a>
###### 전체 Activity Object GET (Full Activity Object GET)

예시 엔드포인트: http://example.com/xAPI/activities

지정된 Activity Object 전체를 불러온다.  

**Content:** 없음.

**Returns:** `200 OK`, Content 
<table>
	<tr><th>파라미터 (Parameter)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>불러올 Activity와 연관된 id.</td>
		<td>필수</td>
	</tr>
</table>

<a name="requirements-11"></a>
###### 요구사항 (Requirements)

* LRS가 반환할 Activity의 정규(canonical) 정의를 갖고 있지 않더라도, LRS는 조회 시 
여전히 Activity Object를 반환해야 한다(SHOULD*).


<a name="26-agent-profile-resource"></a>
### 2.6 Agent Profile Resource

<a name="description-5"></a>
###### 설명 (Description)

Agent Profile Resource는 State Resource와 매우 유사하며, Agent와 관련된 임의의 키/Document 쌍을 
저장할 수 있게 해 준다. 

<a name="details-8"></a>
###### 세부 사항 (Details)

요청의 의미는 "profileId" 파라미터에 의해 결정된다. 이 파라미터가 포함되면 GET 메서드는 "profileId"로 식별되는 
단일 Document를 대상으로 동작한다. 그렇지 않으면 GET은 사용 가능한 id들을 반환한다.  

<a name="single-agent-or-profile-document-put--post--get--delete"></a>
###### 단일 Agent 또는 Profile Document (Single Agent or Profile Document) (PUT | POST | GET | DELETE)

예시 엔드포인트: http://example.com/xAPI/agents/profile

지정된 Agent의 맥락에서 지정된 Profile Document를 저장, 변경, 조회 또는 삭제한다.  

**Content (PUT | POST):** 저장하거나 갱신할 Document.  
**Content (GET | DELETE):** 없음.  

**Returns (PUT | POST | DELETE):** `204 No Content`  
**Returns (GET):** `200 OK`, 해당 Profile Document  

<table>
	<tr><th>파라미터 (Parameter)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>이 Profile Document와 연관된 Agent.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>profileId</td>
		<td>String</td>
		<td>이 Profile Document와 연관된 profile id.</td>
		<td>필수</td>
	</tr>
</table>

__참고:__ "agent" 파라미터는 Agent Object이며 Group이 아니다. Identified Group에 대해 데이터를 저장하려는 
Learning Record Provider는 Agent Object 안에 해당 Identified Group의 식별자를 사용할 수 있다. 

<a name="multiple-document-get-1"></a>
###### 다중 Document GET (Multiple Document GET)

예시 엔드포인트: http://example.com/xAPI/agents/profile

한 Agent에 대한 모든 Profile Document의 Profile id를 조회한다. "since" 파라미터가 지정되면, 지정된 Timestamp 
이후(해당 시각 미포함)에 저장되거나 갱신된 항목으로 제한된다.  

**Content:** 없음.

**Returns:** `200 OK`, Profile id 배열  

<table>
	<tr><th>파라미터 (Parameter)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>agent</td>
		<td>Agent object (JSON)</td>
		<td>이 Profile Document와 연관된 Agent.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>since</td>
		<td>Timestamp</td>
		<td>지정된 Timestamp 이후(해당 시각 미포함)에 저장된 
			Profile의 id만 반환된다.</td>
		<td>선택</td>
	</tr>
</table>


<a name="27-activity-profile-resource"></a>
### 2.7 Activity Profile Resource

<a name="description-6"></a>
###### 설명 (Description)

Activity Profile Resource는 State Resource와 매우 유사하며, Activity와 관련된 임의의 키/Document 쌍을 
저장할 수 있게 해 준다. 

<a name="details-9"></a>
###### 세부 사항 (Details)

요청의 의미는 "profileId" 파라미터에 의해 결정된다. 이 파라미터가 포함되면, 
GET 메서드는 "profileId"로 식별되는 단일 Document를 대상으로 동작한다. 
그렇지 않으면 GET은 사용 가능한 id들을 반환한다.

<a name="single-document-put--post--get--delete-1"></a>
###### 단일 Document (Single Document) (PUT | POST | GET | DELETE)

예시 엔드포인트: http://example.com/xAPI/activities/profile

지정된 Activity의 맥락에서 지정된 Profile Document를 저장, 변경, 조회 또는 삭제한다.  

**Content (PUT | POST):** 저장하거나 갱신할 Document.  
**Content (GET | DELETE):** 없음.  

**Returns (PUT | POST | DELETE)** `204 No Content`  
**Returns (GET):** `200 OK`, 해당 Profile Document  
<table>
	<tr><th>파라미터 (Parameter)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>이 Profile Document와 연관된 Activity id.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>profileId</td>
		<td>String</td>
		<td>이 Profile Document와 연관된 profile id.</td>
		<td>필수</td>
	</tr>
</table>

<a name="multiple-document-get-2"></a>
###### 다중 Document GET (Multiple Document GET)

예시 엔드포인트: http://example.com/xAPI/activities/profile

한 Activity에 대한 모든 Profile Document의 Profile id를 조회한다. "since" 파라미터가 지정되면, 지정된 Timestamp 
이후(해당 시각 미포함)에 저장되거나 갱신된 항목으로 제한된다.  

**Content:** 없음.

**Returns:** `200 OK`, Profile id 배열  

<table>
	<tr><th>파라미터 (Parameter)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th><tr>
	<tr>
		<td>activityId</td>
		<td>Activity id (IRI)</td>
		<td>이 Profile Document들과 연관된 Activity id.</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>since</td>
		<td>Timestamp</td>
		<td>지정된 Timestamp 이후(해당 시각 미포함)에 저장된 Profile Document의 id만 
		반환된다.</td>
		<td>선택</td>
	</tr>
</table>



<a name="28-about-resource"></a>
### 2.8 About Resource

<a name="description-7"></a>
###### 설명 (Description)

지원하는 xAPI 버전을 포함하여 이 LRS에 대한 정보를 담은 JSON Object를 반환한다.

<a name="rationale-1"></a>
###### 근거 (Rationale)

이 리소스는 주로 여러 xAPI 버전을 지원하는 Client가 LRS와 통신할 때 어떤 버전을 사용할지 결정할 수 있도록 
하기 위해 존재한다. 다른 용도가 생겨날 수 있도록 Extension이 포함되어 있다.

<a name="details-10"></a>
###### 세부 사항 (Details)

<a name="information-get"></a>
###### 정보 GET (Information GET)

예시 엔드포인트: http://example.com/xAPI/about

**Content:** 없음.

**Returns:** `200 OK`, 이 LRS에 대한 기본 메타데이터를 담은 JSON object
<table border="1">
	<tr><th>속성 (Property)</th><th>타입 (Type)</th><th>설명 (Description)</th><th>필수 여부 (Required)</th></tr>
	<tr>
		<td>version</td>
		<td>Array of version strings</td>
		<td>이 LRS가 지원하는 xAPI 버전</td>
		<td>필수</td>
	</tr>
	<tr>
		<td>extensions</td>
		<td><a href="./xAPI-Data.md#41-extensions">Object</a></td>
		<td>필요에 따른 기타 속성들의 맵</td>
		<td>선택</td>
	</tr>

</table>

<a name="requirements-12"></a>
###### 요구사항 (Requirements)

* LRS는 위에서 설명한 JSON Document를 반드시 반환해야 하며(MUST), 이 Document의 "version" 속성에는
각 메이저 버전별로 LRS가 준수하는 최신 마이너 및 패치 버전이 포함되어야 한다.
    * 이 명세의 버전 1.0.0의 경우, 이는 `1.0.0`이 반드시 포함되어야 함(MUST)을 의미하며,
    `0.9`와 `0.95`는 포함될 수 있다(MAY). (이 요구사항의 목적상 `0.9`와 `0.95`는
    메이저 버전으로 간주한다.)
* Extension 외부에서 이 객체에 추가 속성을 추가해서는 안 되며(MUST NOT), 각 
속성은 반드시 한 번만 나타나야 한다(MUST).  
* LRS는 이 리소스에 대해 인증되지 않은 접근을 허용해야 한다(SHOULD).
* LRS는 [버전 관리(Versioning)](#33-versioning)에 따라 원래라면 요구되었을 버전 헤더 기반의 요청 거부를 
해서는 안 된다(MUST NOT).


<a name="30-data-validation"></a>
## 3.0 데이터 검증 (Data Validation)

<a name="description-8"></a>
###### 설명 (Description)

xAPI 내에서 LRS의 기능은 Statement를 저장하고 조회하는 것이다. 이러한 작업을 수행하기에 충분한 정보가 있는 한, 
LRS는 그 작업을 수행할 것으로 기대된다. Experience API에서 Statement의 검증은 오로지 구문(syntax)에만 
초점을 두며 의미(semantics)는 다루지 않는다. Verb 정의, Activity 타입, Extension 사이에서 유효한 의미를 보장하는 
규칙을 강제하는 것은 Statement를 전송하는 Learning Record Provider의 책임이다. 

<a name="requirements-13"></a>
###### 요구사항 (Requirements)

* LRS는 구조에 관한 규칙을 강제해야 한다(SHOULD). 
* LRS는 의미에 관한 규칙을 강제하지 않아야 한다(SHOULD NOT).  


<a name="31-concurrency"></a>
### 3.1 동시성 제어 (Concurrency)

<a name="description-9"></a>
##### 설명 (Description)
동시성 제어는 Client가 오래된 데이터에 기반하여 LRS에 Document를 PUT, POST 또는 DELETE하지 않도록
보장한다.

<a name="details-11"></a>
##### 세부 사항 (Details)
xAPI는 PUT, POST 또는 DELETE가 기존 데이터를 덮어쓰거나 제거할 수 있는 API의 다음 부분에서
낙관적 동시성 제어(optimistic concurrency control)를 구현하기 위해 HTTP 1.1 엔티티 태그([ETags](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19))를
사용한다.

* State Resource
* Agent Profile Resource 
* Activity Profile Resource

<a name="client-requirements"></a>
##### Client 요구사항 (Client Requirements)
State 충돌은 일어날 가능성이 낮으므로, State Resource는 동시성 헤더 없는 PUT, POST, DELETE 요청을 허용한다.
아래 요구사항은 Agent Profile Resource와 Activity Profile Resource에만 적용된다.

* Agent Profile Resource 또는 Activity Profile 
Resource에 PUT 요청을 보내는 Client는 "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" 헤더 또는 
[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26) 헤더를 반드시 포함해야 한다(MUST).

* Agent Profile Resource 또는 Activity Profile 
Resource에 POST 요청을 보내는 Client는 "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" 헤더 또는 
[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26) 헤더를 포함해야 한다(SHOULD*).

* Agent Profile Resource 또는 Activity Profile 
Resource에 DELETE 요청을 보내는 Client는 "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" 헤더를 포함해야 한다(SHOULD*).

* Client는 ETag 값을 직접 계산하기보다 LRS가 제공한 ETag 값을 사용해야 한다(SHOULD*). 

<a name="lrs-requirements-4"></a>
##### LRS 요구사항 (LRS Requirements)

* GET 요청에 응답하는 LRS는 응답에 ETag HTTP 헤더를 반드시 추가해야 한다(MUST).
* 전송 인코딩(transfer encoding)을 사용하지 않거나 identity 전송 인코딩을 사용하여 GET 요청에 
응답하는 LRS는 ETag 헤더의 값을 콘텐츠의 SHA-1 다이제스트를 16진수 문자열로 나타낸 값으로 반드시 계산해야 한다(MUST). 
이 16진수 문자열은 숫자와 소문자만으로 표현해야 하며(SHOULD), 대문자는 사용하지 않아야 한다(SHOULD NOT). 
ETag를 이 방식으로 계산해야 한다는 요구사항은 향후 버전의 명세에서 제거될 예정이다.
* identity가 아닌 전송 인코딩을 사용하여 GET 요청에 응답하는 LRS는 기존 웹 인프라가 ETag를 해석하는 방식 때문에 
포함되는 ETag를 위와 같이 계산해서는 안 된다(MUST NOT).
* [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19)에 정의된 대로, 
GET 요청에 응답하는 LRS는 헤더 값을 반드시 따옴표로 감싸야 한다(MUST).  
* PUT 요청에 응답하는 LRS는 "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" 헤더에 ETag가 포함된 경우, Client가 Document를 마지막으로 
조회한 이후에 이루어진 수정을 감지하기 위해 RFC2616, HTTP 1.1에 설명된 대로 이 헤더를 반드시 처리해야 한다(MUST).
* PUT 요청에 응답하는 LRS는 "[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26)" 헤더에 "*"가 포함된 경우, Client가 알지 못하는 리소스가 
존재하는지 감지하기 위해 RFC2616, HTTP 1.1에 설명된 대로 이 헤더를 반드시 처리해야 한다(MUST).
* POST 또는 DELETE 요청에 응답하는 LRS는 "[If-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.24)" 헤더에 ETag가 포함된 경우, 
Client가 Document를 마지막으로 조회한 이후에 이루어진 수정을 감지하기 위해 RFC2616, HTTP 1.1에 설명된 대로 이 헤더를 처리해야 한다(SHOULD*).
* POST 요청에 응답하는 LRS는 
"[If-None-Match](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.26)" 헤더에 "*"가 포함된 경우, Client가 알지 못하는 리소스가 
존재하는지 감지하기 위해 RFC2616, HTTP 1.1에 설명된 대로 이 헤더를 처리해야 한다(SHOULD*).

위의 PUT 요청 사례 중 어느 하나에서 헤더 전제 조건(precondition)이 충족되지 않으면, LRS는:

* HTTP 상태 `412 Precondition Failed`를 반드시 반환해야 한다(MUST).
* 리소스를 수정해서는 안 된다(MUST NOT). 

위의 POST 또는 DELETE 요청 사례 중 어느 하나에서 헤더 전제 조건이 충족되지 않으면, LRS는:

* HTTP 상태 `412 Precondition Failed`를 반환해야 한다(SHOULD*).
* 리소스를 수정하지 않아야 한다(SHOULD* NOT). 

이미 존재하는 리소스에 대해 두 헤더 중 어느 것도 없는 PUT 요청을 받으면, LRS는:

* HTTP 상태 `409 Conflict`를 반드시 반환해야 한다(MUST).
* Learning Record Provider가 다음을 해야 한다(SHOULD)는 설명을 담은 응답을 반드시 반환해야 한다(MUST).
	* 리소스의 현재 상태를 확인한다.
	* 충돌을 해결하기 위해 현재 ETag로 "If-Match" 헤더를 설정한다.
* 리소스를 수정해서는 안 된다(MUST NOT).


<a name="32-error-codes"></a>
### 3.2 오류 코드 (Error Codes)

<a name="description-10"></a>
##### 설명 (Description)

이 명세는 여러 요구사항을 정의하며, 그중 일부는 특정 조건에서 LRS가 요청을 수락하거나 거부하고,
응답을 반환하고, 기타 동작을 수행하도록 부과한다. LRS가 요청을 거부해야 하는 경우에는 
적절한 오류 코드가 해당 요구사항의 일부로 명시되어 있다. 

이러한 요구사항 중 어느 것도, LRS가 이 명세의 범위를 벗어난 조건에 근거하여 요청을 거부하거나 다르게 응답 또는 
동작하도록 구성 가능하다는 개념과 모순되지 않는다. 

이러한 조건 중 하나는 권한(permission)이다. 예를 들어, LRS는 특정 자격 증명 집합에 권한을 부여하여 
그 자격 증명으로는 특정 agent와 관련된 Statement만 발행할 수 있도록 할 수 있다. 그런 다음 해당 자격 증명을 
사용하면서 그 agent와 관련되지 않은 모든 statement를 거부할 수 있다. LRS가 부여할 수 있는 권한은 
섹션 [4.2](#42-oauth-10-authorization-scope)의 권장 OAuth 인가 범위(Authorization scope) 값 목록을 제외하면 
이 명세의 범위를 벗어난다. 

권한은 GET 요청에 대해 LRS가 반환하는 응답에도 영향을 줄 수 있다. 예를 들어, 
어떤 자격 증명 집합은 특정 Actor에 관한 Statement만 볼 수 있는 권한을 가질 수 있으며, 이 경우
LRS는 반환되는 Statement를 필터링하여 해당 Actor와 관련되지 않은 Statement를 모두 제외한다. 자세한 내용은 
[GET Statements](#213-get-statements)를 참고한다. 

이 명세에서 명시적으로 허용하는 경우, 사용된 자격 증명은 요청을 처리하는 LRS의 동작에도 영향을 줄 수 있다. 
예를 들어, LRS는 일반적으로 Statement의 "authority" 속성을 덮어쓰지만, Statement 제출에 사용된 자격 증명과 
강한 신뢰 관계가 연결되어 있다면 제출된 authority를 수락하기도 한다. 자세한 내용은 [Authority](./xAPI-Data.md#249-authority)를 참고한다. 

LRS가 설정한 권한으로 인해, 기술적으로는 적합한(conformant) LRS가 적합성 테스트(conformance testing)에서 실패할 수 있다. 
이는 테스트 소프트웨어가 보낸 요청이 권한을 근거로 거부되는 경우에 발생할 수 있다. 이러한 이유로
LRS는 구성 가능해야 하며, 또는 테스트에 사용되는 자격 증명에 충분한 권한이 부여되어 있어야 하며,
그렇게 하여 권한 제한이 적합성 테스트 결과에 영향을 주지 않도록 해야 한다. 

또 다른 조건은 전송된 요청이 LRS가 설정한 크기 제한을 초과하는 경우이다. LRS가 어떤 크기의 요청이든 
항상 수락하기를 기대하는 것은 비합리적이다. LRS는 적합하다고 판단하는 어떤 크기 제한이든 선택할 수 있지만,
적합성 테스트 중에는 크기 제한을 적용하지 않도록 구성 가능해야 한다. 물론 하드웨어 등의 한계로 인해 
적합성 테스트 중에도 일부 크기 제한은 여전히 존재하겠지만, 이러한 제한은 테스트 실행에 영향을 주지 않을 만큼 
충분히 높을 것으로 기대된다. 

LRS는 악의적인 의도가 의심되는 경우, 예를 들어 짧은 시간에 예상치 못하게 많은 수의 요청이 들어오는 경우에도
요청을 거부하거나 자격 증명을 폐기할 수 있다. 이러한 제한은 적합성 테스트 중에 발생하는 요청 속도가 
어떤 속도 제한(rate limit)도 유발하지 않을 만큼 충분히 높을 것으로 기대된다.

<a name="details-12"></a>
##### 세부 사항 (Details)
아래 목록은 API의 여러 메서드에서 반환될 수 있는 HTTP 오류 코드에 대한 일반적인 지침을 제공한다. 

* `400 Bad Request` - 유효하지 않거나 누락된 인수로 인해 
발생한 오류 상태를 나타낸다. "유효하지 않은 인수(invalid arguments)"라는 용어에는 
형식이 잘못된 JSON이나 유효하지 않은 Object 구조가 포함된다.

* `401 Unauthorized` - 인증이 필요함을 나타내거나, 요청에 인증 정보가 
포함된 경우에는 제공된 자격 증명이 거부되었음을 나타낸다.

* `403 Forbidden` - 제공된 자격 증명으로는 해당 요청이 허가되지 않음을 
나타낸다. 이는 제공된 자격 증명을 거부하는 것과는 다르다는 점에 유의한다. 이 경우 자격 증명은 
검증되었지만, 인증된 Client가 해당 작업을 수행하도록 허용되지 않은 것이다.

* `404 Not Found` - 요청한 리소스를 찾을 수 없음을 나타낸다. 
고유하게 식별되는 리소스를 반환하는 모든 메서드, 예를 들어 특정 Document를 대상으로 하는 State, Agent Profile, 
Activity Profile Resource 요청이나 단일 Statement를 조회하는 메서드에서 반환될 수 있다.

* `409 Conflict` - State Resource, Agent Profile Resource, Activity Profile Resource 
요청의 경우나 Statement Resource의 PUT 또는 POST 호출에서, 리소스의 현재 상태와의 충돌로 인해 
발생한 오류 상태를 나타낸다. 자세한 내용은 섹션 [3.1 동시성 제어(Concurrency)](#31-concurrency)를 참고한다.

* `412 Precondition Failed` - State, Agent Profile 또는 Activity Profile 
API 요청의 경우, 요청과 함께 전달된 전제 조건이 충족되지 않아 발생한 오류 상태를 나타낸다. 
자세한 내용은 섹션 [6.3 동시성 제어(Concurrency)](#31-concurrency)를 참고한다.

* `413 Request Entity Too Large` - Statement 또는 Document의 크기(또는 요청에 포함된 
Attachment의 크기)가 LRS가 허용하는 최대 크기보다 커서 LRS가 이를 거부했음을 
나타낸다. 

* `429 Too Many Requests` - LRS가 주어진 시간 동안 Client 또는 자격 증명 집합으로부터 
너무 많은 요청을 받아 해당 요청을 거부했음을 나타낸다. 

* `500 Internal Server Error` - 일반적인 오류 상태를 나타내며, 보통 서버에서 처리 중 
발생한 예기치 못한 예외에 해당한다.

<a name="requirements-14"></a>
##### 요구사항 (Requirements)

* LRS는 위 목록에서 오류 상태에 가장 적합한 오류 코드를 반드시 반환해야 한다(MUST).

* LRS는 응답에 오류의 원인을 설명하는 메시지를 반환해야 한다(SHOULD).

* LRS는 오류의 형식을 결정하기 위해 [RFC 7231](http://tools.ietf.org/html/rfc7231#section-5.3)에 설명된 콘텐츠 협상(content negotiation)을 사용해야 한다(SHOULD).

* LRS는 (콘텐츠 협상을 통해) 일반 텍스트, HTML, JSON 형식의 오류 응답을 허용해야 한다(SHOULD).

* Learning Record Provider는 콘텐츠 협상이 가능하도록 요청에 "Accept" 헤더를 함께 보내야 한다(SHOULD).

* LRS는 content type 헤더가 요청에 포함된 콘텐츠와 일치하지 않거나, 요청의 구조가 특정 content type에 대해 
이 명세에서 기술한 구조와 일치하지 않는 모든 요청을 `400 Bad Request` 상태로 거부해야 한다(SHOULD*). 예를 들어, 요청의 콘텐츠가 JSON 형식이라면 
content type은 `application/json`일 것으로 기대된다. content type이 application/x-www-form-urlencoded라면, 
요청에는 [대체 요청 구문(Alternate Request Syntax)](#13-alternate-request-syntax)에 기술된 대로 method 파라미터가 포함될 것으로 기대된다.

* LRS는 이 명세에서 의도된 맥락으로 LRS가 인식하지 못하는 파라미터를 사용하는 모든 요청을 
`400 Bad Request` 상태로 반드시 거부해야 한다(MUST). 
( __참고:__ LRS는 이 명세에 없는 파라미터를 인식하고 그에 따라 동작할 수 있다(MAY)).

* LRS는 대소문자만 다르고 이 명세에 기술된 파라미터와 일치하는 파라미터를 사용하는 
모든 요청을 `400 Bad Request` 상태로 반드시 거부해야 한다(MUST).

* LRS는 statement 묶음(batch) 내의 Statement 중 하나라도 거부되면 해당 묶음 전체를 반드시 거부해야 한다(MUST).

* LRS는 요청과 연관된 자격 증명이 해당 요청을 수행할 권한을 갖고 있지 않아 
LRS가 거부하는 모든 요청을 `403 Forbidden` 상태로 반드시 거부해야 한다(MUST). 

* LRS는 Attachment, Statement 또는 Document의 크기가 LRS가 허용하는 최대 크기보다 커서 
LRS가 거부하는 모든 요청을 `413 Request Entity Too Large` 상태로 반드시 거부해야 한다(MUST).

* LRS는 Attachment, Statement, Document의 크기 제한을 임의로 선택할 수 있으며(MAY), 예를 들어 authority별로처럼 
어떤 기준에 따라서든 이 제한을 다르게 적용할 수 있다(MAY).

* LRS는 주어진 시간 동안 특정 Client 또는 자격 증명 집합으로부터 너무 많은 요청을 받아 
LRS가 거부하는 모든 요청을 `429 Too Many Requests` 상태로 반드시 거부해야 한다(MUST). 

* LRS는 속도 제한을 임의로 선택할 수 있으며(MAY), 예를 들어 authority별로처럼 어떤 기준에 따라서든 이 제한을 다르게 적용할 수 있다(MAY).

다음 요구사항은 LRS가 구현한 제한이나 권한이 적합성 테스트 소프트웨어의 실행에 영향을 주지 않도록 
보장하기 위해, 적합성 테스트를 목적으로 존재한다. 

* LRS는 특정 자격 증명 집합으로부터의 요청을 권한을 근거로 거부하지 않도록 구성 가능해야 
한다(SHOULD*). 이 자격 증명 집합은 적합성 테스트에 사용해야 하지만(SHOULD*), 운영 중인 시스템에서는 
삭제하거나 비활성화할 수 있다(MAY). 

* LRS는 합리적인 어떤 크기의 Attachment, Statement 또는 Document든 수락하도록 반드시 구성 가능해야 
한다(MUST) (위 내용 참고).

* LRS는 합리적인 어떤 속도의 요청이든 수락하도록 반드시 구성 가능해야 한다(MUST). 


<a name="33-versioning"></a>
### 3.3 버전 관리 (Versioning)

<a name="rationale-2"></a>
###### 근거 (Rationale)

향후 스펙 개정에서는 Statement에 속성이 추가되는 것과 같은 변경이 도입될 수 있다. 시맨틱 버저닝(Semantic 
Versioning)을 사용하면 스펙이 변경되더라도 Client와 LRS가 상호운용성을 유지할 수 있다.

<a name="details-13"></a>
###### 세부 사항 (Details)

버전 1.0.0부터 xAPI는 [Semantic Versioning 1.0.0](http://semver.org/spec/v1.0.0.html)에 따라 버전이 매겨진다.  
Client의 모든 요청과 LRS의 모든 응답에는 이름이 `X-Experience-API-Version`이고 값이 버전인 HTTP 헤더가 
포함된다. 예를 들어 버전 1.0.3의 경우 ``X-Experience-API-Version : 1.0.3``이다. 
이 스펙의 현재 버전은 [개정 이력(Revision History)](./xAPI-About.md#appendix-a-revision-history)을 참고한다. 

__참고:__ 1.0.0보다 이후의 스펙 패치 버전에서는 "X-Experience-API-Version" 헤더가 
[Statement의 version 속성](./xAPI-Data.md#2410-version)과 일치하지 않는다. version 속성은 스펙의 모든 1.0.x 버전에서 항상 `1.0.0`이다.
"X-Experience-API-Version" 헤더를 통해 LRS와 Client는 따르고 있는 스펙의 정확한 패치 버전을 판단할 수 
있다. 1.0.x 버전들 사이에서 통신 비호환성이 발생해서는 안 되지만, 이전에 의도되었던 동작에 대한 
명확화가 이루어지는 경우가 있다.

<a name="lrs-requirements-5"></a>
###### LRS 요구사항 (LRS Requirements)

* LRS는 모든 응답에 "X-Experience-API-Version" 헤더를 반드시 포함해야 한다(MUST).
* LRS는 이 헤더를 최신 패치 버전으로 반드시 설정해야 한다(MUST).
* LRS는 버전 헤더가 `1.0`인 요청을 버전 헤더가 `1.0.0`인 것처럼 반드시 수락해야 한다(MUST).
* LRS는 버전 헤더가 1.0.0보다 이전 버전인 요청을 반드시 거부해야 한다(MUST). 단, 해당 요청이 
헤더에 지정된 이전 버전을 완전히 준수하는 구현으로 라우팅되는 경우는 예외이다.
* LRS는 버전 헤더가 없는 요청을 반드시 거부해야 한다(MUST). 단, 해당 요청이 
0.9를 완전히 준수하는 구현으로 라우팅되는 경우는 예외이다.
* LRS는 버전 헤더가 `1.0.`으로 시작하는 요청을, 그 요청이 그 밖의 측면에서 유효하다면 반드시 수락해야 한다(MUST). 
* LRS는 버전 헤더가 `1.1.0` 이상인 요청을 반드시 거부해야 한다(MUST).
* LRS는 이러한 거부를 문제에 대한 간단한 설명을 포함한 `400 Bad Request` 오류로 응답하는 방식으로 
반드시 수행해야 한다(MUST).

<a name="client-requirements-1"></a>
###### Client 요구사항 (Client Requirements)

* Client는 모든 요청에 "X-Experience-API-Version" 헤더를 반드시 포함해야 한다(MUST).
* Client는 이 헤더를 최신 패치 버전으로 반드시 설정해야 한다(MUST).
* Client는 버전이 `1.0.0` 이상인 응답을 수신하는 것을 허용해야 한다(SHOULD).
* Client는 추가 속성이 있는 데이터 구조를 수신하는 것을 허용해야 한다(SHOULD).
* Client는 스펙 버전 1.0.0에 정의되지 않은 모든 속성을 무시해야 한다(SHOULD).

<a name="conversion-requirements"></a>
###### 변환 요구사항 (Conversion Requirements)

* 더 새로운 버전의 Statement를 이전 버전 형식으로 변환해서는 안 된다(MUST NOT). 예를 들어 버전 차이를 
처리하기 위한 목적이라도 마찬가지이다.
* 이전 버전의 Statement는 [부록 A: Statement를 1.0.0으로 변환하기](#appendix-a-converting-statements-to-100)에 
설명된 방법을 따르는 경우에만 더 새로운 버전으로 변환할 수 있다(MAY).


<a name="40-authentication"></a>
## 4.0 인증 (Authentication)

<a name="rationale-3"></a>
###### 근거 (Rationale)

상호운용성과 환경마다 다른 보안 요구사항 사이의 균형을 맞추기 위해 여러 가지 
인증 방식이 정의되어 있다.

<a name="details-14"></a>
###### 세부 사항 (Details)
이 스펙에는 다음 인증 방식이 정의되어 있다. 각 LRS는 이 방식들 중 적어도 하나를 구현하며, 
이 스펙에 정의되지 않은 추가 방식을 구현할 수도 있다. 

* 서명 방식 "HMAC-SHA1", "RSA-SHA1", "PLAINTEXT"를 사용하는 
[OAuth 1.0 (RFC 5849)](http://tools.ietf.org/html/rfc5849)
* [HTTP 기본 인증(HTTP Basic Authentication)](http://tools.ietf.org/html/rfc7235)
* 공통 접근 카드(Common Access Cards)

공통 접근 카드(Common Access Cards)는 이 스펙에서 인증 방식으로 정의되어 있지만, 이 인증 방식의 구현 세부 사항은 
정의되어 있지 않다. xAPI 워킹 그룹은 공통 접근 카드를 인증 방식으로 구현하는 LRS 개발자들이 
향후 버전의 스펙에서 이 인증 방식의 세부 사항을 정의하는 데 협력할 것을 권장한다. 

HTTP 기본 인증(HTTP Basic Authentication)은 [RFC 7235](http://tools.ietf.org/html/rfc7235)에 명확하고 완전하게 
정의되어 있으므로, 이 스펙에서는 이에 대한 추가 세부 사항을 제공하지 않는다. 

<a name="requirements-15"></a>
###### 요구사항 (Requirements)

* LRS는 이 스펙에 정의된 인증 방식 중 적어도 하나를 사용한 인증을 반드시 
지원해야 한다(MUST).

* LRS는 Statement의 유효성에 대한 결정과, 사용된 자격 증명(credentials)에 기반하여 어떤 작업을 
수행할 수 있는지에 대한 판단을 반드시 직접 수행하거나 위임해야 한다(MUST).


<a name="41-oauth-10-authentication-scenarios-and-methods"></a>
### 4.1 OAuth 1.0 인증 시나리오와 방식 (OAuth 1.0 Authentication Scenarios and Methods)

아래의 매트릭스와 요구사항은 OAuth에서 사용되는 가능한 인증 시나리오를 설명하고, 이 시나리오에서 사용할 
인증 워크플로를 권장한다. 각 시나리오에 대해 설명하는 절차는 포괄적인 것을 의도하지 않으며, 
표준 OAuth 워크플로와의 차이점을 개략적으로 설명하는 것이다. 

이 절의 요구사항은 LRS가 OAuth 1.0을 지원하는 경우에만 적용된다.

**등록된 애플리케이션(registered application)**이란 LRS에 등록되어 있으며 OAuth 컨슈머(consumer)로서 LRS에 
인증하는 애플리케이션이다.

**알려진 사용자(known user)**란 LRS 또는 LRS가 사용자 정의를 위해 신뢰하는 시스템에 있는 사용자 계정이다.


<table border="1">
<tr><th></th><th>알려진 사용자</th><th>알려지지 않은 사용자</th></tr>
<tr>
<td>애플리케이션이 등록됨</td>
<td>OAuth의 표준 워크플로.</td>
<td>LRS는 추가 사용자 자격 증명 없이 애플리케이션이 xAPI에 접근하는 것을 신뢰한다. OAuth 토큰 단계는 수행되지 않는다</td>
</tr>
<tr>
<td>애플리케이션이 등록되지 않음</td>
<td>애플리케이션 Agent가 등록된 Agent로 식별되지 않으며, LRS는 그 신원에 대해 어떤 가정도 할 수 없다.</td>
<td></br></td>
</tr>
<tr>
<td>애플리케이션 없음</td>
<td>관여하는 애플리케이션이 없으므로 OAuth 대신 HTTP 기본 인증을 사용한다.</td>
<td></br></td>
</tr>
<tr>
<td>인증 없음</td>
<td align="center"colspan="2">LRS가 지원할 수 있다(MAY). 주로 테스트 목적일 수 있다.</td>

</tr>

</table>

<a name="requirements-16"></a>
##### 요구사항 (Requirements)

* LRS는 애플리케이션의 이름과 고유한 컨슈머 키(consumer key, 식별자)를 반드시 기록해야 한다(MUST).
* LRS는 이 등록을 완료하기 위한 메커니즘을 반드시 제공하거나, 그러한 메커니즘을 제공하는 다른 시스템에 
위임해야 한다(MUST).
* LRS는 다음과 같이 xAPI를 완전히 지원하도록 반드시 구성될 수 있어야 한다(MUST):
	* 아래의 어떤 방식으로든.
	* 아래의 어떤 워크플로 시나리오에서든.
* LRS는 (보안상의 이유로) 다음을 할 수 있다(MAY): 
	* 아래 방식 중 일부만 지원한다.
	* 알려진 사용자 또는 등록된 애플리케이션을 제한한다.
* LRS는 최소한 "HMAC-SHA1" 및 "RSA-SHA1" 서명을 사용하는 OAuth를 제공해야 한다(SHOULD).

<a name="application-registered--known-user-process-and-requirements"></a>
###### 애플리케이션 등록됨 + 알려진 사용자: 절차와 요구사항 (Application registered + known user Process and Requirements)
**절차:** OAUth 1.0의 표준 워크플로를 사용한다. 

**요구사항:**
* LRS는 표준 OAuth 워크플로를 완료하기 위해 [OAuth 인가 범위(OAuth Authorization Scope)](#42-oauth-10-authorization-scope)의 
리소스를 반드시 지원해야 한다(MUST) (세부 사항은 이 스펙에 포함되지 않는다).
* 이 형태의 인증이 Statement 기록에 사용되고 authority가 지정되지 않은 경우, LRS는 
authority를 등록된 애플리케이션을 나타내는 Agent와 알려진 사용자를 나타내는 Agent로 구성된 
Group으로 기록해야 한다(SHOULD).

<a name="application-registered--user-unknown-process-and-requirements"></a>
###### 애플리케이션 등록됨 + 알려지지 않은 사용자: 절차와 요구사항 (Application registered + user unknown Process and Requirements)

**절차:** 
LRS는 등록된 애플리케이션의 자격 증명과 빈 토큰(token) 및 빈 토큰 시크릿(token secret)으로 
OAuth 서명된 요청을 수용한다.

**요구사항:**
* 이 형태의 인증이 Statement 기록에 사용되는 경우, LRS는 authority를 
등록된 애플리케이션을 나타내는 Agent로 기록해야 한다(SHOULD).

<a name="application-not-registered--known-user-process-and-requirements"></a>
###### 애플리케이션 등록되지 않음 + 알려진 사용자: 절차와 요구사항 (Application Not Registered + Known User Process and Requirements)

**절차:**
Learning Record Provider는 빈 문자열로 이루어진 컨슈머 시크릿(consumer secret)을 사용하여, "consumer_name" 및 
기타 일반적인 파라미터를 지정해 Temporary Credential Request 엔드포인트를 호출한다. "consumer_name"에는 
접근을 요청하는 애플리케이션을 나타내는 문자열이 들어간다. 

그런 다음 Learning Record Provider는 LRS로부터 얻은 임시 자격 증명을 사용하여 사용자의 브라우저를 
Resource Owner Authorization으로 보낸다. Resource Owner Authorization은 "consumer_name"과 함께 
인가를 요청하는 애플리케이션의 신원을 검증할 수 없다는 경고를 표시하는 페이지를 보여준다.

그 밖의 절차는 표준 OAuth 워크플로를 따른다. 

**요구사항:**
* 이 형태의 인증이 Statement 기록에 사용되는 경우, OAuth는 애플리케이션을 명시하므로 LRS는 
해당 애플리케이션과 인증하는 사용자를 모두 포함하는 authority를 Group으로 반드시 기록해야 한다(MUST).

<a name="no-application--known-user-process-and-requirements"></a>
###### 애플리케이션 없음 + 알려진 사용자: 절차와 요구사항 (No Application + Known User Process and Requirements)
**절차:**
알려진 사용자가 사용하도록 LRS가 제공한 사용자 이름/비밀번호 조합을 사용한다.

**요구사항:**
* 이 형태의 인증이 Statement 기록에 사용되는 경우, LRS는 
authority를 알려진 사용자를 나타내는 Agent로 기록해야 한다(SHOULD).

<a name="no-authorization-process-and-requirements"></a>
###### 인가 없음: 절차와 요구사항 (No Authorization Process and Requirements)

* 요청은 0개 이상의 공백 문자로 이루어진 사용자 이름과 비밀번호에 기반한 HTTP 기본 인증 헤더를 
반드시 포함해야 한다(MUST). 
* 요청은 각각 빈 문자열로 이루어진 사용자 이름과 비밀번호에 기반한 HTTP 기본 인증 헤더를 
포함해야 한다(SHOULD*). 이 경우 HTTP 기본 인증 헤더는 `Basic ` 뒤에 문자열 `:`을 base64로 
인코딩한 값이 붙은 형태가 된다. 그 결과 문자열은 `Basic Og==`이다.

이는 명시적으로 인증되지 않은 요청을 HTTP 기본 인증 챌린지(challenge)를 받아야 하는 요청과 
구별하기 위한 것이다.


<a name="42-oauth-10-authorization-scope"></a>
### 4.2 OAuth 1.0 인가 범위 (OAuth 1.0 Authorization Scope)

<a name="description-11"></a>
##### 설명 (Description)
다음은 xAPI를 사용하여 통신하는 LRS와 애플리케이션이, 애플리케이션에 필요한 것을 달성하면서도 
오용 가능성은 최소화하는 접근 수준을 협상할 수 있도록 설계된 범위(scope)에 대한 권장 사항이다. 
각 범위의 제한은 요청과 연관된 사용자 계정에 적용되는 모든 보안 제한에 추가로 
적용된다.

이 절은 [OAuth 1.0](http://tools.ietf.org/html/rfc5849)을 지원하는 LRS에 대한 요구사항을 설명하지만, 
일부 요소는 [OAuth 2.0](http://tools.ietf.org/html/rfc6749#section-3.3)을 참고했다.

이 절의 요구사항은 LRS가 OAuth 1.0을 지원하는 경우에만 적용된다.

<a name="details-15"></a>
##### 세부 사항 (Details)

다음 표는 xAPI 범위(scope) 값을 나열한다:  
<table>
	<tr><th>범위 (Scope)</th><th>권한 (Permission)</th></tr>
	<tr><td>statements/write</td><td>모든 Statement 쓰기</td></tr>
	<tr>
		<td>statements/read/mine</td>
		<td>"나"가 작성한 Statement 읽기. 즉, 현재 토큰으로 Statement를 
			작성할 경우 LRS가 할당할 authority와 일치하는 authority를 
			가진 Statement.
		</td>
	</tr>
	<tr><td>statements/read</td><td>모든 Statement 읽기</td>
	<tr>
		<td>state</td>
		<td>state 데이터 읽기/쓰기. 현재 토큰과 연관된 Activity 및 Actor로 
			제한되며, 이 관계를 판단할 수 있는 범위 내에서 
			적용된다.
		</td>
	</tr>
	<tr>
		<td>define</td>
		<td>Activity 및 Actor를 정의(재정의). 이 권한이 부여되지 않은 상태에서 
			Statement를 저장하는 경우 id는 저장되며, LRS는 감사(audit) 
			목적으로 원본 Statement를 저장할 수 있지만(MAY), 
			어떤 Actor나 Activity의 정규 표현(canonical representation)도 
			갱신하지 않아야 한다(SHOULD NOT).
		</td>
	</tr>
	<tr>
		<td>profile</td>
		<td>Profile Document 데이터 읽기/쓰기. 현재 토큰과 연관된 Activity 및 Actor로 
			제한되며, 이 관계를 판단할 수 있는 범위 내에서 
			적용된다.
		</td>
	</tr>
	<tr><td>all/read</td><td>제한 없는 읽기 접근</td></tr>
	<tr><td>all</td><td>제한 없는 접근</td></tr>
</table>

<a name="oauth-resources"></a>
###### OAuth 리소스 (OAuth Resources)
<table>
	<tr>
		<th>이름 (Name)</th>
		<th>엔드포인트 (Endpoint)</th>
		<th>예시 (Example)</th>
	</tr>
	<tr>
		<td>Temporary Credential Request</td>
		<td>OAuth/initiate</td>
		<td>http://example.com/xAPI/OAuth/initiate</td>
	</tr>
	<tr>
		<td>Resource Owner Authorization</td>
		<td>OAuth/authorize</td>
		<td>http://example.com/xAPI/OAuth/authorize</td>
	</tr>
	<tr>
		<td>Token Request</td>
		<td>OAuth/token</td>
		<td>http://example.com/xAPI/OAuth/token </td>
	</tr>
</table>

<a name="example-1"></a>
##### 예시 (Example)
범위 목록은 요청되는 권한의 집합을 결정한다. 예를 들어 강사는 애플리케이션(Client)에 
"statements/read"를 부여할 수 있지만, LRS는 여전히 해당 도구가 접근할 수 있는 Statement를 강사가 자신의 자격 증명으로 
LRS에 직접 질의할 때 읽을 수 있는 Statement(예: 자신의 학생과 관련된 Statement)로 제한한다.

<a name="requirements-17"></a>
##### 요구사항 (Requirements)

* LRS는 [OAuth 2.0](http://tools.ietf.org/html/rfc6749#section-3.3)에 정의된 scope 파라미터를 반드시 수락해야 한다(MUST).
* 범위가 지정되지 않은 경우, LRS는 요청된 범위를 "statements/write" 및 "statements/read/mine"으로 
반드시 간주해야 한다(MUST).
* LRS는 최소한 "all" 범위를 반드시 지원해야 한다(MUST).
* LRS는 다른 범위를 지원할 수 있다(MAY).
* Client는 요청이 승인될 가능성을 높이기 위해 필요한 최소한의 범위만 
요청해야 한다(SHOULD).
* "consumer_name" 및 "scope" 파라미터는 OAuth 1.0의 일부가 아니므로, 사용하는 경우 OAuth 헤더가 아니라 
쿼리 문자열 또는 폼 파라미터로 반드시 전달해야 한다(MUST).  


<a name="50-security"></a>
## 5.0 보안 (Security) 

인증 이외의 보안(OAuth 인가 범위의 해석 포함)은 이 문서의 현재 범위를 벗어나며, 
개별 LRS 제공자의 구현 세부 사항으로 남겨둔다. 구현자는 업계 모범 사례를 따를 것을 권장한다. 
예를 들어 미국 백악관 CIO실의 [The HTTPS-Only Standard](https://https.cio.gov)가 있다.

이 스펙을 구현하는 과정에서 보안 문제가 발생할 수 있으며, 구현자는 보안을 위해 적합성 요구사항을 
위반하기로 선택할 수도 있다. 이러한 경우 구현자는 자신의 구현 결정이 보안과 상호운용성에 
미치는 영향을 모두 고려할 것을 권장한다. 어떤 경우에든 LRS는 여전히 적합성 테스트를 통과할 수 있도록 
구성 가능해야 한다. 

다른 보안 문제는 이 스펙의 범위를 벗어나지만, xAPI 커뮤니티는 보안 모범 사례를 정립하는 데 
계속 힘쓰고 있다. 이 작업은 [xAPIsec](https://github.com/xapisec/xapisec)에서 시작되었다. 
적극적인 참여를 권장한다.

<a name="appendices"></a>
## 부록 (Appendices)


<a name="appendix-a-converting-statements-to-100"></a>
### 부록 A: Statement를 1.0.0으로 변환하기 (Appendix A: Converting Statements to 1.0.0)

<a name="rationale-4"></a>
###### 근거 (Rationale)
이 문서는 1.0.0 스펙이므로 구현자는 이전 버전의 스펙을 고려할 필요가 없다. 
그러나 이전 버전들도 상당히 널리 채택되었다. 이 데이터 변환은 이전 버전을 사용해 추적된 데이터를 
보존하고, 새로운 구현자가 일관된 방식으로 그 데이터를 사용할 수 있도록 하기 위해 규정된다.

<a name="details-16"></a>
###### 세부 사항 (Details)

<a name="conversion-of-statements-created-based-on-version-09"></a>
###### 버전 0.9 기반으로 생성된 Statement의 변환 (Conversion of Statements created based on version 0.9)

0.9에서 생성된 Statement를 변환하는 1.0.0 Client 또는 기타 시스템은 아래 단계를 반드시 따라야 한다(MUST):

* Statement가 무효화되었거나, 0.9 스펙에 포함되지 않은 Verb, Activity 유형 또는 속성을 사용하는 경우
 변환하지 않는다.
* "verb" 앞에 `http://adlnet.gov/expapi/verbs/`를 붙인다.
* 완전한 절대 IRI가 아닌 모든 Activity id 앞에 `tag:adlnet.gov,2013:expapi:0.9:activities:`를 붙인다.
* 완전한 절대 IRI가 아닌 모든 extension 키 앞에 `tag:adlnet.gov,2013:expapi:0.9:extensions:`를 붙인다.
* Activity 유형 앞에 `http://adlnet.gov/expapi/activities/`를 붙인다.
* 각 Agent(Actor)에 대해:
    * "mbox, mbox_sha1sum, openid, account" 순서로 역함수 식별자(Inverse Functional Identifier)를
    찾는다. 처음 발견된 값이 채워진 역함수 식별자만 유지하고 나머지는 버린다.
    * 위의 역함수 식별자에 대해, 배열의 첫 번째 요소를 해당 역함수 식별자 속성의 값으로
    사용하고 나머지 요소는 버린다.
    * "name" 속성이 있으면 "name" 배열의 첫 번째 요소로 설정하고
    나머지 요소는 버린다.
    * 나머지 속성은 모두 제거한다.
* Statement에 "voided" 속성이 있으면 제거한다. voided 속성의 값이 `true`이면
  해당 Statement는 변환해서는 안 된다(MUST NOT)는 점을 기억한다.
* `version": "1.0.0`을 추가한다.
* 이전에 authority가 설정되지 않았다면, authority를 account로 식별되는 Agent로 설정한다. 
이 account의 homePage는 변환을 수행하는 시스템에 해당하는 홈 페이지로, accountName은 `unknown`으로 설정한다.
* Context의 "statement" 속성이 설정되어 있었다면 Statement에서 제거한다.
* "stored" 속성을 포함한 그 밖의 모든 속성은 수정 없이 보존한다. "stored" 
속성은 Statement가 LRS로 전송되면 여전히 갱신된다.

<a name="conversion-of-statements-created-based-on-version-095"></a>
###### 버전 0.95 기반으로 생성된 Statement의 변환 (Conversion of Statements created based on version 0.95)

0.95에서 생성된 Statement를 변환하는 1.0.0 Client 또는 기타 시스템은 아래 단계를 반드시 따라야 한다(MUST):

* Statement가 무효화되었다면 변환하지 않는다.
* Statement에 "voided" 속성이 있으면 제거한다. "voided" 속성의 값이 `true`이면 
해당 Statement는 변환해서는 안 된다(MUST NOT)는 점을 기억한다.
* `version": "1.0.0`을 추가한다.
* 이전에 authority가 설정되지 않았다면, authority를 account로 식별되는 Agent로 설정한다. 
이 account의 homePage는 변환을 수행하는 시스템에 해당하는 홈 페이지로, accountName은 `unknown`으로 설정한다.
* Context의 Statement 속성이 StatementRef가 아닌 다른 것으로 설정되어 있었다면 
Statement에서 제거한다.
* "stored" 속성을 포함한 그 밖의 모든 속성은 수정 없이 보존한다. "stored" 
속성은 Statement가 LRS로 전송되면 여전히 갱신된다.


<a name="example-2"></a>
###### 예시 (Example)


0.9 Statement:
```
{
    "id": "d1eec41f-1e93-4ed6-acbf-5c4bd0c24269",
    "actor": {
        "objectType": "Person",
        "name": [
            "Joe Schmoe",
            "Joseph Schmoseph"
        ],
        "mbox": [
            "mailto:joe@example.com"
        ],
        "openid": [
            "http://openid.com/joe-schmoe"
        ]
    },
    "verb": "completed",
    "inProgress": false,
    "object": {
        "objectType": "Activity",
        "id": "http://www.example.com/activities/001",
        "definition": {
            "name": {
                "en-US": "Example Activity"
            },
            "type": "course"
        }
    },
    "result": {
        "completion": true
    },
    "context": {
        "instructor": {
            "objectType": "Person",
            "lastName": [
                "Dad"
            ],
            "firstName": [
                "Joe's"
            ],
            "mbox": [
                "mailto:joesdad@example.com"
            ]
        },
        "contextActivities": {
            "parent": {
                "objectType": "Activity",
                "id": "non-absolute-activity-id",
                "definition": {
                    "name": {
                        "en-US": "Another Activity"
                    }
                }
            }
        }
    },
    "timestamp": "2012-06-01T19:09:13.245Z",
    "stored": "2012-06-29T15:41:39.165Z"
}
```

1.0.0으로 변환된 결과:
```
{
    "version": "1.0.0",
    "id": "d1eec41f-1e93-4ed6-acbf-5c4bd0c24269",
    "actor": {
        "objectType": "Agent",
        "name": "Joe Schmoe",
        "mbox": "mailto:joe@example.com"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/completed",
        "display": {
            "en-US": "completed"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.example.com/activities/001",
        "definition": {
            "name": {
                "en-US": "Example Activity"
            },
            "type": "http://adlnet.gov/expapi/activities/course"
        }
    },
    "result": {
        "completion": true
    },
    "context": {
        "instructor": {
            "objectType": "Agent",
            "mbox": "mailto:joesdad@example.com"
        },
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "tag:adlnet.gov,2013:expapi:0.9:activities:non-absolute-activity-id",
                    "definition": {
                        "name": {
                            "en-US": "Another Activity"
                        }
                    }
                }
            ]
        }
    },
    "timestamp": "2012-06-01T19:09:13.245Z",
    "stored": "2012-06-29T15:41:39.165Z",
    "authority": {
        "objectType": "Agent",
        "account": {
            "homePage": "http://www.example.com",
            "name": "unknown"
        }
    }
}
```



<a name="appendix-b-table-of-all-resources"></a>
### 부록 B: 전체 리소스 표 (Appendix B: Table of All Resources)

<a name="required-resources"></a>
### 필수 리소스 (Required Resources)
<table>
	<tr>
		<th>각 엔드포인트 앞에 LRS의 기본 리소스 엔드포인트가 붙는다</th>
		<th>기능</th>
	</tr>
	<tr>
		<td>statements</td>
		<td>Statement 저장/조회</td>
	</tr>
	<tr>
		<td>agents</td>
		<td>Agent Object 저장/조회</td>
	</tr>
	<tr>
		<td>agents/profile</td>
		<td>Agent Profile Resource</td>
	</tr>
	<tr>
		<td>activities</td>
		<td>Activity Object 저장/조회</td>
	</tr>
	<tr>
		<td>activities/profile</td>
		<td>Activity Profile Resource</td>
	</tr>
	<tr>
		<td>activities/state</td>
		<td>State Resource</td>
	</tr>
	<tr>
		<td>about</td>
		<td>LRS 정보</td>
	</tr>
</table>

<a name="oauth-resources-1"></a>
### OAuth 리소스 (OAuth Resources)
<table>
	<tr>
		<th>각 엔드포인트 앞에 LRS의 기본 리소스 엔드포인트가 붙는다</th>
		<th>기능</th>
	</tr>
	<tr>
		<td>OAuth/initiate</td>
		<td>Temporary Credential Request</td>
	</tr>
	<tr>
		<td>OAuth/authorize</td>
		<td>Resource Owner Authorization</td>
	</tr>
	<tr>
		<td>OAuth/token</td>
		<td>Token Request</td>
	</tr>
</table>


<a name="appendix-c-cross-domain-request-example"></a>
### 부록 C: 크로스 도메인 요청 예시 (Appendix C: Cross Domain Request Example)

[대체 요청 구문(Alternate Request Syntax)](#13-alternate-request-syntax)은 브라우저 또는 쿼리 문자열 길이 제한 때문에 일반 구문을 
사용할 수 없을 때 사용하는 대체 구문을 설명한다. 이 부록은 이 형식을 따르는 Statements Resource에 대한 
PUT 요청의 예시를 제공한다. 

일반 구문을 사용한 요청:

```
URL: http://example.com/xAPI/statements
Method: PUT

Query String Parameters:
    statementId=c70c2b85-c294-464f-baca-cebd4fb9b348

Request Headers:
    Accept:*/*
    Accept-Encoding:gzip, deflate, sdch
    Accept-Language:en-US,en;q=0.8
    Authorization: Basic VGVzdFVzZXI6cGFzc3dvcmQ=
    Content-Type: application/json
    X-Experience-API-Version: 1.0.3
    Content-Length: 351

Content:
{"id":"c70c2b85-c294-464f-baca-cebd4fb9b348","timestamp":"2014-12-29T12:09:37.468Z","actor":{"objectType":"Agent","mbox":"mailto:example@example.com","name":"Test User"},"verb":{"id":"http://adlnet.gov/expapi/verbs/experienced","display":{"en-US":"experienced"}},"object":{"id":"http://example.com/xAPI/activities/myactivity","objectType":"Activity"}}

```

대체 구문을 사용한 요청:

```
URL: http://example.com/xAPI/statements
Method: POST

Query String Parameters:
    method=PUT

Request Headers:
    Accept:*/*
    Accept-Encoding:gzip, deflate, sdch
    Accept-Language:en-US,en;q=0.8
    Content-Type: application/x-www-form-urlencoded
    Content-Length: 745

Content (with added line breaks and not URL encoded for readability):
    statementId=c70c2b85-c294-464f-baca-cebd4fb9b348
    &Authorization=Basic VGVzdFVzZXI6cGFzc3dvcmQ=
    &X-Experience-API-Version=1.0.3
    &Content-Type=application/json
    &Content-Length=351
    &content={"id":"c70c2b85-c294-464f-baca-cebd4fb9b348","timestamp":"2014-12-29T12:09:37.468Z","actor":{"objectType":"Agent","mbox":"mailto:example@example.com","name":"Test User"},"verb":{"id":"http://adlnet.gov/expapi/verbs/experienced","display":{"en-US":"experienced"}},"object":{"id":"http://example.com/xAPI/activities/myactivity","objectType":"Activity"}}
```
