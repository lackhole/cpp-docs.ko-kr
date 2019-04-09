---
title: 기본 (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: c6448b00fef50a7654816a2c39af2943db12d314
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024584"
---
# <a name="default-c"></a>default(C++)

coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.

## <a name="syntax"></a>구문

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>매개 변수

*interface1*<br/>
기본 인터페이스는 **default** 특성으로 정의된 클래스에 따라 개체를 만드는 스크립팅 환경에 사용할 수 있습니다.

지정된 기본 인터페이스가 없는 경우 처음에 발생하는 비 소스 인터페이스가 기본값으로 사용됩니다.

*interface2*<br/>
(선택 사항) 기본 소스 인터페이스입니다. 이 인터페이스는 [source](source-cpp.md) 특성을 사용하여 지정해야 합니다.

지정된 기본 소스 인터페이스가 없는 경우 첫 번째 소스 인터페이스가 기본값으로 사용됩니다.

## <a name="remarks"></a>설명

**default** C++ 특성에는 [default](/windows/desktop/Midl/default) MIDL 특성과 동일한 기능이 있습니다. **default** 특성을 [case](case-cpp.md) 특성과 함께 사용할 수도 있습니다.

## <a name="example"></a>예제

다음 코드에서는 어떻게 **기본** coclass 정의에서 지정 하는 데 사용 됩니다 `ICustomDispatch` 기본 프로그래밍 인터페이스로:

```cpp
// cpp_attr_ref_default.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};

[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]
__interface IDual {
   HRESULT Dual([in] long l, [out, retval] long *pLong);
};

[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]
__interface ICustomDispatch : public IDispatch {
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);
};

[   coclass, default(ICustomDispatch), source(IDual), uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")
]
class CClass : public ICustom, public IDual, public ICustomDispatch {
   HRESULT Custom(long l, long *pLong) { return(S_OK); }
   HRESULT Dual(long l, long *pLong) { return(S_OK); }
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }
};

int main() {
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch
   CClass *pClass = new CClass;

   long llong;

   pClass->custom(1, &llong);
   pClass->dual(1, &llong);
   pClass->dispinterface(1, &llong);
   pClass->dispatch(1, &llong);

   delete pClass;
#endif
   return(0);
}
```

[source](source-cpp.md) 특성에는 **default**사용 방법에 대한 예제도 있습니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**클래스**하십시오 **구조체**, 데이터 멤버|
|**반복 가능**|아니요|
|**필수 특성**|**coclass** (적용할 때 **클래스** 하거나 **구조체**)|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[coclass](coclass.md)