---
title: IQuickActivateImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 2a2b11746249b6ee4f6ddd578717aacc374d53bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198151"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl 클래스

이 클래스는 컨테이너의 컨트롤 초기화를 단일 호출으로 결합합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IQuickActivateImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|실행 중인 컨트롤의 현재 표시 크기를 검색합니다.|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|로드 되는 컨트롤의 빠른 초기화를 수행 합니다.|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|컨테이너에 할당 된 표시 공간 크기의 컨트롤을 알립니다.|

## <a name="remarks"></a>설명

합니다 [IQuickActivate](/windows/desktop/api/ocidl/nn-ocidl-iquickactivate) 인터페이스 단일 호출에서 초기화를 결합 하 여 컨트롤을 로드할 때 지연이 발생 하지 않도록 하는 컨테이너는 데 도움이 됩니다. 합니다 `QuickActivate` 메서드를 사용 하면 컨테이너에 대 한 포인터를 전달 하는 [QACONTAINER](/windows/desktop/api/ocidl/ns-ocidl-tagqacontainer) 컨트롤 모든 인터페이스에 대 한 포인터를 보유 하는 구조 필요 합니다. 반환이 컨트롤을 다시 전달에 대 한 포인터를 [QACONTROL](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol) 컨테이너에서 사용 되는 자체 인터페이스에 대 한 포인터를 보유 하는 구조입니다. 클래스 `IQuickActivateImpl` 의 기본 구현을 제공 `IQuickActivate` 구현 및 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent

실행 중인 컨트롤의 현재 표시 크기를 검색합니다.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>설명

크기는 컨트롤의 전체 렌더링 되며 HIMETRIC 단위로 지정 됩니다.

참조 [IQuickActivate::GetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) Windows SDK에에서 있습니다.

##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate

로드 되는 컨트롤의 빠른 초기화를 수행 합니다.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>설명

구조는 컨트롤 및 일부 앰비언트 속성의 값에 필요한 인터페이스에 대 한 포인터를 포함 합니다. 반환 될 때 컨트롤에 대 한 포인터를 전달 된 [QACONTROL](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol) 컨테이너에 필요한 자체 인터페이스와 추가 상태 정보에 대 한 포인터를 포함 하는 구조입니다.

참조 [IQuickActivate::QuickActivate](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-quickactivate) Windows SDK에에서 있습니다.

##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent

컨테이너에 할당 된 표시 공간 크기의 컨트롤을 알립니다.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>설명

크기를 HIMETRIC 단위로 지정 됩니다.

참조 [IQuickActivate::SetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
