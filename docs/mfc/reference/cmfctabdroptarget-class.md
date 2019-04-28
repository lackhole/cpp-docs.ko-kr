---
title: CMFCTabDropTarget 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
ms.openlocfilehash: 8b24d7679edfaab4d4eeb6d59770f30cd4253580
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252986"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget 클래스

탭 컨트롤을 OLE 라이브러리 사이의 통신 메커니즘을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCTabDropTarget : public COleDropTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CMFCTabDropTarget::CMFCTabDropTarget`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|사용자가 탭 창으로 개체를 끌 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|포커스가 있는 탭 창 외부에서 개체를 끌 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|
|[CMFCTabDropTarget::OnDragOver](#ondragover)|포커스가 있는 탭 창에 개체를 끌 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[CMFCTabDropTarget::OnDropEx](#ondropex)|끌기 작업의 끝에 마우스 단추를 놓을 때 프레임 워크에서 호출 됩니다. (재정의 [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[CMFCTabDropTarget::Register](#register)|OLE 끌어서 놓기 작업의 대상이 될 수 있는 형식으로 컨트롤을 등록 합니다.|

### <a name="remarks"></a>설명

이 클래스는 끌어서 놓기 지원을 제공 합니다 `CMFCBaseTabCtrl` 클래스입니다. 응용 프로그램 사용 하 여 OLE 라이브러리를 초기화 하는 경우는 [AfxOleInit](ole-initialization.md#afxoleinit) 함수를 `CMFCBaseTabCtrl` 개체 끌어서 놓기 작업에 대해 자신을 등록 합니다.

`CMFCTabDropTarget` 클래스는 커서 아래에 있는 경우 끌기 작업이 발생 하는 활성 탭 하 여 해당 기본 클래스를 확장 합니다. 끌어서 놓기 작업에 대 한 자세한 내용은 참조 하십시오 [끌어서 놓기 (OLE)](../../mfc/drag-and-drop-ole.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCTabDropTarget` 개체를 생성하고 해당 `Register` 메서드를 사용하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxbasetabctrl.h

##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter

사용자가 탭 창으로 개체를 끌 때 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pWnd*|[in] 사용 되지 않습니다.|
|*pDataObject*|[in] 끌 개체에 대 한 포인터입니다.|
|*dwKeyState*|[in] 보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.|
|*point*|[in] 클라이언트 좌표에서 커서의 위치입니다.|

### <a name="return-value"></a>반환 값

지정 된 위치에서 발생 하는 경우 발생 하는 효과 *지점*합니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>설명

이 메서드는 프레임 워크를 도구 모음 사용자 지정 모드에 있지 않습니다. 또는 클립보드 데이터 형식을 사용할 수 없는 경우 DROPEFFECT_NONE를 반환 합니다. 호출의 결과 반환 하는 고, 그렇지 `CMFCBaseTabCtrl::OnDragEnter` 제공 된 매개 변수를 사용 합니다.

사용자 지정 모드에 대 한 자세한 내용은 참조 하세요. [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)합니다. 클립보드 데이터 형식에 대 한 자세한 내용은 참조 하세요. [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)합니다.

##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave

포커스가 있는 탭 창 외부에서 개체를 끌 때 프레임 워크에서 호출 됩니다.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pWnd*|[in] 사용 되지 않습니다.|

### <a name="remarks"></a>설명

이 메서드를 호출 합니다 `CMFCBaseTabCtrl::OnDragLeave` 끌기 작업을 수행 하는 방법입니다.

##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver

포커스가 있는 탭 창에 개체를 끌 때 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pWnd*|[in] 사용 되지 않습니다.|
|*pDataObject*|[in] 끌 개체에 대 한 포인터입니다.|
|*dwKeyState*|[in] 보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.|
|*point*|[in] 클라이언트 좌표로 나타낸에서 마우스 포인터의 위치입니다.|

### <a name="return-value"></a>반환 값

지정 된 위치에서 발생 하는 경우 발생 하는 효과 *지점*합니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>설명

이 메서드는 커서 아래에 있는 경우 끌기 작업이 발생 하는 활성 탭으로 설정 합니다. 도구 모음 프레임 워크를 사용자 지정 모드에 있지 않습니다. 또는 클립보드 데이터 형식을 사용할 수 없는 경우에 DROPEFFECT_NONE을 반환 합니다. 호출의 결과 반환 하는 고, 그렇지 `CMFCBaseTabCtrl::OnDragOver` 제공 된 매개 변수를 사용 합니다.

사용자 지정 모드에 대 한 자세한 내용은 참조 하세요. [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)합니다. 클립보드 데이터 형식에 대 한 자세한 내용은 참조 하세요. [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)합니다.

##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx

끌기 작업의 끝에 마우스 단추를 놓을 때 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pWnd*|[in] 사용 되지 않습니다.|
|*pDataObject*|[in] 끌 개체에 대 한 포인터입니다.|
|*dropEffect*|[in] 기본 삭제 작업입니다.|
|*dropList*|[in] 사용 되지 않습니다.|
|*point*|[in] 클라이언트 좌표로 나타낸에서 마우스 포인터의 위치입니다.|

### <a name="return-value"></a>반환 값

결과 놓기 효과입니다. 다음 중 하나 이상의 수 있습니다.

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>설명

이 메서드를 호출 `CMFCBaseTabCtrl::OnDrop` 이 프레임 워크 도구 모음 사용자 지정 모드는 고 클립보드 데이터 형식을 사용할 수 있습니다. 경우에 대 한 호출 `CMFCBaseTabCtrl::OnDrop` 으로 지정 된 기본 놓기 효과 반환 하는 0이 아닌 값을이 메서드가 반환 *dropEffect*합니다. 그렇지 않은 경우이 메서드는 DROPEFFECT_NONE를 반환합니다. 끌어서 놓기 작업 결과 대 한 자세한 내용은 참조 하세요. [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex)합니다.

사용자 지정 모드에 대 한 자세한 내용은 참조 하세요. [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)합니다. 클립보드 데이터 형식에 대 한 자세한 내용은 참조 하세요. [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)합니다.

##  <a name="register"></a>  CMFCTabDropTarget::Register

OLE 끌어서 놓기 작업의 대상이 될 수 있는 형식으로 컨트롤을 등록 합니다.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pOwner*|[in] 탭 컨트롤을 놓기 대상으로 등록입니다.|

### <a name="return-value"></a>반환 값

등록에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) 끌어서 놓기 작업에 대 한 컨트롤을 등록 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[끌어서 놓기(OLE)](../../mfc/drag-and-drop-ole.md)
