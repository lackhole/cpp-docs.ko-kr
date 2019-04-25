---
title: coclass (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: e1f99a2780ab4f451533a3e797e473f60680c6ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148291"
---
# <a name="coclass"></a>coclass

COM 인터페이스를 구현할 수 있는 COM 개체를 만듭니다.

## <a name="syntax"></a>구문

```cpp
[coclass]
```

## <a name="remarks"></a>설명

합니다 **coclass** C++ 특성 생성된 된.idl 파일에서 coclass 구문을 배치 합니다.

Coclass를 정의할 때는 지정할 수도 있습니다는 [uuid](uuid-cpp-attributes.md)를 [버전](version-cpp.md)를 [스레딩](threading-cpp.md)를 [vi_progid](vi-progid.md), 및 [progid ](progid.md) 특성입니다. 그 중 하나를 지정 하지 않은 경우 생성 됩니다.

두 개의 헤더 파일 사용 하 여 클래스를 포함 하는 경우는 **coclass** 특성 및 GUID를 지정 하지 않는 컴파일러에서는 두 클래스 모두에 대 한 동일한 GUID를 사용 하 고 MIDL 오류가 발생 하는 합니다.  따라서 사용 해야 합니다 `uuid` 사용 하는 경우 특성 **coclass**합니다.

**ATL 프로젝트**

이 특성은 클래스 또는 구조체 정의 ATL 프로젝트에서 앞에 오는 경우 해당:

- 코드 또는 개체에 대 한 자동 등록을 지원 하기 위해 데이터를 삽입 합니다.

- 코드 또는 개체에 대 한 COM 클래스 팩터리를 지원 하기 위해 데이터를 삽입 합니다.

- 코드 또는 구현 하는 데이터를 삽입 `IUnknown` COM creatable 개체를 개체를 확인 합니다.

특히 다음 기본 클래스에는 대상 개체에 추가 됩니다.

- [CComCoClass 클래스](../../atl/reference/ccomcoclass-class.md) 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 제공 합니다.

- [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md) 에서 지정한 스레딩 모델 클래스를 기반으로 템플릿을는 [스레딩](threading-cpp.md) 특성입니다. 경우는 `threading` 특성을 지정 하지 않으면 스레딩 모델 기본값인 아파트 합니다.

- [IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md) 를 추가 하면 합니다 [noncreatable](noncreatable.md) 대상 개체에 대 한 특성을 지정 하지 않으면.

마지막으로, 포함된 IDL를 사용 하 여 정의 되지 않은 모든 이중 인터페이스는 해당 바뀝니다 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md) 클래스입니다. 이중 인터페이스 포함된 IDL에 정의 된 경우에 기본 목록에 특정 인터페이스를 수정 되지 않습니다.

합니다 **coclass** 특성 또한 다음 함수를 사용할 수 있게의 경우 삽입 된 코드를 통하거나 `GetObjectCLSID`, 기본 클래스의 정적 메서드로 `CComCoClass`:

- `UpdateRegistry` 대상 클래스의 클래스 팩터리를 등록합니다.

- `GetObjectCLSID`에 관련 된 등록을 사용할 수도 있습니다 대상 클래스의 CLSID를 가져오려고 합니다.

- `GetObjectFriendlyName` 기본적으로 형식의 문자열을 반환 합니다 "\<*대상 클래스 이름*> `Object`"입니다. 이 함수가 이미 있으면 추가 되지 않습니다. 이 함수를 자동으로 생성 하는 것 보다 친숙 한 이름을 반환 하는 대상 클래스를 추가 합니다.

- `GetProgID`를 등록, 관련 된 지정 된 문자열을 반환 합니다는 [progid](progid.md) 특성입니다.

- `GetVersionIndependentProgID` 동일한 기능이 `GetProgID`를 사용 하 여 지정 된 문자열을 반환 하지만 [vi_progid](vi-progid.md)합니다.

대상 클래스를 COM 맵 관련이 다음 변경 내용이:

- 대상 클래스에서 파생 되는 모든 인터페이스에 대 한 항목 및 지정 된 모든 항목을 사용 하 여 COM 맵에 추가 되는 [COM 인터페이스 진입점](../../mfc/com-interface-entry-points.md) 특성 또는에 필요한 것을 [집계](aggregates.md) 특성입니다.

- [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) COM 맵에 매크로가 삽입 됩니다.

클래스에 대 한.idl 파일에서 생성 된 coclass의 이름 클래스와 동일한 이름을 갖습니다.  예를 들어와 coclass의 클래스 ID에 액세스 하려면 다음 샘플에서는 참조 `CMyClass`, MIDL에서 생성 된 헤더 파일을 통해 클라이언트에서 사용 하 여 `CLSID_CMyClass`입니다.

## <a name="example"></a>예제

다음 코드에서는 사용 하 여 **coclass** 특성:

```cpp
// cpp_attr_ref_coclass1.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I {
   HRESULT func();
};

[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]
class CMyClass : public I {};
```

다음 예제에서 삽입 된 코드에 표시 되는 함수의 기본 구현을 재정의 하는 방법을 설명 합니다 **coclass** 특성입니다. 삽입된 코드 보기에 대한 자세한 정보는 [/Fx](../../build/reference/fx-merge-injected-code.md) 를 참조하세요. 모든 기본 클래스 또는 인터페이스 클래스를 사용 하는 삽입된 된 코드에 나타납니다. 또한 클래스는 삽입된 된 코드에 기본적으로 포함 하 고 명시적으로 해당 클래스를 기준으로 프로그램 coclass에 대 한를 지정 하는 경우 특성 공급자 코드에서 지정 된 형식을 사용 합니다.

```cpp
// cpp_attr_ref_coclass2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface bb {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class CMyClass : public bb {
public:
   // by adding the definition of UpdateRegistry to your code, // the function will not be included in the injected code
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {
      // you can add to the default implementation
      CRegistryVirtualMachine rvm;
      HRESULT hr;
      if (FAILED(hr = rvm.AddStandardReplacements()))
         return hr;
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),       GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);
   }
};
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[COM 특성](com-attributes.md)<br/>
[클래스 특성](class-attributes.md)<br/>
[Typedef, Enum, Union 및 Struct 특성](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)