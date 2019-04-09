---
title: transmit_as (c + + COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.transmit_as
helpviewer_keywords:
- transmit_as attribute
ms.assetid: 53d0b8ab-5b06-423e-83eb-3d01a10424b2
ms.openlocfilehash: e432d1a8f39cbc5e12f192ed7b07c29421bc403e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032104"
---
# <a name="transmitas"></a>transmit_as

전송된 형식을 사용 하 여 클라이언트 및 서버 응용 프로그램을 조작 하는 제공 된 형식을 연결 하는 컴파일러에 지시 합니다.

## <a name="syntax"></a>구문

```cpp
[ transmit_as(type) ]
```

### <a name="parameters"></a>매개 변수

*type*<br/>
클라이언트와 서버 간에 전송 되는 데이터 형식을 지정 합니다.

## <a name="remarks"></a>설명

합니다 **transmit_as** c + + 특성에 동일한 기능을 합니다 [transmit_as](/windows/desktop/Midl/transmit-as) MIDL 특성입니다.

## <a name="example"></a>예제

다음 코드에서는 사용 하 여 **transmit_as** 특성:

```cpp
// cpp_attr_ref_transmit_as.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export] typedef struct _TREE_NODE_TYPE {
unsigned short data;
struct _TREE_NODE_TYPE * left;
struct _TREE_NODE_TYPE * right;
} TREE_NODE_TYPE;

[export] struct PACKED_NODE {
   unsigned short data;   // same as normal node
   int index;   // array index of parent
};

// A left node recursive built array of
// the nodes in the tree.  Can be unpacked with
// that knowledge
[export] typedef struct _TREE_XMIT_TYPE {
   int count;
   [size_is(count)] PACKED_NODE node[];
} TREE_XMIT_TYPE;

[transmit_as(TREE_XMIT_TYPE)] typedef TREE_NODE_TYPE * TREE_TYPE;
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
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[내보내기](export.md)