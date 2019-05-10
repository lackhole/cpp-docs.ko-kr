---
title: 컴파일러 오류 C2100 ~ C2199
ms.date: 04/21/2019
f1_keywords:
- C2119
- C2123
- C2125
- C2126
- C2127
- C2136
- C2176
- C2187
- C2189
helpviewer_keywords:
- C2119
- C2123
- C2125
- C2126
- C2127
- C2131
- C2136
- C2176
- C2187
- C2189
ms.assetid: 1ccab076-0954-4386-b959-d3112a6793ae
ms.openlocfilehash: 3a5a5368700eb1c4c585826021fefc21c25ecedf
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857407"
---
# <a name="compiler-errors-c2100-through-c2199"></a>컴파일러 오류 C2100 ~ C2199

설명서의이 섹션의 문서는 컴파일러에서 생성 되는 오류 메시지의 하위 집합을 설명 합니다.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>오류 메시지

|Error|메시지|
|-----------|-------------|
|[컴파일러 오류 C2100](compiler-error-c2100.md)|간접 참조가 잘못 되었습니다|
|[컴파일러 오류 C2101](compiler-error-c2101.md)|상수에 '&'가 있습니다.|
|[컴파일러 오류 C2102](compiler-error-c2102.md)|'&'에 l-value가 있어야 합니다.|
|[컴파일러 오류 C2103](compiler-error-c2103.md)|레지스터 변수에 '&'가 있습니다.|
|[컴파일러 오류 C2104](compiler-error-c2104.md)|비트 필드의 '&'가 무시됩니다.|
|[컴파일러 오류 C2105](compiler-error-c2105.md)|'*연산자*' l-value가 필요|
|[컴파일러 오류 C2106](compiler-error-c2106.md)|'*연산자*': 왼쪽된 피연산자 l 값 이어야 합니다.|
|[컴파일러 오류 C2107](compiler-error-c2107.md)|인덱스가 잘못 되어 간접 참조 허용 되지 않습니다|
|[컴파일러 오류 C2108](compiler-error-c2108.md)|첨자가 정수 계열 형식이 아닙니다.|
|[컴파일러 오류 C2109](compiler-error-c2109.md)|아래 첨자 배열 또는 포인터 형식이 필요|
|[컴파일러 오류 C2110](compiler-error-c2110.md)|'+': 두 포인터를 더할 수 없습니다.|
|[컴파일러 오류 C2111](compiler-error-c2111.md)|'+': 포인터 더하기에는 정수 계열 피연산자가 있어야 합니다.|
|[컴파일러 오류 C2112](compiler-error-c2112.md)|'-': 포인터 빼기에는 정수 계열 또는 포인터 피연산자가 있어야 합니다.|
|[컴파일러 오류 C2113](compiler-error-c2113.md)|'-': 다른 포인터에서 포인터 에서만 뺄 수 있습니다|
|[컴파일러 오류 C2114](compiler-error-c2114.md)|'*연산자*': 왼쪽이 포인터 이므로 오른쪽에 정수 값 요구|
|[컴파일러 오류 C2115](compiler-error-c2115.md)|'*연산자*': 호환 되지 않는 형식|
|[컴파일러 오류 C2116](compiler-error-c2116.md)|함수 매개 변수 목록이 다릅니다.|
|[컴파일러 오류 C2117](compiler-error-c2117.md)|'*식별자*': 배열 범위 오버플로입니다|
|[컴파일러 오류 C2118](compiler-error-c2118.md)|첨자가 음수.|
|컴파일러 오류 C2119|'*식별자*': 형식에 대 한 '*형식*' 비어 있는 이니셜라이저에서 추론할 수 없습니다|
|[컴파일러 오류 C2120](compiler-error-c2120.md)|' void' 형식도 사용할 수 없습니다.|
|[컴파일러 오류 C2121](compiler-error-c2121.md)|'#': 잘못 된 문자: 매크로 확장의 결과 수|
|[컴파일러 오류 C2122](compiler-error-c2122.md)|'*식별자*': 프로토타입 매개 변수가 이름 목록이 잘못 되었습니다.|
|컴파일러 오류 C2123|'*식별자*': 별칭 템플릿을 특수화할 수 없습니다. 명시적으로 또는 부분적으로|
|[컴파일러 오류 C2124](compiler-error-c2124.md)|0으로 나누기 또는 나머지 연산을 수행했습니다.|
|컴파일러 오류 C2125|'constexpr'와 호환 되지 않습니다. '*토큰*'|
|컴파일러 오류 C2126|'*식별자*' 'constexpr' 지정자를 사용 하 여 선언할 수 없습니다.|
|컴파일러 오류 C2127|'*식별자*': 비상수 식으로 'constexpr' 엔터티 초기화가 잘못 되었습니다|
|[컴파일러 오류 C2128](compiler-error-c2128.md)|'*함수*': alloc_text/same_seg는 C 링크가 있는 함수에만 적용|
|[컴파일러 오류 C2129](compiler-error-c2129.md)|정적 함수 '*식별자*' 선언 되었지만 정의 되지 않았습니다|
|[컴파일러 오류 C2130](compiler-error-c2130.md)|#line 예상에 파일 이름을 포함 하는 문자열 '*토큰*'|
|[컴파일러 오류 C2131](compiler-error-c2131.md)|식이 상수로 계산 되지 않았습니다.|
|[컴파일러 오류 C2132](compiler-error-c2132.md)|구문 오류: 예기치 않은 식별자|
|[컴파일러 오류 C2133](compiler-error-c2133.md)|'*식별자*': 알 수 없는 크기|
|[컴파일러 오류 C2134](compiler-error-c2134.md)|'*함수*': 상수 식에서는 호출 되지 않습니다|
|[컴파일러 오류 C2135](compiler-error-c2135.md)|'*연산자*': 잘못 된 비트 필드 연산이|
|컴파일러 오류 C2136|허용 되지 않습니다 API 계약 작성|
|[컴파일러 오류 C2137](compiler-error-c2137.md)|문자 상수가 비어 있습니다.|
|[컴파일러 오류 C2138](compiler-error-c2138.md)|멤버 없이 열거형을 정의 하는 잘못 되었습니다.|
|[컴파일러 오류 C2139](compiler-error-c2139.md)|'*클래스*': 정의 되지 않은 클래스는 컴파일러 내장 형식 특성에 대 한 인수로 허용 되지 않습니다는 '*특성 (trait)*'|
|[컴파일러 오류 C2140](compiler-error-c2140.md)|'*형식*': 제네릭 형식 매개 변수에 종속 된 형식은 컴파일러 내장 형식 특성에 대 한 인수로 사용할 수 없습니다 '*특성 (trait)*'|
|[컴파일러 오류 C2141](compiler-error-c2141.md)|배열 크기 오버플로|
|[컴파일러 오류 C2142](compiler-error-c2142.md)|함수 선언이 서로 다릅니다. 그 중 하나에 지정 하는 가변 매개 변수|
|[컴파일러 오류 C2143](compiler-error-c2143.md)|구문 오류: 누락 된 '*token1*'before'*token2*'|
|[컴파일러 오류 C2144](compiler-error-c2144.md)|구문 오류: '*형식*'앞에 있어야'*token2*'|
|[컴파일러 오류 C2145](compiler-error-c2145.md)|구문 오류: 누락 된 '*토큰*' 식별자 앞|
|[컴파일러 오류 C2146](compiler-error-c2146.md)|구문 오류: 누락 된 '*토큰*'identifier' before*식별자*'|
|[컴파일러 오류 C2147](compiler-error-c2147.md)|구문 오류: '*토큰*'는 새로운 키워드|
|[컴파일러 오류 C2148](compiler-error-c2148.md)|배열의 총 크기 0 x를 초과할 수 없습니다*값* 바이트|
|[컴파일러 오류 C2149](compiler-error-c2149.md)|'*식별자*': 명명 된 비트 필드의 너비가 0 일 수 없습니다.|
|[컴파일러 오류 C2150](compiler-error-c2150.md)|'*식별자*': 비트 필드 형식은 'int', 'signed int' 또는 'unsigned int' 있어야 합니다.|
|[컴파일러 오류 C2151](compiler-error-c2151.md)|둘 이상의 언어 특성|
|[컴파일러 오류 C2152](compiler-error-c2152.md)|'*식별자*': 특성이 서로 다른 함수에 대 한 포인터|
|[컴파일러 오류 C2153](compiler-error-c2153.md)|정수 리터럴은 진수가 적어도 하나 있어야 합니다.|
|[컴파일러 오류 C2154](compiler-error-c2154.md)|'*형식*': 컴파일러 내장 형식 특성에 대 한 인수로 열거형 형식만 허용 됩니다 '*특성 (trait)*'|
|[컴파일러 오류 C2155](compiler-error-c2155.md)|'?': 잘못 된 왼쪽 피연산자를 산술 또는 포인터 형식|
|[컴파일러 오류 C2156](compiler-error-c2156.md)|pragma는 함수 외부에 있어야 합니다.|
|[컴파일러 오류 C2157](compiler-error-c2157.md)|'*식별자*': pragma 목록에서 사용 하기 전에 선언 되어야 합니다|
|[컴파일러 오류 C2158](compiler-error-c2158.md)|'*형식*': #pragma make_public 지시문은 현재 기본 템플릿이 아닌 형식에 대 한 지원|
|[컴파일러 오류 C2159](compiler-error-c2159.md)|스토리지 클래스를 두 개 이상 지정했습니다.|
|[컴파일러 오류 C2160](compiler-error-c2160.md)|매크로 정의 시작에 '##'이 올 수 없습니다.|
|[컴파일러 오류 C2161](compiler-error-c2161.md)|매크로 정의 끝에 '##'이 올 수 없습니다.|
|[컴파일러 오류 C2162](compiler-error-c2162.md)|예상된 매크로 정식 매개 변수|
|[컴파일러 오류 C2163](compiler-error-c2163.md)|'*함수*': 내장 함수로 사용할 수 없음|
|[컴파일러 오류 C2164](compiler-error-c2164.md)|'*함수*': 내장 함수를 선언 하지|
|[컴파일러 오류 C2165](compiler-error-c2165.md)|'*한정자*': 데이터에 대 한 포인터를 수정할 수 없습니다.|
|[컴파일러 오류 C2166](compiler-error-c2166.md)|l-value가 const 개체를 지정합니다.|
|[컴파일러 오류 C2167](compiler-error-c2167.md)|'*함수*': 내장 함수에 대 한 실제 매개 변수가 너무 많습니다|
|[컴파일러 오류 C2168](compiler-error-c2168.md)|'*함수*': 내장 함수에 대 한 실제 매개 변수가 너무 적습니다|
|[컴파일러 오류 C2169](compiler-error-c2169.md)|'*함수*': 내장 함수를 정의할 수 없습니다|
|[컴파일러 오류 C2170](compiler-error-c2170.md)|'*식별자*': 함수로 선언 되지 내장 함수 일 수 없습니다|
|[컴파일러 오류 C2171](compiler-error-c2171.md)|'*연산자*': 잘못 된 형식의 피연산자에 '*형식*'|
|[컴파일러 오류 C2172](compiler-error-c2172.md)|'*함수*': 실제 매개 변수가 포인터가 아닙니다: 매개 변수 *수*|
|[컴파일러 오류 C2173](compiler-error-c2173.md)|'*함수*': 실제 매개 변수가 포인터가 아닙니다: 매개 변수 *번호*, 매개 변수 목록 *수*|
|[컴파일러 오류 C2174](compiler-error-c2174.md)|'*함수*': 실제 매개 변수는 'void' 형식의: 매개 변수 *번호*에 매개 변수 목록 *수*|
|[컴파일러 오류 C2175](compiler-error-c2175.md)|'*로캘*': 잘못 된 로캘|
|컴파일러 오류 C2176|return 문은 생성자와 관련 된 함수-시도-블록의 처리기에 나타날 수 없습니다.|
|[컴파일러 오류 C2177](compiler-error-c2177.md)|상수가 너무 큽니다.|
|[컴파일러 오류 C2178](compiler-error-c2178.md)|'*식별자*'로 선언할 수 없습니다'*지정자*' 지정자|
|[컴파일러 오류 C2179](compiler-error-c2179.md)|'*형식*': 특성 인수에서 형식 매개 변수를 사용할 수 없습니다|
|[컴파일러 오류 C2180](compiler-error-c2180.md)|제어 식의 형식이 '*형식*'|
|[컴파일러 오류 C2181](compiler-error-c2181.md)|if와 짝을 이루지 않는 잘못된 else문입니다.|
|[컴파일러 오류 C2182](compiler-error-c2182.md)|'*식별자*': 'void' 형식 잘못 사용|
|[컴파일러 오류 C2183](compiler-error-c2183.md)|구문 오류: 변환 단위가 비어 있습니다.|
|[컴파일러 오류 C2184](compiler-error-c2184.md)|'*형식*': __except 식에 대 한 형식이 잘못 되었습니다.|
|[컴파일러 오류 C2185](compiler-error-c2185.md)|'*식별자*': 기반 할당이 잘못 되었습니다|
|[컴파일러 오류 C2186](compiler-error-c2186.md)|'*연산자*': 'void' 형식의 피연산자가 잘못 되었습니다|
|컴파일러 오류 C2187|구문 오류: '*토큰*' 여기 예기치 않은|
|[컴파일러 오류 C2188](compiler-error-c2188.md)|'*번호*': 와이드 문자에 비해 너무 커서|
|컴파일러 오류 C2189|'alignas' 특성은 비트 필드, 함수 매개 변수, 예외 선언에 적용할 수 없습니다 또는 'register' 저장소 클래스 사용 하 여 선언 된 변수|
|[컴파일러 오류 C2190](compiler-error-c2190.md)|첫 번째 매개 변수 목록이 둘째 보다 깁니다.|
|[컴파일러 오류 C2191](compiler-error-c2191.md)|두 번째 매개 변수 목록이 첫째 보다 깁니다.|
|[컴파일러 오류 C2192](compiler-error-c2192.md)|매개 변수 '*번호*' 선언이 다릅니다.|
|[컴파일러 오류 C2193](compiler-error-c2193.md)|'*식별자*': 세그먼트에 이미|
|[컴파일러 오류 C2194](compiler-error-c2194.md)|'*식별자*': 텍스트 세그먼트|
|[컴파일러 오류 C2195](compiler-error-c2195.md)|'*식별자*': 데이터 세그먼트|
|[컴파일러 오류 C2196](compiler-error-c2196.md)|case 값 '*값*' 이미 사용|
|[컴파일러 오류 C2197](compiler-error-c2197.md)|'*함수*': 호출에 대 한 인수가 너무 많습니다.|
|[컴파일러 오류 C2198](compiler-error-c2198.md)|'*함수*': 호출에 대 한 인수가 너무 적습니다.|
|[컴파일러 오류 C2199](compiler-error-c2199.md)|구문 오류: 찾을 수 '*식별자* (' 전역 범위에서 (계획 된 선언?)|

## <a name="see-also"></a>참고자료

[C /C++ 컴파일러 및 빌드 도구 오류 및 경고](../compiler-errors-1/c-cpp-build-errors.md) \
[컴파일러 오류 C2000-C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
