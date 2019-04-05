---
title: public (c + + 특성) (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: a12ab0905064a72057dffac03340b667f07b3ae5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022829"
---
# <a name="public-c-attributes"></a>public(C++ 특성)

.Idl 파일 내에서 참조 하지 않는 경우에 typedef 형식 라이브러리로 이동 됩니다 확인 합니다.

## <a name="syntax"></a>구문

```cpp
[public]
```

## <a name="remarks"></a>설명

**공개** c + + 특성에 동일한 기능을 합니다 [공용](/windows/desktop/Midl/public) MIDL 특성입니다.

## <a name="example"></a>예제

다음 코드에서는 사용 하 여 **공용** 특성:

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**형식 정의**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)