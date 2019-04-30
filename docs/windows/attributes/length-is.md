---
title: length_is (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.length_is
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
ms.openlocfilehash: 1de168606b57c801bc3dc1fb9aee76eb6f3d54c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409306"
---
# <a name="lengthis"></a>length_is

전송할 배열 요소의 수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ length_is("expression") ]
```

### <a name="parameters"></a>매개 변수

*expression*<br/>
하나 이상의 C 언어 식입니다. 빈 인수 슬롯 허용 됩니다.

## <a name="remarks"></a>설명

**length_is** C++ 특성에 동일한 기능을 합니다 [length_is](/windows/desktop/Midl/length-is) MIDL 특성입니다.

## <a name="example"></a>예제

참조 [first_is](first-is.md) 배열 섹션을 지정 하는 방법의 예입니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|필드에 **구조체** 하거나 **union**인터페이스 매개 변수, 인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[last_is](last-is.md)<br/>
[size_is](size-is.md)