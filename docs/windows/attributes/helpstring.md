---
title: helpstring (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 623b2c7fb4ce7c3e5de87d21f012d008720fdee2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022207"
---
# <a name="helpstring"></a>helpstring

적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.

## <a name="syntax"></a>구문

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>매개 변수

*string*<br/>
텍스트 도움말 문자열입니다.

## <a name="remarks"></a>설명

합니다 **helpstring** c + + 특성에 동일한 기능을 합니다 [helpstring](/windows/desktop/Midl/helpstring) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [defaultvalue](defaultvalue.md) 사용 하는 방법의 예제 **helpstring**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**인터페이스**하십시오 **typedef**를 **클래스**, 메서드, 속성|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)