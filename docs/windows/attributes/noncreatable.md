---
title: noncreatable (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.noncreatable
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
ms.openlocfilehash: a10d93650c0ae564019a09b34c3a604d12327998
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305322"
---
# <a name="noncreatable"></a>noncreatable

자체적으로 인스턴스화할 수 없는 개체를 정의 합니다.

## <a name="syntax"></a>구문

```cpp
[noncreatable]
```

## <a name="remarks"></a>설명

**noncreatable** C++ 특성에 동일한 기능을 합니다 [noncreatable](/windows/desktop/Midl/noncreatable) MIDL 특성과 생성 된 자동으로 전달 됩니다. 컴파일러에서 IDL 파일입니다.

ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하면 특성의 동작을 변경 합니다. 위 동작 외에도 특성도 삽입 합니다 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) 매크로입니다. ATL에 나타냅니다이 매크로 개체를 외부에서 만들 수 없습니다.

## <a name="example"></a>예제

```cpp
// cpp_attr_ref_noncreatable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("11111111-1111-1111-1111-111111111111")]
__interface A
{
};

[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]
class CMyClass : public A
{
   HRESULT xx();
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|아니요|
|**필수 특성**|**coclass**|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[클래스 특성](class-attributes.md)
