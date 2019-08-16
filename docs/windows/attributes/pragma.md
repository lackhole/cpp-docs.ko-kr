---
title: pragma (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: 5c3ee0d3f99bd27ca41d68b11c11522e92c8d40a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514269"
---
# <a name="pragma"></a>pragma

따옴표를 사용 하지 않고 지정 된 문자열을 생성 된 .idl 파일로 내보냅니다.

## <a name="syntax"></a>구문

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>매개 변수

*pragma_statement*<br/>
생성 된 .idl 파일로 이동 하려는 pragma입니다.

## <a name="remarks"></a>설명

**Pragma** C++ 특성은 [pragma](/windows/win32/Midl/pragma) MIDL 특성과 동일한 기능을 포함 합니다.

## <a name="example"></a>예제

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)