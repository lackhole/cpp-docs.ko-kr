---
title: CComFakeCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 39a9859380eba1b72768234eb8f43d80fca0143f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259159"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection 클래스

이 클래스와 같은 방법으로 제공 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 하지만 임계 영역을 제공 하지 않습니다.

## <a name="syntax"></a>구문

```
class CComFakeCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.|
|[CComFakeCriticalSection::Lock](#lock)|가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.|
|[CComFakeCriticalSection::Term](#term)|가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.|
|[CComFakeCriticalSection::Unlock](#unlock)|가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.|

## <a name="remarks"></a>설명

`CComFakeCriticalSection` 메서드를 있는 반영 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)합니다. 그러나 `CComFakeCriticalSection` ; 임계 영역을 제공 하지 않습니다 따라서 해당 메서드는 아무것도 수행 합니다.

일반적으로 사용 `CComFakeCriticalSection` 를 통해를 `typedef` 하거나, 이름을 `AutoCriticalSection` 또는 `CriticalSection`. 사용 하는 경우 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 하거나 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), 둘 다 `typedef` 참조 이름을 `CComFakeCriticalSection`입니다. 사용 하는 경우 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)를 참조 하는 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) 고 `CComCriticalSection`, 각각.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

##  <a name="init"></a>  CComFakeCriticalSection::Init

가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="lock"></a>  CComFakeCriticalSection::Lock

가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="term"></a>  CComFakeCriticalSection::Term

가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock

가 아무 작업도 수행 되기 때문에 중요 한 섹션이 없습니다.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
