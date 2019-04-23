---
title: custom(C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 227e67696e679452a9c6c0e18c04e3d918f7a93f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029436"
---
# <a name="custom-c"></a>custom(C++)

형식 라이브러리의 개체에 대 한 메타 데이터를 정의합니다.

## <a name="syntax"></a>구문

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>매개 변수

*uuid*<br/>
고유한 ID입니다.

*값*<br/>
Variant로 입력할 수 있는 값입니다.

## <a name="remarks"></a>설명

합니다 **사용자 지정** C++ 특성 정보를 형식 라이브러리에 배치 하면 됩니다. 형식 라이브러리에서 사용자 지정 값을 읽는 도구를 해야 합니다.

합니다 **사용자 지정** 특성이 동일한 기능을 합니다 [사용자 지정](/windows/desktop/Midl/custom) MIDL 특성입니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|비-COM **인터페이스**, **클래스**, **열거형**s `idl_module` 인터페이스 매개 변수, 메서드, 인터페이스 멤버 **typedef**s, **union**개이면 **구조체**s|
|**반복 가능**|예|
|**필수 특성**|**coclass** (클래스에 사용) 하는 경우|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[매개 변수 특성](parameter-attributes.md)<br/>
[메서드 특성](method-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)