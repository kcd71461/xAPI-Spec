# xAPI-Spec (한국어)

[English](../README.md) | **한국어**

> 이 문서는 xAPI(Experience API) 1.0.3 스펙의 **비공식 한국어 번역**입니다.
> 번역 과정에서 생긴 오류가 있을 수 있으며, 원문과 번역의 내용이 다를 경우 **[영어 원문](../README.md)이 우선**합니다.
> 번역에 사용한 용어와 표기 원칙은 [용어집(GLOSSARY.md)](./GLOSSARY.md)에 정리해 두었습니다.

이 GitHub 저장소에는 xAPI 스펙이 담겨 있습니다. xAPI는 학습 기술 간 상호운용성(interoperability)을 위한
스펙으로, 학습자의 활동과 경험에 관한 정보를 여러 기술(시스템) 사이에서 주고받는 방식을 정의합니다.
스펙은 세 개의 문서로 나뉘어 있습니다.

*   1부: [Experience API 소개 (About the Experience API)](./xAPI-About.md#part-one-about-the-experience-api)
*   2부: [Experience API 데이터 (Experience API Data)](./xAPI-Data.md#part-two-experience-api-data)
*   3부: [데이터 처리, 검증 및 보안 (Data Processing, Validation, and Security)](./xAPI-Communication.md#part-three-data-processing-validation-and-security)

## 처음 읽는다면

xAPI를 처음 접하는 개발자라면 다음 순서로 읽는 것을 추천합니다.

1. **1부 4.0 정의(Definitions)와 5.0 xAPI 구성 요소(xAPI Components)**: Statement, Activity, LRS 같은 핵심 개념을 먼저 익힙니다.
2. **2부 2.0 Statements**: xAPI의 중심 데이터인 Statement의 구조(Actor, Verb, Object, Result, Context 등)를 이해합니다.
3. **3부 1.0 요청(Requests)과 2.0 리소스(Resources)**: LRS와 HTTP로 통신하는 방법(엔드포인트, 헤더, 인증 등)을 확인합니다.

## 스펙 버전

이 저장소의 스펙은 이전 버전인 [1.0.3](https://github.com/adlnet/xAPI-Spec/)입니다.

현재 스펙 버전은 xAPI [2.0](https://opensource.ieee.org/xapi/xapi-base-standard-documentation)입니다.

다음 버전의 스펙은 아직 계획되지 않았습니다.

## 스펙이 불명확할 때

스펙을 구현하다가 불명확하거나 도움이 되지 않는 부분을 발견하면,
[원본 저장소에 이슈를 등록](https://github.com/adlnet/xAPI-Spec/issues)하여 스펙 개선에 기여할 수 있습니다.
이슈를 등록할 때는 다음 내용을 최대한 자세히 적어 주세요.

* 읽고 있는 스펙의 부분(들)
* 해당 부분에 대해 이해한 내용
* xAPI를 적용하려는 제품과 기능, 그리고 달성하려는 사용 사례
* 스펙이 어떻게 개선되면 좋을지에 대한 제안 (구체적인 문구를 제안해도 좋습니다)

이슈를 등록하거나 댓글을 달려면 [GitHub 계정](https://github.com/signup/free)이 필요합니다.

이슈를 등록하기 전이나 후에 [스펙 Google Group](https://groups.google.com/a/adlnet.gov/forum/#!forum/xapi-spec)과
[주간 스펙 회의](https://attendee.gotowebinar.com/register/5526804432322315009)에서 논의할 수도 있습니다.

> 번역 자체의 오류나 어색한 표현은 원본 저장소가 아니라 이 포크 저장소의 이슈로 알려 주세요.

## 기여 방법

스펙에 기여하려면 [GitHub 계정](https://github.com/signup/free)이 필요합니다.

xAPI 스펙 워킹 그룹(xAPI Spec Working Group)은 매월 첫째·셋째 주 수요일 오후 2시 30분(미국 동부 시간)에
GoToMeeting에서 모입니다. [https://global.gotomeeting.com/join/686232837](https://global.gotomeeting.com/join/686232837)에서 참여할 수 있습니다.

xAPI 적합성 테스트 워킹 그룹(xAPI Conformance Testing Working Group)은 매월 둘째 주 수요일 오후 2시 30분(미국 동부 시간)에
GoToMeeting에서 모입니다. [https://global.gotomeeting.com/join/686232837](https://global.gotomeeting.com/join/686232837)에서 참여할 수 있습니다.

자세한 안내와 기여자 목록은 [기여 가이드라인(영문)](../CONTRIBUTING.md)을 참고하세요.
