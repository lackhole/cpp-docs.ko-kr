---
title: pointer_default (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: 37bd2b16fb7a7c1c186f59897898e08cc73fffae
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022668"
---
# <a name="pointerdefault"></a>pointer_default

매개 변수 목록에 표시 되는 최상위 포인터를 제외 하 고 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>매개 변수

*값*<br/>
포인터 형식을 설명 하는 값: **ptr**하십시오 **ref**, 또는 **고유**.

## <a name="remarks"></a>설명

합니다 **pointer_default** c + + 특성에 동일한 기능을 합니다 [pointer_default](/windows/desktop/Midl/pointer-default) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [defaultvalue](defaultvalue.md) 의 샘플 사용에 대 한 **pointer_default**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface(인터페이스)**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)