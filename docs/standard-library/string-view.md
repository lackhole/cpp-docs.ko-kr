---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 47924c3d6bd1a2f45cdbac648f4f563c57ce8939
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459112"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

클래스 템플릿과 `basic_string_view` 관련 형식 및 연산자를 정의 합니다. 컴파일러 옵션 [std: c + + 17](../build/reference/std-specify-language-standard-version.md) 이상이 필요 합니다.

## <a name="syntax"></a>구문

```cpp
#include <string_view>
```

## <a name="remarks"></a>설명

템플릿 특수화의 string_view 패밀리는 위치 0에 있는 시퀀스의 첫 번째 요소를 사용 하 여 문자열 형식 개체의 문자 데이터에 대 한 읽기 전용, 예외 안전, 소유 하지 않은 핸들을 전달 하는 효율적인 방법을 제공 합니다. 형식의 `string_view` 함수 매개 변수 (에 대 한 `basic_string_view<char>`typedef)는, **char\*** 또는에 `std::string` `string_view`대한암시적변환으로사용할수있는좁은문자의기타문자열유사클래스와같은인수를사용할수있습니다.이 정의 되었습니다. 마찬가지로, `wstring_view` `u16string_view` 또는 의매개변수는암시적변환이정의된모든문자열형식을허용할수있습니다.`u32string_view` 자세한 내용은 [Basic_string_view 클래스](../standard-library/basic-string-view-class.md)를 참조 하세요.

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|**Char**형식의 요소가 있는 클래스 템플릿의 `basic_string_view` 특수화입니다.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|**Wchar_t**형식의 요소가 있는 클래스 템플릿의 `basic_string_view` 특수화입니다.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|`basic_string_view` 형식의`char16_t`요소를 포함 하는 클래스 템플릿의 특수화입니다.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|`basic_string_view` 형식의`char32_t`요소를 포함 하는 클래스 템플릿의 특수화입니다.|

### <a name="operators"></a>연산자

String_view \<> 연산자는 개체를 `string_view` 변환할 수 있는 문자열 형식의 개체와 비교할 수 있습니다.

|연산자|설명|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.|
|[연산자==](../standard-library/string-view-operators.md#op_eq_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.|
|[operator<](../standard-library/string-view-operators.md#op_lt)|연산자의 좌 변에 있는 개체가 우변에 있는 개체 보다 작음을 테스트 합니다.|
|[operator<=](../standard-library/string-view-operators.md#op_lt_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작거나 같은지 테스트합니다.|
|[operator<\<](../standard-library/string-view-operators.md#op_lt_lt)|를 `string_view` 출력 스트림에 삽입 하는 템플릿 함수입니다.|
|[operator>](../standard-library/string-view-operators.md#op_gt)|연산자의 좌 변에 있는 개체가 우변에 있는 개체 보다 큰지 테스트 합니다.|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|연산자의 좌변에 있는 개체가 우변에 있는 개체보다 크거나 같은지 테스트합니다.|

### <a name="literals"></a>리터럴

|연산자|Description|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|추가 되는 문자열 `u16string_view`리터럴의 형식 `u32string_view` 에 따라 `wstring_view`,,또는를 생성 합니다. `string_view`|

### <a name="classes"></a>클래스

|클래스|Description|
|-|-|
|[basic_string_view 클래스](../standard-library/basic-string-view-class.md)|임의의 문자 형식 개체 시퀀스에 읽기 전용 뷰를 제공 하는 클래스 템플릿입니다.|
|[hash](string-view-hash.md)|String_view에 대 한 해시 값을 생성 하는 함수 개체입니다.|

## <a name="requirements"></a>요구 사항

- **헤더:** \<string_view >

- **네임스페이스:** std

- **컴파일러 옵션:** std: c + + 17 이상

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
