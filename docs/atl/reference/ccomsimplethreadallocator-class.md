---
title: CComSimpleThreadAllocator 클래스
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: ef1f86ca832674ba5710083b08b67f0a775a7a33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246155"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator 클래스

이 클래스는 클래스에 대 한 스레드 선택을 관리 `CComAutoThreadModule`합니다.

## <a name="syntax"></a>구문

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComSimpleThreadAllocator::GetThread](#getthread)|스레드를 선택 합니다.|

## <a name="remarks"></a>설명

`CComSimpleThreadAllocator` 관리에 대 한 스레드 선택을 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다. `CComSimpleThreadAllocator::GetThread` 단순히 각 스레드를 순환 하 고 시퀀스의 다음 항목을 반환 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="getthread"></a>  CComSimpleThreadAllocator::GetThread

시퀀스의 다음 스레드를 지정 하 여 스레드를 선택 합니다.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>매개 변수

*pApt*<br/>
ATL의 기본 구현에서 사용 되지 않습니다.

*nThreads*<br/>
EXE 모듈의 스레드의 최대 수입니다.

### <a name="return-value"></a>반환 값

0 사이의 정수 및 (*nThreads* -1). EXE 모듈에서 스레드 중 하나를 식별합니다.

### <a name="remarks"></a>설명

재정의할 수 있습니다 `GetThread` 선택 영역의 다른 메서드를 제공 하거나 변경 하려면 사용 합니다 *pApt* 매개 변수입니다.

`GetThread` 호출한 [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)합니다.

## <a name="see-also"></a>참고자료

[CComApartment 클래스](../../atl/reference/ccomapartment-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
