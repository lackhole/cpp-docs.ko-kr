---
title: odl (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.odl
helpviewer_keywords:
- odl attribute
ms.assetid: 75dcb314-b50f-4a63-9180-507ac1bc78f3
ms.openlocfilehash: 90f9f1df23542138b2fac0dcfe0e122f1993d805
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407642"
---
# <a name="odl"></a>odl

개체 설명 언어 (ODL) 인터페이스는 인터페이스를 식별합니다. MIDL 컴파일러 않아도 합니다 **odl** ; 특성 이전.odl 파일을 사용 하 여 호환성을 위해서만 인식 됩니다.

## <a name="syntax"></a>구문

```cpp
[odl]
```

## <a name="remarks"></a>설명

**odl** C++ 특성에 동일한 기능을 합니다 [odl](/windows/desktop/Midl/odl) MIDL 특성입니다.

## <a name="example"></a>예제

```cpp
// cpp_attr_ref_odl.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLIb")];

[odl, oleautomation, dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyInterface
{
   HRESULT x();
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
class cmyClass : public IMyInterface
{
public:
   HRESULT x(){}
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**interface**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)