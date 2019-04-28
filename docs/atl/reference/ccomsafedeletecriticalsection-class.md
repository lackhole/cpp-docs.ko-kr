---
title: CComSafeDeleteCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: 0269079db97e2ff91767c9c0c74a9336fce81ade
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258886"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection 클래스

이 클래스는 가져오기 및 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|생성자입니다.|
|[CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|만들고 임계 영역 개체를 초기화 합니다.|
|[CComSafeDeleteCriticalSection::Lock](#lock)|임계 영역 개체의 소유권을 가져옵니다.|
|[CComSafeDeleteCriticalSection::Term](#term)|임계 영역 개체에서 사용 하는 시스템 리소스를 해제 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_bInitialized](#m_binitialized)|플래그 있는지 여부를 내부 `CRITICAL_SECTION` 개체가 초기화 되었습니다.|

## <a name="remarks"></a>설명

`CComSafeDeleteCriticalSection` 클래스에서 파생 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)합니다. 그러나 `CComSafeDeleteCriticalSection` 를 통해 보안 강화 메커니즘을 제공 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)합니다.

인스턴스가 `CComSafeDeleteCriticalSection` 범위를 벗어날 또는 명시적으로 메모리에서 삭제 기본 임계 영역 개체를 자동으로 정리 됩니다 여전히 유효 합니다. 또한 합니다 [CComSafeDeleteCriticalSection::Term](#term) 메서드는 기본 임계 영역 개체 아직 할당 되지 않은 또는 이미 메모리에서 해제 하는 경우 정상적으로 종료 됩니다.

참조 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 임계 도우미 클래스에 대 한 자세한 내용은 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection

생성자입니다.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>설명

설정 된 [m_bInitialized](#m_binitialized) FALSE 데이터 멤버입니다.

##  <a name="dtor"></a>  CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection

소멸자입니다.

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>설명

내부 해제 `CRITICAL_SECTION` 하는 경우 메모리에서 개체를 [m_bInitialized](#m_binitialized) 데이터 멤버를 TRUE로 설정 합니다.

##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init

기본 클래스 구현을 호출 [Init](/visualstudio/debugger/init) 집합과 [m_bInitialized](#m_binitialized) 성공한 경우 TRUE로 합니다.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>반환 값

결과 반환 합니다 [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init)합니다.

##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock

기본 클래스 구현을 호출 [잠금](ccomcriticalsection-class.md#lock)합니다.

```
HRESULT Lock();
```

### <a name="return-value"></a>반환 값

결과 반환 합니다 [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)합니다.

### <a name="remarks"></a>설명

이 메서드에서 [m_bInitialized](#m_binitialized) 데이터 멤버를 항목으로 TRUE로 설정 합니다. 어설션은이 condidtion 충족 되지 않으면 디버그 빌드에서 생성 됩니다.

함수 동작에 자세한 내용은를 참조 [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)합니다.

##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized

플래그 있는지 여부를 내부 `CRITICAL_SECTION` 개체가 초기화 되었습니다.

```
bool m_bInitialized;
```

### <a name="remarks"></a>설명

합니다 `m_bInitialized` 데이터 멤버의 내부 유효성을 추적 하는 `CRITICAL_SECTION` 연관 된 개체를 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 클래스입니다. 기본 `CRITICAL_SECTION` 개체가이 플래그가 TRUE로 설정 하지 않으면 메모리에서 해제를 시도 되지 것입니다.

##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term

기본 클래스 구현을 호출 [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) 하는 경우 내부 `CRITICAL_SECTION` 개체는 유효 합니다.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>반환 값

결과 반환 합니다 [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), 또는 s_ok이 고, 경우 [m_bInitialized](#m_binitialized) 진입할 때 FALSE로 설정 되었습니다.

### <a name="remarks"></a>설명

내부 경우에도이 메서드를 호출 하지 않아도 안전 합니다 `CRITICAL_SECTION` 개체가 잘못 되었습니다. 이 클래스의 소멸자는 경우이 메서드를 호출 합니다 [m_bInitialized](#m_binitialized) 데이터 멤버를 TRUE로 설정 합니다.

## <a name="see-also"></a>참고자료

[CComCriticalSection 클래스](../../atl/reference/ccomcriticalsection-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
