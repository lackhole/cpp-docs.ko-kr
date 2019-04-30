---
title: 레지스트리 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
ms.openlocfilehash: 8e05d6a47ea67138e8d1d456077526dd3178cc44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274644"
---
# <a name="registry-macros"></a>레지스트리 매크로

이러한 매크로 유용한 형식 라이브러리 및 레지스트리 기능을 정의합니다.

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL.에 대 한 종속성을 방지 하려면 개체에 개체에 대 한 등록 코드를 원하는 지 나타냅니다. DLL입니다.|
|[DECLARE_LIBID](#declare_libid)|ATL 가져오는 방법을 제공 합니다 *libid* 형식 라이브러리의 합니다.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|기본 ATL 등록을 방지합니다.|
|[DECLARE_REGISTRY](#declare_registry)|입력 또는 시스템 레지스트리에 기본 개체의 항목을 제거 합니다.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|자동으로 등록 하는 데 필요한 정보를 지정 합니다 *appid*합니다.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|명명 된 리소스를 찾아 그 레지스트리 스크립트를 실행 합니다.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|ID 번호로 식별 되는 리소스를 찾아 그 레지스트리 스크립트를 실행 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY

원하는 ATL.에 대 한 종속성을 방지 하려면 개체에 개체에 대 한 등록 코드를 나타내는 기호 DLL입니다.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>설명

ATL_STATIC_REGISTRY를 정의할 때 다음 코드를 사용 해야 합니다.

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

##  <a name="declare_libid"></a>  DECLARE_LIBID

ATL 가져오는 방법을 제공 합니다 *libid* 형식 라이브러리의 합니다.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>매개 변수

*libid*<br/>
형식 라이브러리의 GUID입니다.

### <a name="remarks"></a>설명

DECLARE_LIBID 사용을 `CAtlModuleT`-클래스를 파생 합니다.

### <a name="example"></a>예제

ATL 프로젝트 마법사에서 생성 되지 않은 특성을 사용이 매크로 사용 하 여 예제를 사용 합니다.

##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY

이 매크로 표시 되는 클래스에 대 한 모든 기본 ATL 등록 하지 않으려는 경우 DECLARE_NO_REGISTRY를 사용 합니다.

```
DECLARE_NO_REGISTRY()
```

##  <a name="declare_registry"></a>  DECLARE_REGISTRY

표준 클래스 등록 시스템 레지스트리에 입력 하거나 시스템 레지스트리에서 제거 합니다.

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>매개 변수

*class*<br/>
[in] 이전 버전과 호환성을 위해 포함 되어 있습니다.

*pid*<br/>
[in] 버전별 프로그램 식별자가는 LPCTSTR 합니다.

*vpid*<br/>
[in] 버전에 관계 없이 프로그램 식별자가는 LPCTSTR 합니다.

*nid*<br/>
[in] UINT 프로그램 설명으로 사용 하도록 레지스트리를의 리소스 문자열의 인덱스입니다.

*flags*<br/>
[in] 레지스트리에서 프로그램의 스레딩 모델을 포함 하는 DWORD. 다음 값 중 하나 여야 합니다. THREADFLAGS_APARTMENT, THREADFLAGS_BOTH, 또는 AUTPRXFLAG 합니다.

### <a name="remarks"></a>설명

표준 등록 CLSID, 프로그램 ID, 버전 독립 프로그램 ID, 설명 문자열 및 스레드 모델 구성 됩니다.

개체를 만들거나 ATL 클래스 추가 마법사를 사용 하 여 제어 하는 경우 마법사를 자동으로 레지스트리 스크립트 기반 지원을 구현 하 고 추가 합니다 [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) 파일에는 매크로입니다. 스크립트 기반 레지스트리 지원 하지 않으려면 DECLARE_REGISTRY를 사용 하 여이 매크로 대체 해야 합니다. DECLARE_REGISTRY만 레지스트리에 위에서 설명한 5 개의 기본 키를 삽입 합니다. 수동으로 레지스트리로 다른 키를 삽입 하는 코드를 작성 해야 합니다.

##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID

자동으로 등록 하는 데 필요한 정보를 지정 합니다 *appid*합니다.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>매개 변수

*resid*<br/>
에 대 한 정보를 포함 하는.rgs 파일의 리소스 id를 *appid*합니다.

*appid*<br/>
GUID

### <a name="remarks"></a>설명

DECLARE_REGISTRY_APPID_RESOURCEID 사용을 `CAtlModuleT`-클래스를 파생 합니다.

### <a name="example"></a>예제

클래스 추가 코드 마법사를 사용 하 여 ATL 프로젝트에 추가 하는 클래스는이 매크로 사용 하는 예제를 갖게 됩니다.

##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE

레지스트리 파일을 포함 하는 명명 된 리소스를 가져오고 개체를 시스템 레지스트리에 입력 하거나 시스템 레지스트리에서 제거 스크립트를 실행 합니다.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 리소스의 식별자는 문자열입니다.

### <a name="remarks"></a>설명

개체를 만들거나 ATL 프로젝트 마법사를 사용 하 여 제어 하는 경우 마법사는 자동으로 레지스트리 스크립트 기반 지원을 구현 하 고 추가 합니다 [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) DECLARE_REGISTRY_ 비슷한 매크로 리소스 파일입니다.

ATL 레지스트리 구성 요소 (등록자)에 최적화 된 레지스트리 액세스를 사용 하 여 정적으로 연결할 수 있습니다. 등록자 코드를 정적으로 연결할 stdafx.h 파일에 다음 줄을 추가 합니다.

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

런타임 시 대체 값으로 대체 하는 ATL 원한다 면 DECLARE_REGISTRY_RESOURCE 또는 DECLARE_REGISTRY_RESOURCEID 매크로 지정 하지 마십시오. 대신, 배열을 만든 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자 값을 사용 하 여 쌍을 이루는 구조, 각 항목 변수 자리 표시자를 포함 하는 위치입니다. 그런 다음 호출 [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) 하거나 [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), 배열을 전달 합니다. 모든에서 대체 값이 추가 `_ATL_REGMAP_ENTRIES` 기관의 대체 맵 구조입니다.

대체 가능 매개 변수 및 스크립팅 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.

##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID

동일 [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) 제외를 사용 하 여 마법사에서 생성 된 UINT 문자열 이름 대신 리소스를 식별 합니다.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 마법사에서 생성 한 리소스의 식별자입니다.

### <a name="remarks"></a>설명

ATL 프로젝트 마법사, 마법사를 사용 하 여 컨트롤에서 자동으로 개체를 만들 때 레지스트리 스크립트 기반 지원을 구현 하 고 파일에 DECLARE_REGISTRY_RESOURCEID 매크로 추가 합니다.

ATL 레지스트리 구성 요소 (등록자)에 최적화 된 레지스트리 액세스를 사용 하 여 정적으로 연결할 수 있습니다. 등록자 코드를 정적으로 연결할 stdafx.h 파일에 다음 줄을 추가 합니다.

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

런타임 시 대체 값으로 대체 하는 ATL 원한다 면 DECLARE_REGISTRY_RESOURCE 또는 DECLARE_REGISTRY_RESOURCEID 매크로 지정 하지 마십시오. 대신, 배열을 만든 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자 값을 사용 하 여 쌍을 이루는 구조, 각 항목 변수 자리 표시자를 포함 하는 위치입니다. 그런 다음 호출 [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) 하거나 [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), 배열을 전달 합니다. 모든에서 대체 값이 추가 `_ATL_REGMAP_ENTRIES` 기관의 대체 맵 구조입니다.

대체 가능 매개 변수 및 스크립팅 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
