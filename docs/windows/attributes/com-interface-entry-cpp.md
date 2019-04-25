---
title: com_interface_entry (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.com_interface_entry
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
ms.openlocfilehash: 65d174679f851613e064568b071cfcbdad8f0f06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148265"
---
# <a name="cominterfaceentry-c"></a>com_interface_entry(C++)

대상 클래스의 COM 맵에 인터페이스 항목을 추가 합니다.

## <a name="syntax"></a>구문

```cpp
[ com_interface_entry(
  com_interface_entry) ]
```

### <a name="parameters"></a>매개 변수

*com_interface_entry*<br/>
항목의 실제 텍스트를 포함 하는 문자열입니다. 가능한 값 목록을 참조 하세요 [COM_INTERFACE_ENTRY 매크로](../../atl/reference/com-interface-entry-macros.md)합니다.

## <a name="remarks"></a>설명

합니다 **com_interface_entry** C++ 특성 대상 개체의 COM 인터페이스 맵을 문자열 통화할된 내용을 삽입 합니다. 특성을 적용 하면 한 번 대상 개체에 항목을 기존 인터페이스 맵 시작 부분에 삽입 됩니다. 특성을 적용 하면 반복 해 서 동일한 대상 개체에 항목을 받은 순서 대로 인터페이스 맵 시작 부분에 삽입 됩니다.

이 특성을 사용하려면 [coclass](coclass.md), [progid](progid.md)또는 [vi_progid](vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 있으면 `progid` 적용 됩니다 `vi_progid` 및 `coclass` 도 적용 됩니다.

때문에 첫 번째 사용 **com_interface_entry** 인터페이스 맵 시작 부분에 삽입 될 새 인터페이스를 사용 하면 다음 COM_INTERFACE_ENTRY 유형 중 하나 여야 합니다.

- COM_INTERFACE_ENTRY

- COM_INTERFACE_ENTRY_IID

- COM_INTERFACE_ENTRY2

- COM_INTERFACE_ENTRY2_IID

다른 용도 **com_interface_entry** 특성에는 지원 되는 모든 COM_INTERFACE_ENTRY 형식을 사용할 수 있습니다.

ATL 인터페이스 맵의 첫 번째 항목 id로 사용 하기 때문에이 제한 사항은 반드시 `IUnknown`따라서 올바른 인터페이스를 입력 해야 합니다. 예를 들어, 다음 코드 샘플 올바르지 인터페이스 맵 첫 번째 항목이 실제 COM 인터페이스를 지정 하지 않으므로 합니다.

```cpp
[ coclass, com_interface_entry =
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"
]
   class CMyClass
   {
   };
```

## <a name="example"></a>예제

다음 코드는 두 항목의 기존 COM 인터페이스 맵에 추가 `CMyBaseClass`합니다. 첫 번째는 표준 인터페이스가 고 두 번째 숨깁니다는 `IDebugTest` 인터페이스입니다.

```cpp
// cpp_attr_ref_com_interface_entry.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name ="ldld")];

[ object,
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]
__interface IDebugTest{};

[ object,
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]
__interface IMyClass{};

[ coclass,
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")
]

class CMyClass: public IMyClass, public IDebugTest
{
};
```

에 대 한 결과 COM 개체 맵의 `CMyBaseClass` 는 다음과 같습니다.

```cpp
BEGIN_COM_MAP(CMyClass)
    COM_INTERFACE_ENTRY (IMyClass)
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)
    COM_INTERFACE_ENTRY(IMyClass)
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)
    COM_INTERFACE_ENTRY(IDebugTest)
    COM_INTERFACE_ENTRY(IProvideClassInfo)
END_COM_MAP()
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|예|
|**필수 특성**|다음 중 하나 이상의: `coclass`, `progid`, 또는 `vi_progid`합니다.|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[COM 특성](com-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)