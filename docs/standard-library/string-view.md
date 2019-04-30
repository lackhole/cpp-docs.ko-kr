---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 8952416cf37fc4d8d281d6ced9b8264495ec3799
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346981"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

클래스 템플릿을 정의 `basic_string_view` 및 관련 형식 및 연산자입니다. (컴파일러 옵션을 사용 해야 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md) 이상.)

## <a name="syntax"></a>구문

```cpp
#include <string_view>
```

## <a name="remarks"></a>설명

템플릿 특수화 string_view 패밀리의 위치 0에 있는 시퀀스의 첫 번째 요소를 사용 하 여 문자 데이터 문자열 같은 개체의 읽기 전용 예외 로부터 안전한, 소유 되지 않은 핸들을 전달 하는 효율적인 방법을 제공 합니다. 함수 매개 변수 형식의 `string_view` (에 대 한 typedef `basic_string_view<char>`)와 같은 인수를 허용할 수 있습니다 `std::string`, **char\***, 또는 기타 유사한 문자열 클래스는 좁은 문자 암시적 변환할 `string_view` 정의 됩니다. 마찬가지로, 매개 변수 `wstring_view`, `u16string_view` 또는 `u32string_view` 암시적 변환을 정의 되는 모든 문자열 형식을 받아들일 수 있습니다. 자세한 내용은 [basic_string_view 클래스](../standard-library/basic-string-view-class.md)합니다.

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|클래스 템플릿의 특수화 `basic_string_view` 형식의 요소를 사용 하 여 **char**합니다.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|클래스 템플릿의 특수화 `basic_string_view` 형식의 요소를 사용 하 여 **wchar_t**합니다.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|클래스 템플릿의 특수화 `basic_string_view` 형식의 요소가 있는 `char16_t`합니다.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|클래스 템플릿의 특수화 `basic_string_view` 형식의 요소가 있는 `char32_t`합니다.|

### <a name="operators"></a>연산자

합니다 \<string_view > 연산자를 비교할 수 `string_view` 개체 모두로 변환할 수 있는 개체를 문자열 형식입니다.

|연산자|설명|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.|
|[연산자==](../standard-library/string-view-operators.md#op_eq_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.|
|[operator<](../standard-library/string-view-operators.md#op_lt)|연산자의 좌 변에 있는 개체가 보다 작은 경우 테스트 오른쪽에 있는 개체입니다.|
|[operator<=](../standard-library/string-view-operators.md#op_lt_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작거나 같은지 테스트합니다.|
|[operator<\<](../standard-library/string-view-operators.md#op_lt_lt)|삽입 하는 템플릿 함수는 `string_view` 출력 스트림으로.|
|[operator>](../standard-library/string-view-operators.md#op_gt)|연산자의 좌 변에 있는 개체가 우변에 있는 개체 보다 큰 인지 테스트 합니다.|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체보다 크거나 같은지 테스트합니다.|

### <a name="literals"></a>리터럴

|연산자|설명|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|생성을 `string_view`, `wstring_view`를 `u16string_view`, 또는 `u32string_view` 추가 하는 문자열 리터럴의 형식에 따라 합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[basic_string_view 클래스](../standard-library/basic-string-view-class.md)|임의의 문자 형식 개체의 시퀀스에 읽기 전용 보기를 제공 하는 클래스 템플릿.|
|[hash](string-view-hash.md)|string_view에 대 한 해시 값을 생성 하는 함수 개체입니다.|

## <a name="requirements"></a>요구 사항

- **헤더:** \<string_view >

- **네임스페이스:** std

- **컴파일러 옵션:** /std: c + + 17 (이상)

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
