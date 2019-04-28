---
title: IRunnableObjectImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
ms.openlocfilehash: 44b1e0ae1b72a40b45abe0650eb69a279b5a84d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62200341"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl 클래스

이 클래스는 구현 `IUnknown` 의 기본 구현을 제공 합니다 [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) 인터페이스입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IRunnableObjectImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IRunnableObjectImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|실행 중인 컨트롤의 CLSID를 반환합니다. ATL 구현 GUID_NULL를 CLSID를 설정 하 고 E_UNEXPECTED를 반환 합니다.|
|[IRunnableObjectImpl::IsRunning](#isrunning)|컨트롤이 실행 되 고 있는지 확인 합니다. ATL 구현 TRUE를 반환합니다.|
|[IRunnableObjectImpl::LockRunning](#lockrunning)|실행 중인 상태로 컨트롤을 잠급니다. ATL 구현은 S_OK를 반환 합니다.|
|[IRunnableObjectImpl::Run](#run)|강제로 실행 하도록 합니다. ATL 구현은 S_OK를 반환 합니다.|
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|컨트롤이 포함 되어 있음을 나타냅니다. ATL 구현은 S_OK를 반환 합니다.|

## <a name="remarks"></a>설명

합니다 [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) 인터페이스 컨트롤 실행 되 고 있는지 확인 하 고, 실행 또는 실행 중인 상태로 잠금 강제로 컨테이너를 사용 하도록 설정 합니다. 클래스 `IRunnableObjectImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IRunnableObject`

`IRunnableObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass

실행 중인 컨트롤의 CLSID를 반환합니다.

```
HRESULT GetRunningClass(LPCLSID lpClsid);
```

### <a name="return-value"></a>반환 값

ATL 구현 집합 \* *lpClsid* GUID_NULL를 E_UNEXPECTED 반환 합니다.

### <a name="remarks"></a>설명

참조 [IRunnableObject::GetRunningClass](/windows/desktop/api/objidl/nf-objidl-irunnableobject-getrunningclass) Windows SDK에에서 있습니다.

##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning

컨트롤이 실행 되 고 있는지 확인 합니다.

```
virtual BOOL IsRunning();
```

### <a name="return-value"></a>반환 값

ATL 구현 TRUE를 반환합니다.

### <a name="remarks"></a>설명

참조 [IRunnableObject::IsRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-isrunning) Windows SDK에에서 있습니다.

##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning

실행 중인 상태로 컨트롤을 잠급니다.

```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```

### <a name="return-value"></a>반환 값

ATL 구현은 S_OK를 반환 합니다.

### <a name="remarks"></a>설명

참조 [IRunnableObject::LockRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-lockrunning) Windows SDK에에서 있습니다.

##  <a name="run"></a>  IRunnableObjectImpl::Run

강제로 실행 하도록 합니다.

```
HRESULT Run(LPBINDCTX lpbc);
```

### <a name="return-value"></a>반환 값

ATL 구현은 S_OK를 반환 합니다.

### <a name="remarks"></a>설명

참조 [IRunnableObject::Run](/windows/desktop/api/objidl/nf-objidl-irunnableobject-run) Windows SDK에에서 있습니다.

##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject

컨트롤이 포함 되어 있음을 나타냅니다.

```
HRESULT SetContainedObject(BOOL fContained);
```

### <a name="return-value"></a>반환 값

ATL 구현은 S_OK를 반환 합니다.

### <a name="remarks"></a>설명

참조 [IRunnableObject::SetContainedObject](/windows/desktop/api/objidl/nf-objidl-irunnableobject-setcontainedobject) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
