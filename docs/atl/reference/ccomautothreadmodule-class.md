---
title: CComAutoThreadModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 9b0fa685bf9a7de94b158bd62b00161c1b58562d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260216"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule 클래스

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>매개 변수

*ThreadAllocator*<br/>
[in] 스레드 선택 영역을 관리 하는 클래스입니다. 기본값은 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)합니다.

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CreateInstance](#createinstance)|스레드를 선택 하 고 연결 아파트에서 개체를 만듭니다.|
|[GetDefaultThreads](#getdefaultthreads)|(정적) 프로세서의 수에 따라 모듈에 대 한 스레드 수를 동적으로 계산 합니다.|
|[Init](#init)|모듈의 스레드를 만듭니다.|
|[잠금](#lock)|모듈에는 현재 스레드에서 잠금 수를 늘립니다.|
|[잠금 해제](#unlock)|모듈에는 현재 스레드에서 잠금 횟수를 줄입니다.|

### <a name="data-members"></a>데이터 멤버

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[dwThreadID](#dwthreadid)|현재 스레드의 식별자를 포함 합니다.|
|[m_Allocator](#m_allocator)|스레드 선택 영역을 관리합니다.|
|[m_nThreads](#m_nthreads)|모듈의 스레드 수를 포함합니다.|
|[m_pApartments](#m_papartments)|모듈의 아파트를 관리합니다.|

## <a name="remarks"></a>설명

> [!NOTE]
>  이 클래스는 사용 되지 않는으로 바뀌는 것을 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 하 고 [CAtlModule](../../atl/reference/catlmodule-class.md) 클래스를 파생 합니다. 에 나오는 정보는 이전 릴리스의 ATL. 사용은

`CComAutoThreadModule` 파생 [CComModule](../../atl/reference/ccommodule-class.md) Exe 및 Windows 서비스에 대 한 스레드 풀링, 아파트 모델 COM 서버 구현입니다. `CComAutoThreadModule` 사용 하 여 [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 각 스레드에 대 한 아파트를 관리 합니다.

모듈을 파생 `CComAutoThreadModule` 여러 아파트에서 개체를 만들려는 경우입니다. 포함 해야 합니다 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 지정 하 여 개체의 클래스 정의에서 매크로 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 합니다.

기본적으로 ATL COM 응용 프로그램 마법사 (VISUAL Studio에서에서 ATL 프로젝트 마법사)에서 모듈을 파생 됩니다 `CComModule`합니다. 사용할 `CComAutoThreadModule`를 클래스 정의 수정 합니다. 예를 들어:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="createinstance"></a>  CComAutoThreadModule::CreateInstance

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>매개 변수

*pfnCreateInstance*<br/>
[in] 작성자 함수에 대 한 포인터입니다.

*riid*<br/>
[in] 요청된 된 인터페이스의 IID입니다.

*ppvObj*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *riid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppvObj* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

스레드를 선택 하 고 연결 아파트에서 개체를 만듭니다.

##  <a name="dwthreadid"></a>  CComAutoThreadModule::dwThreadID

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
DWORD dwThreadID;
```

### <a name="remarks"></a>설명

현재 스레드의 식별자를 포함 합니다.

##  <a name="getdefaultthreads"></a>  CComAutoThreadModule::GetDefaultThreads

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>반환 값

EXE 모듈에서 생성 될 스레드의 수입니다.

### <a name="remarks"></a>설명

이 정적 함수는 동적으로 프로세서의 수에 따라 EXE 모듈에 대 한 스레드의 최대 수를 계산 합니다. 기본적으로이 반환 값을 전달 합니다 [Init](#init) 스레드를 만드는 방법.

##  <a name="init"></a>  CComAutoThreadModule::Init

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>매개 변수

*p*<br/>
[in] 개체 맵 항목의 배열에 대 한 포인터입니다.

*h*<br/>
[in] 에 전달 된 HINSTANCE `DLLMain` 또는 `WinMain`합니다.

*plibid*<br/>
[in] 프로젝트에 연결 된 형식 라이브러리의 LIBID 포인터입니다.

*nThreads*<br/>
[in] 만들 스레드의 수입니다. 기본적으로 *nThreads* 반환한 값인 [GetDefaultThreads](#getdefaultthreads)합니다.

### <a name="remarks"></a>설명

데이터 멤버를 초기화 하 고 지정 된 스레드 수를 만듭니다 *nThreads*합니다.

##  <a name="lock"></a>  CComAutoThreadModule::Lock

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
LONG Lock();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

### <a name="remarks"></a>설명

모듈을 현재 스레드에 대 한 잠금 수가에 원자성 증가 수행합니다. `CComAutoThreadModule` 모든 클라이언트 모듈에 액세스 하는 여부를 확인 하려면 모듈 잠금 횟수를 사용 합니다. 현재 스레드에서 잠금 수 통계 용도로 사용 됩니다.

##  <a name="m_allocator"></a>  CComAutoThreadModule::m_Allocator

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>설명

스레드 선택 영역을 관리 하는 개체입니다. 기본적으로 `ThreadAllocator` 클래스 템플릿 매개 변수가 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)합니다.

##  <a name="m_nthreads"></a>  CComAutoThreadModule::m_nThreads

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
int m_nThreads;
```

### <a name="remarks"></a>설명

EXE 모듈에서 스레드 수를 포함합니다. 때 [Init](#init) 가 호출 `m_nThreads` 로 설정 되어 합니다 *nThreads* 매개 변수 값입니다. 연결 된 각 스레드의 아파트에서 관리 되는 [CComApartment](../../atl/reference/ccomapartment-class.md) 개체입니다.

##  <a name="m_papartments"></a>  CComAutoThreadModule::m_pApartments

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>설명

배열을 가리킵니다 [CComApartment](../../atl/reference/ccomapartment-class.md) 개체에는 각 모듈의 아파트를 관리 합니다. 배열의 요소 수에 기반 합니다 [m_nThreads](#m_nthreads) 멤버입니다.

##  <a name="unlock"></a>  CComAutoThreadModule::Unlock

ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
LONG Unlock();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

### <a name="remarks"></a>설명

모듈을 현재 스레드에 대 한 잠금 수에는 원자성 감소를 수행합니다. `CComAutoThreadModule` 모든 클라이언트 모듈에 액세스 하는 여부를 확인 하려면 모듈 잠금 횟수를 사용 합니다. 현재 스레드에서 잠금 수 통계 용도로 사용 됩니다.

모듈 잠금 수가 0에 도달 하면 모듈을 언로드할 수 있습니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
