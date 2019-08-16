---
title: CComMultiThreadModelNoCS 클래스
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
ms.openlocfilehash: 01c7f953b6b8916394ee4c2b5b27cf84af52b920
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497079"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS 클래스

`CComMultiThreadModelNoCS`임계 영역 잠금 또는 잠금 해제 기능 없이 변수 값을 증가 및 감소 시키는 스레드로부터 안전한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|Description|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)클래스를 참조 합니다.|
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|References 클래스 `CComFakeCriticalSection`입니다.|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|References 클래스 `CComMultiThreadModelNoCS`입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|정적인 스레드로부터 안전한 방식으로 지정 된 변수의 값을 감소 시킵니다.|
|[CComMultiThreadModelNoCS::Increment](#increment)|정적인 스레드로부터 안전한 방식으로 지정 된 변수의 값을 증가 시킵니다.|

## <a name="remarks"></a>설명

`CComMultiThreadModelNoCS`는 변수를 증가 및 감소 시킬 수 있는 스레드로부터 안전한 메서드를 제공 한다는 점에서 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 와 비슷합니다. 그러나를 통해 `CComMultiThreadModelNoCS`임계 영역 클래스를 참조 하는 경우 및 `Unlock` 와 `Lock` 같은 메서드는 아무 작업도 수행 하지 않습니다.

일반적으로는 `CComMultiThreadModelNoCS` `ThreadModelNoCS` **typedef** 이름을 통해를 사용 합니다. 이 **typedef** 는, `CComMultiThreadModel`및 `CComMultiThreadModelNoCS` [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)에 정의 되어 있습니다.

> [!NOTE]
>  전역 **typedef** 이름 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 및 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) 는 참조 `CComMultiThreadModelNoCS`하지 않습니다.

외 `ThreadModelNoCS`에도 `CComMultiThreadModelNoCS` `AutoCriticalSection` 및 을`CriticalSection`정의 합니다. 이러한 두 번째 **typedef** 이름은 임계 영역을 가져오고 해제 하는 것과 관련 된 빈 메서드를 제공 하는 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)를 참조 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection

를 사용 `CComMultiThreadModelNoCS`하는 경우 typedef `AutoCriticalSection` 이름이 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)클래스를 참조 합니다.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>설명

는 `CComFakeCriticalSection` 임계 영역을 제공 하지 않으므로 해당 메서드는 아무 작업도 수행 하지 않습니다.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 에는에 대 `AutoCriticalSection`한 정의도 포함 되어 있습니다. 다음 표에서는에서 `AutoCriticalSection`참조 하는 스레딩 모델 클래스와 임계 영역 클래스 간의 관계를 보여 줍니다.

|클래스 정의|참조 된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

외 `AutoCriticalSection`에도 **typedef** 이름 [CriticalSection](#criticalsection)을 사용할 수 있습니다. CRT 시작 코드를 `AutoCriticalSection` 제거 하려는 경우에는 전역 개체 또는 정적 클래스 멤버에를 지정 하면 안 됩니다.

### <a name="example"></a>예제

[CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)를 참조 하세요.

##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection

를 사용 `CComMultiThreadModelNoCS`하는 경우 typedef `CriticalSection` 이름이 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)클래스를 참조 합니다.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>설명

는 `CComFakeCriticalSection` 임계 영역을 제공 하지 않으므로 해당 메서드는 아무 작업도 수행 하지 않습니다.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 에는에 대 `CriticalSection`한 정의도 포함 되어 있습니다. 다음 표에서는에서 `CriticalSection`참조 하는 스레딩 모델 클래스와 임계 영역 클래스 간의 관계를 보여 줍니다.

|클래스 정의|참조 된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

외 `CriticalSection`에도 **typedef** 이름을 `AutoCriticalSection`사용할 수 있습니다. CRT 시작 코드를 `AutoCriticalSection` 제거 하려는 경우에는 전역 개체 또는 정적 클래스 멤버에를 지정 하면 안 됩니다.

### <a name="example"></a>예제

[CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)를 참조 하세요.

##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement

이 정적 함수는 *p*로 가리키는 변수의 값을 감소 시키는 Win32 함수 [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)를 호출 합니다.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
진행 감소 시킬 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

감소 결과가 0 이면는 0을 `Decrement` 반환 합니다. 감소 결과 값이 0이 아니면 반환 값도 0이 아니라 감소의 결과와 다를 수 있습니다.

### <a name="remarks"></a>설명

**InterlockedDecrement** 은이 변수를 사용 하 여 두 개 이상의 스레드가 동시에 수행 되지 않도록 방지 합니다.

##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment

이 정적 함수는 *p*로 가리키는 변수의 값을 증가 시키는 Win32 함수 [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)를 호출 합니다.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
진행 증가 시킬 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

증가값의 결과가 0 이면 **increment** 는 0을 반환 합니다. 증가값의 결과가 0이 아닌 경우 반환 값도 0이 아니라 증가값의 결과와 다를 수 있습니다.

### <a name="remarks"></a>설명

**InterlockedIncrement** 은이 변수를 사용 하 여 두 개 이상의 스레드가 동시에 수행 되지 않도록 방지 합니다.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS

를 사용 `CComMultiThreadModelNoCS`하는 경우 typedef `ThreadModelNoCS` 이름은를 `CComMultiThreadModelNoCS`참조 합니다.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>설명

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 에는에 대 `ThreadModelNoCS`한 정의도 포함 되어 있습니다. 다음 표에서는에서 `ThreadModelNoCS`참조 하는 클래스와 스레딩 모델 클래스 간의 관계를 보여 줍니다.

|클래스 정의|참조 된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

에서 `ThreadModelNoCS` `CComMultiThreadModel` 의 정의는 및에 대 한 `CComSingleThreadModel`대칭을 제공 합니다. `CComMultiThreadModelNoCS` 예를 들어의 `CComMultiThreadModel::AutoCriticalSection` 샘플 코드에서 다음 **typedef**를 선언 했다고 가정 합니다.

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

에 대해 `ThreadModel` 지정 된 클래스 ( `CComMultiThreadModelNoCS`예:)에 관계 `_ThreadModel` 없이는 그에 따라 확인 됩니다.

### <a name="example"></a>예제

[CComMultiThreadModel:: AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)를 참조 하세요.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
