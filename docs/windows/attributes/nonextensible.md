---
title: nonextensible (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonextensible
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
ms.openlocfilehash: ed396b3d55e16cf195949c713ab574812b796a1a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032078"
---
# <a name="nonextensible"></a>nonextensible

지정 된 `IDispatch` 구현 속성만 포함 하 고 메서드 인터페이스 설명에 나열 된 런타임 시 추가 멤버를 사용 하 여 확장할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
[nonextensible]
```

## <a name="remarks"></a>설명

합니다 **nonextensible** c + + 특성에 동일한 기능을 합니다 [nonextensible](/windows/desktop/Midl/nonextensible) MIDL 특성입니다.

이용 **nonextensible** 도 필요 합니다 [oleautomation](oleautomation.md) 특성입니다.

## <a name="example"></a>예제

다음 코드와의 용도 중 하나는 **nonextensible** 특성:

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface(인터페이스)**|
|**반복 가능**|아니요|
|**필수 특성**|`dual` 및 `oleautomation`, 또는 `dispinterface`|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)