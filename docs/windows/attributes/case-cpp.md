---
title: 경우 (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: b3058f2fe6f35e1b11d4790780cb0fcdcaada706
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038202"
---
# <a name="case-c"></a>case(C++)

사용 된 [switch_type](switch-type.md) 특성을 **union**합니다.

## <a name="syntax"></a>구문

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>매개 변수

*값*<br/>
가능한 처리를 제공 하려는 값을 입력 합니다. 유형의 **값** 다음 유형 중 하나일 수 있습니다.

- `int`

- `char`

- `boolean`

- `enum`

또는 이러한 형식의 식별자입니다.

## <a name="remarks"></a>설명

**대/소문자** C++ 특성이 동일한 기능을 합니다 **사례** MIDL 특성. 이 특성에만 사용 합니다 [switch_type](switch-type.md) 특성입니다.

## <a name="example"></a>예제

다음 코드에서는 사용 하는 **사례** 특성:

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|멤버는 **클래스** 또는 **구조체**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[클래스 특성](class-attributes.md)