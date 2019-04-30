---
title: async_uuid (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.async_uuid
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
ms.openlocfilehash: 4c2bca9165d8b23f8cfa4f0f5523c882fd2f52bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364976"
---
# <a name="asyncuuid"></a>async_uuid

MIDL 컴파일러에 지시 합니다 COM 인터페이스의 동기 및 비동기 버전을 정의 하는 UUID를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[async_uuid (uuid)]
```

### <a name="parameters"></a>매개 변수

*uuid*<br/>
인터페이스의 버전을 식별 하는 UUID입니다.

## <a name="remarks"></a>설명

**async_uuid** C++ 특성에 동일한 기능을 합니다 [async_uuid](/windows/desktop/Midl/async-uuid) MIDL 특성입니다.

## <a name="example"></a>예제

```cpp
// cpp_attr_ref_async_uuid.cpp
// compile with: /LD
#include <Windows.h>
[module(name="Test")];
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|`interface`|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|**dual**, **dispinterface**|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[인터페이스 특성](interface-attributes.md)