---
title: CComMultiThreadModel 클래스
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: 74fb68eead498685ef252968124368863e27be75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497098"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel 클래스

`CComMultiThreadModel`변수의 값을 증가 및 감소 시키는 스레드로부터 안전한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CComMultiThreadModel
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)클래스를 참조 합니다.|
|[CComMultiThreadModel::CriticalSection](#criticalsection)|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)클래스를 참조 합니다.|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)클래스를 참조 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CComMultiThreadModel::Decrement](#decrement)|정적인 스레드로부터 안전한 방식으로 지정 된 변수의 값을 감소 시킵니다.|
|[CComMultiThreadModel::Increment](#increment)|정적인 스레드로부터 안전한 방식으로 지정 된 변수의 값을 증가 시킵니다.|

## <a name="remarks"></a>설명

일반적으로 두 가지 `CComMultiThreadModel` **typedef** 이름 ([CComObjectThreadModel] (atl-typedef. md # CComObjectThreadModel 또는 [CComGlobalsThreadModel] (atl-typedef. md # CComGlobalsThreadModel) 중 하나를 사용 합니다. 각 **typedef** 에서 참조 하는 클래스는 다음 표에 나와 있는 것 처럼 사용 된 스레딩 모델에 따라 달라 집니다.

|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`; M= `CComMultiThreadModel`

`CComMultiThreadModel`자체는 세 가지 **typedef** 이름을 정의 합니다. `AutoCriticalSection`및 `CriticalSection` 는 임계 영역에 대 한 소유권을 얻고 해제 하기 위한 메서드를 제공 하는 참조 클래스입니다. `ThreadModelNoCS`references 클래스 [CComMultiThreadModelNoCS (CComMultiThreadModelNoCS-class.md).

## <a name="requirements"></a>요구 사항

**헤더:** 서 기. h

##  <a name="autocriticalsection"></a>  CComMultiThreadModel::AutoCriticalSection

를 사용 `CComMultiThreadModel`하는 경우 typedef `AutoCriticalSection` 이름이 [CComAutoCriticalSection](ccomautocriticalsection-class.md)클래스를 참조 합니다 .이 클래스는 임계 영역 개체의 소유권을 가져오고 해제 하는 메서드를 제공 합니다.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>설명

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) 에는에 대 `AutoCriticalSection`한 정의도 포함 되어 있습니다. 다음 표에서는에서 `AutoCriticalSection`참조 하는 스레딩 모델 클래스와 임계 영역 클래스 간의 관계를 보여 줍니다.

|클래스 정의|참조 된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

외 `AutoCriticalSection`에도 **typedef** 이름 [CriticalSection](#criticalsection)을 사용할 수 있습니다. CRT 시작 코드를 `AutoCriticalSection` 제거 하려는 경우에는 전역 개체 또는 정적 클래스 멤버에를 지정 하면 안 됩니다.

### <a name="example"></a>예제

다음 코드는 [CComObjectRootEx](ccomobjectrootex-class.md)이후에 모델링 되며 스레딩 환경에서 `AutoCriticalSection` 사용 되는 방법을 보여 줍니다.

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

다음 표에서는 응용 프로그램에서 사용 하 `InternalAddRef` 는 `Lock` `ThreadModel` 템플릿 매개 변수 및 스레딩 모델에 따라 및 메서드의 결과를 보여 줍니다.

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel

|메서드|단일 또는 아파트 스레딩|자유 스레딩|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|이 증가값은 스레드로부터 안전 하지 않습니다.|이 증가값은 스레드로부터 안전 합니다.|
|`Lock`|아무 작업도 수행 하지 않습니다. 잠글 임계 섹션이 없습니다.|임계 섹션이 잠겼습니다.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel::ThreadModelNoCS

|메서드|단일 또는 아파트 스레딩|자유 스레딩|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|이 증가값은 스레드로부터 안전 하지 않습니다.|이 증가값은 스레드로부터 안전 합니다.|
|`Lock`|아무 작업도 수행 하지 않습니다. 잠글 임계 섹션이 없습니다.|아무 작업도 수행 하지 않습니다. 잠글 임계 섹션이 없습니다.|

##  <a name="criticalsection"></a>  CComMultiThreadModel::CriticalSection

를 사용 `CComMultiThreadModel`하는 경우 typedef `CriticalSection` 이름이 [CComCriticalSection](ccomcriticalsection-class.md)클래스를 참조 합니다 .이 클래스는 임계 영역 개체의 소유권을 가져오고 해제 하는 메서드를 제공 합니다.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>설명

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) 에는에 대 `CriticalSection`한 정의도 포함 되어 있습니다. 다음 표에서는에서 `CriticalSection`참조 하는 스레딩 모델 클래스와 임계 영역 클래스 간의 관계를 보여 줍니다.

|클래스 정의|참조 된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

외 `CriticalSection`에도 **typedef** 이름 [AutoCriticalSection](#autocriticalsection)을 사용할 수 있습니다. CRT 시작 코드를 `AutoCriticalSection` 제거 하려는 경우에는 전역 개체 또는 정적 클래스 멤버에를 지정 하면 안 됩니다.

### <a name="example"></a>예제

[CComMultiThreadModel:: AutoCriticalSection](#autocriticalsection)를 참조 하세요.

##  <a name="decrement"></a>  CComMultiThreadModel::Decrement

이 정적 함수는 *p*로 가리키는 변수의 값을 감소 시키는 Win32 함수 [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)를 호출 합니다.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
진행 감소 시킬 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

감소 결과가 0 이면는 0을 `Decrement` 반환 합니다. 감소 결과 값이 0이 아니면 반환 값도 0이 아니라 감소의 결과와 다를 수 있습니다.

### <a name="remarks"></a>설명

`InterlockedDecrement`이 변수를 사용 하 여 두 개 이상의 스레드가 동시에 수행 되지 않도록 합니다.

##  <a name="increment"></a>  CComMultiThreadModel::Increment

이 정적 함수는 *p*로 가리키는 변수의 값을 증가 시키는 Win32 함수 [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)를 호출 합니다.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
진행 증가 시킬 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

증가값의 결과가 0 이면는 0을 `Increment` 반환 합니다. 증가값의 결과가 0이 아닌 경우 반환 값도 0이 아니라 증가값의 결과와 다를 수 있습니다.

### <a name="remarks"></a>설명

`InterlockedIncrement`이 변수를 사용 하 여 두 개 이상의 스레드가 동시에 수행 되지 않도록 합니다.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS

를 사용 `CComMultiThreadModel`하는 경우 typedef `ThreadModelNoCS` 이름이 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)클래스를 참조 합니다.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>설명

`CComMultiThreadModelNoCS`변수를 증가 및 감소 시키는 스레드로부터 안전한 메서드를 제공 합니다. 그러나 중요 한 섹션은 제공 하지 않습니다.

[CComSingleThreadModel에](ccomsinglethreadmodel-class.md) 는에 대 한 `ThreadModelNoCS`정의 도포함되어있습니다.`CComMultiThreadModelNoCS` 다음 표에서는에서 `ThreadModelNoCS`참조 하는 클래스와 스레딩 모델 클래스 간의 관계를 보여 줍니다.

|클래스 정의|참조 된 클래스|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>예제

[CComMultiThreadModel:: AutoCriticalSection](#autocriticalsection)를 참조 하세요.

## <a name="see-also"></a>참고자료

[CComSingleThreadModel 클래스](ccomsinglethreadmodel-class.md)<br/>
[CComAutoCriticalSection 클래스](ccomautocriticalsection-class.md)<br/>
[CComCriticalSection 클래스](ccomcriticalsection-class.md)<br/>
[클래스 개요](../atl-class-overview.md)
