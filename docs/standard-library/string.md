---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: fda00cd5a8f8768688c8e10f25a0d1f2370a256f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459197"
---
# <a name="ltstringgt"></a>&lt;string&gt;

컨테이너 클래스 템플릿 `basic_string` 및 다양한 지원 템플릿을 정의합니다.

`basic_string`에 대한 자세한 내용은 [basic_string 클래스](../standard-library/basic-string-class.md)를 참조하세요.

## <a name="syntax"></a>구문

```cpp
#include <string>
```

## <a name="remarks"></a>설명

C++ 언어와 C++ 표준 라이브러리는 두 가지 문자열 형식을 지원합니다.

- Null로 종료되는 문자 배열은 보통 C 문자열이라고 합니다.

- 모든 문자 형식 템플릿 인수를 `basic_string`처리 하는 형식의 템플릿 클래스 개체입니다.

### <a name="typedefs"></a>형식 정의

|형식 이름|Description|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Char 형식의 요소가로 포함 된 템플릿 클래스 `basic_string` 의 특수화를 설명 하는 형식입니다.  `string`|
|[wstring](../standard-library/string-typedefs.md#wstring)|Wchar_t 형식의 요소가로 포함 된 템플릿 클래스 `basic_string` 의 특수화를 설명 하는 형식입니다.  `wstring`|
|[u16string](../standard-library/string-typedefs.md#u16string)|`basic_string` 형식 요소를 기준으로 템플릿 클래스 `char16_t`의 특수화를 설명하는 형식입니다.|
|[u32string](../standard-library/string-typedefs.md#u32string)|`basic_string` 형식 요소를 기준으로 템플릿 클래스 `char32_t`의 특수화를 설명하는 형식입니다.|

### <a name="operators"></a>연산자

|연산자|Description|
|-|-|
|[operator+](../standard-library/string-operators.md#op_add)|두 문자열 개체를 연결합니다.|
|[operator!=](../standard-library/string-operators.md#op_neq)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체와 같지 않은지 테스트합니다.|
|[연산자==](../standard-library/string-operators.md#op_eq_eq)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체와 같은지 테스트합니다.|
|[operator<](../standard-library/string-operators.md#op_lt)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 작은지 테스트합니다.|
|[operator<=](../standard-library/string-operators.md#op_lt_eq)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 작거나 같은지 테스트합니다.|
|[operator<\<](../standard-library/string-operators.md#op_lt_lt)|문자열을 출력 스트림에 삽입하는 템플릿 함수입니다.|
|[operator>](../standard-library/string-operators.md#op_gt)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 큰지 테스트합니다.|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 크거나 같은지 테스트합니다.|
|[operator>>](../standard-library/string-operators.md#op_gt_gt)|입력 스트림에서 문자열을 추출하는 템플릿 함수입니다.|

### <a name="specialized-template-functions"></a>특별 템플릿 함수

|||
|-|-|
|[hash]()||
|[swap](../standard-library/string-functions.md#swap)|두 문자열의 문자 배열을 교환합니다.|
|[stod](../standard-library/string-functions.md#stod)|문자 시퀀스를 **double**로 변환 합니다.|
|[stof](../standard-library/string-functions.md#stof)|문자 시퀀스를 **float**로 변환 합니다.|
|[stoi](../standard-library/string-functions.md#stoi)|문자 시퀀스를 정수로 변환합니다.|
|[stold](../standard-library/string-functions.md#stold)|문자 시퀀스를 **long double**로 변환 합니다.|
|[stoll](../standard-library/string-functions.md#stoll)|문자 시퀀스를 **long long**으로 변환 합니다.|
|[stoul](../standard-library/string-functions.md#stoul)|문자 시퀀스를 **부호 없는 long**으로 변환 합니다.|
|[stoull](../standard-library/string-functions.md#stoull)|문자 시퀀스를 **부호 없는 long long**으로 변환 합니다.|
|[to_string](../standard-library/string-functions.md#to_string)|값을 `string`로 변환합니다.|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|값을 와이드 `string`으로 변환합니다.|

### <a name="functions"></a>함수

|기능|Description|
|-|-|
|[getline 템플릿](../standard-library/string-functions.md#getline)|입력 스트림에서 문자열을 한 줄씩 추출합니다.|

### <a name="classes"></a>클래스

|클래스|Description|
|-|-|
|[basic_string 클래스](../standard-library/basic-string-class.md)|임의의 문자 형식 개체 시퀀스를 저장할 수 있는 개체를 설명하는 템플릿 클래스입니다.|
|[char_traits 구조체](../standard-library/char-traits-struct.md)|CharType 형식 문자와 관련된 특성을 설명하는 템플릿 클래스입니다.|

### <a name="specializations"></a>특수화

|||
|-|-|
|[char_traits\<char> 구조체](../standard-library/char-traits-char-struct.md)|`char` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType>의 특수화인 구조체입니다.|
|[char_traits<wchar_t> 구조체](../standard-library/char-traits-wchar-t-struct.md)|`wchar_t` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType>의 특수화인 구조체입니다.|
|[char_traits<char16_t> 구조체](../standard-library/char-traits-char16-t-struct.md)|`char16_t` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType>의 특수화인 구조체입니다.|
|[char_traits<char32_t> 구조체](../standard-library/char-traits-char32-t-struct.md)|`char32_t` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType>의 특수화인 구조체입니다.|

## <a name="requirements"></a>요구 사항

- **헤더:** \<string>

- **네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
