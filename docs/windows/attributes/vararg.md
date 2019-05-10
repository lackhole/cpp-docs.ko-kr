---
title: vararg (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vararg
helpviewer_keywords:
- vararg attribute
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
ms.openlocfilehash: a433522b78424c48c4afe754f7b8337e3952dc8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407213"
---
# <a name="vararg"></a>vararg

함수는 가변 개수의 인수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[vararg]
```

## <a name="remarks"></a>설명

**vararg** C++ 특성에 동일한 기능을 합니다 [vararg](/windows/desktop/Midl/vararg) MIDL 특성입니다.

## <a name="example"></a>예제

다음 코드는 사용 방법을 보여 줍니다 **vararg**:

```cpp
// cpp_attr_ref_vararg.cpp
// compile with: /LD
#include "unknwn.h"
#include "oaidl.h"
[module(name="MyLibrary")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface X : public IUnknown
{
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|인터페이스 메서드|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[메서드 특성](method-attributes.md)