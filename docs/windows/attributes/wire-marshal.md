---
title: wire_marshal (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.wire_marshal
helpviewer_keywords:
- wire_marshal attribute
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
ms.openlocfilehash: d1d18336a20644338a50ab66c7fcb06959e5760a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407018"
---
# <a name="wiremarshal"></a>wire_marshal

응용 프로그램별 데이터 형식 대신 전송을 위해 사용 될 데이터 형식을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[wire_marshal]
```

## <a name="remarks"></a>설명

**wire_marshal** C++ 특성에 동일한 기능을 합니다 [wire_marshal](/windows/desktop/Midl/wire-marshal) MIDL 특성입니다.

## <a name="example"></a>예제

다음 코드는 사용 방법을 보여 줍니다 **wire_marshal**:

```cpp
// cpp_attr_ref_wire_marshal.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export, public] typedef unsigned long _FOUR_BYTE_DATA;

[export] typedef struct _TWO_X_TWO_BYTE_DATA {
   unsigned short low;
   unsigned short high;
} TWO_X_TWO_BYTE_DATA ;

[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**typedef**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)