---
title: COleClientItem 클래스
ms.date: 07/02/2019
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
helpviewer_keywords:
- COleClientItem [MFC], COleClientItem
- COleClientItem [MFC], Activate
- COleClientItem [MFC], ActivateAs
- COleClientItem [MFC], AttachDataObject
- COleClientItem [MFC], CanCreateFromData
- COleClientItem [MFC], CanCreateLinkFromData
- COleClientItem [MFC], CanPaste
- COleClientItem [MFC], CanPasteLink
- COleClientItem [MFC], Close
- COleClientItem [MFC], ConvertTo
- COleClientItem [MFC], CopyToClipboard
- COleClientItem [MFC], CreateCloneFrom
- COleClientItem [MFC], CreateFromClipboard
- COleClientItem [MFC], CreateFromData
- COleClientItem [MFC], CreateFromFile
- COleClientItem [MFC], CreateLinkFromClipboard
- COleClientItem [MFC], CreateLinkFromData
- COleClientItem [MFC], CreateLinkFromFile
- COleClientItem [MFC], CreateNewItem
- COleClientItem [MFC], CreateStaticFromClipboard
- COleClientItem [MFC], CreateStaticFromData
- COleClientItem [MFC], Deactivate
- COleClientItem [MFC], DeactivateUI
- COleClientItem [MFC], Delete
- COleClientItem [MFC], DoDragDrop
- COleClientItem [MFC], DoVerb
- COleClientItem [MFC], Draw
- COleClientItem [MFC], GetActiveView
- COleClientItem [MFC], GetCachedExtent
- COleClientItem [MFC], GetClassID
- COleClientItem [MFC], GetClipboardData
- COleClientItem [MFC], GetDocument
- COleClientItem [MFC], GetDrawAspect
- COleClientItem [MFC], GetExtent
- COleClientItem [MFC], GetIconFromRegistry
- COleClientItem [MFC], GetIconicMetafile
- COleClientItem [MFC], GetInPlaceWindow
- COleClientItem [MFC], GetItemState
- COleClientItem [MFC], GetLastStatus
- COleClientItem [MFC], GetLinkUpdateOptions
- COleClientItem [MFC], GetType
- COleClientItem [MFC], GetUserType
- COleClientItem [MFC], IsInPlaceActive
- COleClientItem [MFC], IsLinkUpToDate
- COleClientItem [MFC], IsModified
- COleClientItem [MFC], IsOpen
- COleClientItem [MFC], IsRunning
- COleClientItem [MFC], OnActivate
- COleClientItem [MFC], OnActivateUI
- COleClientItem [MFC], OnChange
- COleClientItem [MFC], OnDeactivate
- COleClientItem [MFC], OnDeactivateUI
- COleClientItem [MFC], OnGetClipboardData
- COleClientItem [MFC], OnInsertMenus
- COleClientItem [MFC], OnRemoveMenus
- COleClientItem [MFC], OnSetMenu
- COleClientItem [MFC], OnShowControlBars
- COleClientItem [MFC], OnUpdateFrameTitle
- COleClientItem [MFC], ReactivateAndUndo
- COleClientItem [MFC], Release
- COleClientItem [MFC], Reload
- COleClientItem [MFC], Run
- COleClientItem [MFC], SetDrawAspect
- COleClientItem [MFC], SetExtent
- COleClientItem [MFC], SetHostNames
- COleClientItem [MFC], SetIconicMetafile
- COleClientItem [MFC], SetItemRects
- COleClientItem [MFC], SetLinkUpdateOptions
- COleClientItem [MFC], SetPrintDevice
- COleClientItem [MFC], UpdateLink
- COleClientItem [MFC], CanActivate
- COleClientItem [MFC], OnChangeItemPosition
- COleClientItem [MFC], OnDeactivateAndUndo
- COleClientItem [MFC], OnDiscardUndoState
- COleClientItem [MFC], OnGetClipRect
- COleClientItem [MFC], OnGetItemPosition
- COleClientItem [MFC], OnGetWindowContext
- COleClientItem [MFC], OnScrollBy
- COleClientItem [MFC], OnShowItem
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
ms.openlocfilehash: 6c370271f1508f79ea20cdf84b38b1f3dc2df023
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552273"
---
# <a name="coleclientitem-class"></a>COleClientItem 클래스

OLE 항목에 대한 컨테이너 인터페이스를 정의합니다.

## <a name="syntax"></a>구문

```
class COleClientItem : public CDocItem
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleClientItem::COleClientItem](#coleclientitem)|`COleClientItem` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleClientItem::Activate](#activate)|작업에 대 한 OLE 항목 열리고 지정된 된 동사를 실행 합니다.|
|[COleClientItem::ActivateAs](#activateas)|다른 형식으로 항목을 활성화합니다.|
|[COleClientItem::AttachDataObject](#attachdataobject)|OLE 개체의 데이터에 액세스합니다.|
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|컨테이너 응용 프로그램을 포함된 된 개체를 만들 수 있는지 여부를 나타냅니다.|
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|컨테이너 응용 프로그램을 연결된 된 개체를 만들 수 있는지 여부를 나타냅니다.|
|[COleClientItem::CanPaste](#canpaste)|포함 가능한 또는 정적 OLE 항목을 클립보드에 포함 되는지 여부를 나타냅니다.|
|[COleClientItem::CanPasteLink](#canpastelink)|클립보드에 링크할 수 있는 OLE 항목을 포함 되는지 여부를 나타냅니다.|
|[COleClientItem::Close](#close)|서버에 대 한 링크를 닫지만 OLE 항목을 제거 하지 않습니다.|
|[COleClientItem::ConvertTo](#convertto)|항목을 다른 형식으로 변환 합니다.|
|[COleClientItem::CopyToClipboard](#copytoclipboard)|OLE 항목을 클립보드에 복사합니다.|
|[COleClientItem::CreateCloneFrom](#createclonefrom)|기존 항목의 복제본을 만듭니다.|
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|클립보드의 포함 된 항목을 만듭니다.|
|[COleClientItem::CreateFromData](#createfromdata)|데이터 개체에서 포함 된 항목을 만듭니다.|
|[COleClientItem::CreateFromFile](#createfromfile)|파일에서 포함 된 항목을 만듭니다.|
|[COleClientItem::CreateLinkFromClipboard](#createlinkfromclipboard)|클립보드의 연결 된 항목을 만듭니다.|
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|데이터 개체에서 연결 된 항목을 만듭니다.|
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|파일에서 연결된 된 항목을 만듭니다.|
|[COleClientItem::CreateNewItem](#createnewitem)|서버 응용 프로그램을 실행 하 여 새 포함 된 항목을 만듭니다.|
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|클립보드에서 정적 항목을 만듭니다.|
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|데이터 개체에서 정적 항목을 만듭니다.|
|[COleClientItem::Deactivate](#deactivate)|항목을 비활성화합니다.|
|[COleClientItem::DeactivateUI](#deactivateui)|컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원합니다.|
|[COleClientItem::Delete](#delete)|삭제 하거나 연결 된 항목을 되었으면 OLE 항목을 닫습니다.|
|[COleClientItem::DoDragDrop](#dodragdrop)|끌어서 놓기 작업을 수행합니다.|
|[COleClientItem::DoVerb](#doverb)|지정된 된 동사를 실행합니다.|
|[COleClientItem::Draw](#draw)|OLE 항목을 그립니다.|
|[COleClientItem::GetActiveView](#getactiveview)|항목 위치에서 활성화 되는 뷰를 가져옵니다.|
|[COleClientItem::GetCachedExtent](#getcachedextent)|OLE 항목의 직사각형의 경계를 반환합니다.|
|[COleClientItem::GetClassID](#getclassid)|현재 항목의 클래스 ID를 가져옵니다.|
|[COleClientItem::GetClipboardData](#getclipboarddata)|호출 하 여 클립보드에 배치 하는 데이터를 가져옵니다는 `CopyToClipboard` 멤버 함수입니다.|
|[COleClientItem::GetDocument](#getdocument)|반환 된 `COleDocument` 있는 항목이 포함 된 개체입니다.|
|[COleClientItem::GetDrawAspect](#getdrawaspect)|렌더링에 대 한 항목의 현재 뷰를 가져옵니다.|
|[COleClientItem::GetExtent](#getextent)|OLE 항목의 직사각형의 경계를 반환합니다.|
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|특정 CLSID의 서버에 연결 된 아이콘에 대 한 핸들을 검색 합니다.|
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 가져옵니다.|
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|항목의 전체 편집 창에 대 한 포인터를 반환합니다.|
|[COleClientItem::GetItemState](#getitemstate)|항목의 현재 상태를 가져옵니다.|
|[COleClientItem::GetLastStatus](#getlaststatus)|마지막 OLE 작업의 상태를 반환 합니다.|
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|연결된 된 항목 (고급 기능)에 대 한 업데이트 모드를 반환합니다.|
|[COleClientItem::GetType](#gettype)|OLE 항목의 유형 (포함 된, 연결, 또는 정적)를 반환합니다.|
|[COleClientItem::GetUserType](#getusertype)|항목의 형식을 설명 하는 문자열을 가져옵니다.|
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|항목이 내부 활성 이면 TRUE를 반환 합니다.|
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|원본 문서를 사용 하 여 최신 상태 인지 하는 TRUE 이면 연결 된 항목을 반환 합니다.|
|[COleClientItem::IsModified](#ismodified)|TRUE 반환 항목이 마지막으로 수정 된 경우 저장 합니다.|
|[COleClientItem::IsOpen](#isopen)|TRUE를 반환 된 항목이 현재 경우 서버 응용 프로그램에서 엽니다.|
|[COleClientItem::IsRunning](#isrunning)|항목의 서버 응용 프로그램을 실행 하는 경우 TRUE를 반환 합니다.|
|[COleClientItem::OnActivate](#onactivate)|활성화 된 항목에 알리기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnActivateUI](#onactivateui)|활성화 된 해당 사용자 인터페이스를 표시 해야 하는 항목에 알리기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnChange](#onchange)|서버는 OLE 항목을 변경할 때 호출 됩니다. 필요한 구현입니다.|
|[COleClientItem::OnDeactivate](#ondeactivate)|항목 비활성화 되 면 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|서버에 전체 사용자 인터페이스를 제거 하는 경우 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|클립보드에 복사할 데이터를 가져오기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnInsertMenus](#oninsertmenus)|합성 메뉴를 만드는 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnRemoveMenus](#onremovemenus)|합성 메뉴에서 컨테이너의 메뉴를 제거 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnSetMenu](#onsetmenu)|설치 및 합성 메뉴를 제거 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|표시 및 컨트롤 막대를 숨기기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|프레임 창의 제목 표시줄을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|항목을 다시 활성화 하 고 마지막으로 전체 편집 작업을 실행 취소 합니다.|
|[COleClientItem::Release](#release)|OLE 링크 된 항목에 대 한 연결을 해제 하 고 열려 있었던 경우 닫습니다. 클라이언트 항목을 제거 하지 않습니다.|
|[COleClientItem::Reload](#reload)|항목을 호출한 후에 다시 로드 `ActivateAs`합니다.|
|[COleClientItem::Run](#run)|항목과 연결 된 응용 프로그램을 실행 합니다.|
|[COleClientItem::SetDrawAspect](#setdrawaspect)|렌더링에 대 한 항목의 현재 보기를 설정합니다.|
|[COleClientItem::SetExtent](#setextent)|OLE 항목의 경계 사각형을 설정합니다.|
|[COleClientItem::SetHostNames](#sethostnames)|OLE 항목을 편집할 때 서버 표시 이름을 설정 합니다.|
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 캐시 합니다.|
|[COleClientItem::SetItemRects](#setitemrects)|항목의 경계 사각형을 설정합니다.|
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|연결된 된 항목 (고급 기능)에 대 한 업데이트 모드를 설정합니다.|
|[COleClientItem::SetPrintDevice](#setprintdevice)|이 클라이언트 항목에 대 한 인쇄 대상 장치를 설정합니다.|
|[COleClientItem::UpdateLink](#updatelink)|항목의 프레젠테이션 캐시를 업데이트합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[COleClientItem::CanActivate](#canactivate)|내부 활성화 허용 되는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnChangeItemPosition](#onchangeitemposition)|항목의 위치가 변경 될 때 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|활성화 된 후 실행 취소 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|항목의 실행 취소 상태 정보를 삭제 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnGetClipRect](#ongetcliprect)|항목의 클리핑 사각형 좌표를 가져오기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnGetItemPosition](#ongetitemposition)|뷰를 기준으로 항목의 위치를 가져오기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|항목 위치에서 활성화 되 면 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnScrollBy](#onscrollby)|항목을 스크롤하여 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleClientItem::OnShowItem](#onshowitem)|OLE 항목을 표시 하기 위해 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

OLE 항목 데이터를 통합할 수 있습니다 "원활 하 게" 문서를 단일 문서를 사용자에 게 표시 되도록 서버 응용 프로그램에서 만들고 유지 관리를 나타냅니다. 결과 "복합 문서" OLE 항목을 포함 하는 문서를 구성 합니다.

OLE 항목을 포함 또는 연결 수 수 있습니다. 포함 된 경우 해당 데이터는 복합 문서의 일부로 저장 됩니다. 연결 된 경우 해당 데이터는 별도 서버 응용 프로그램에 의해 생성 된 파일의 일부로 저장 됩니다 및만 해당 파일에 대 한 링크는 복합 문서에 저장 됩니다. 모든 OLE 항목 편집을 호출 해야 하는 서버 응용 프로그램을 지정 하는 정보를 포함 합니다.

`COleClientItem` 서버 응용 프로그램에서 요청에 대 한 응답으로 호출 되는 몇 가지 재정의 가능 함수 정의 이러한 함수는 일반적으로 알림으로 작동합니다. 이렇게 하면 서버 응용 프로그램을 컨테이너 OLE 항목을 편집할 때 사용자가 변경 내용을 알리기 위해 또는 편집 중에 필요한 정보를 검색할 수 있습니다.

`COleClientItem` 사용 하 여 사용할 수는 [COleDocument](../../mfc/reference/coledocument-class.md)를 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), 또는 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 클래스입니다. 사용 하도록 `COleClientItem`클래스에서 파생 되 고 구현 합니다 [OnChange](#onchange) 컨테이너 항목에 대 한 변경에 반응 하는 방법을 정의 하는 멤버 함수. 내부 활성화를 지원 하려면 재정의 [OnGetItemPosition](#ongetitemposition) 멤버 함수입니다. 이 함수는 해당 OLE 항목의 표시 된 위치에 대 한 정보를 제공합니다.

컨테이너 인터페이스를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하세요. [컨테이너: 컨테이너를 구현](../../mfc/containers-implementing-a-container.md) 하 고 [활성화](../../mfc/activation-cpp.md)합니다.

> [!NOTE]
>  Windows SDK "개체"로 포함 및 연결 된 항목을 참조 하 고 "classes"를 선택 합니다. 항목의 형식 이 참조 "항목" 라는 용어를 사용 하 여 해당 되는 OLE 엔터티를 구분 하기 위해 C++ 개체 및 OLE 범주를 구분 하기 위해 "type" 라는 용어는 C++ 클래스입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleClientItem`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="activate"></a>  COleClientItem::Activate

대신 지정된 된 동사를 실행 하려면이 함수를 호출 [DoVerb](#doverb) 예외가 throw 될 때 고유한 처리를 수행할 수 있도록 합니다.

```
void Activate(
    LONG nVerb,
    CView* pView,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>매개 변수

*nVerb*<br/>
실행 하는 동사를 지정 합니다. 다음 중 하나일 수 있습니다.

|값|의미|기호|
|-----------|-------------|------------|
|- 0|기본 동사|OLEIVERB_PRIMARY|
|- 1|보조 동사|(None)|
|- 1|편집을 위해 표시 항목|OLEIVERB_SHOW|
|- 2|별도 창에서 항목 편집|OLEIVERB_OPEN|
|- 3|항목 숨기기|OLEIVERB_HIDE|

일반적으로-1 값은 다른 동사에 대 한 별칭입니다. 열린 편집 지원 되지 않는 경우-2는 것과 동일한 효과가-1입니다. 추가 값을 참조 하세요 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK에 있습니다.

*pView*<br/>
OLE 항목을 포함 하는 컨테이너 보기 창에 대 한 포인터 내부 활성화에 대 한 서버 응용 프로그램에서 사용 됩니다. 이 매개 변수는 컨테이너 내부 활성화를 지원 하지 않는 경우 NULL 이어야 합니다.

*lpMsg*<br/>
항목을 활성화할 수를 발생 시킨 메시지에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수로 인해 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 작성 된 경우는 [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb) 멤버 함수는 해당 `COleServerItem` 실행할 개체입니다.

기본 동사는 편집 및 0에 지정 된 경우는 *nVerb* OLE 항목을 편집할 수 있도록 매개 변수를 서버 응용 프로그램이 시작 됩니다. 컨테이너 응용 프로그램에서 내부 활성화를 지 원하는 경우 편집 가능 진행에서 합니다. 컨테이너 내부 활성화 (또는 Open 동사 지정 된 경우)를 지원 하지 않습니다 별도 창에서 서버를 시작 하 고 편집 할 수 있습니다. 컨테이너 응용 프로그램의 사용자 OLE 항목을 기본 동사에 대 한 값을가 하는 경우 일반적으로 *nVerb* 매개 변수는 사용자가 수행할 수 있는 작업을 결정 합니다. 그러나 서버에서 하나의 작업을 지 원하는 경우 걸립니다 값에 지정 된 관계 없이 해당 작업에는 *nVerb* 매개 변수입니다.

자세한 내용은 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK에 있습니다.

##  <a name="activateas"></a>  COleClientItem::ActivateAs

OLE의 개체 변환 기능을 사용 하 여 지정 된 형식의 항목 처럼 항목을 활성화 *clsidNew*합니다.

```
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,
    REFCLSID clsidOld,
    REFCLSID clsidNew);
```

### <a name="parameters"></a>매개 변수

*lpszUserType*<br/>
"Word 문서입니다."와 같은 대상 사용자 유형을 나타내는 문자열에 대 한 포인터

*clsidOld*<br/>
항목의 현재 클래스에 대 한 참조 id입니다. 클래스 ID를 나타내야 실제 개체의 형식을 저장 시에 링크 하지 않는 한 합니다. 이 경우 링크를 참조 하는 항목의 CLSID 여야 합니다. 합니다 [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md) 자동으로 해당 항목에 대 한 올바른 클래스 ID를 제공 합니다.

*clsidNew*<br/>
대상 클래스 ID에 대 한 참조

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 자동으로 호출 됩니다 [COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert)합니다. 이 일반적으로 직접 호출 되지 합니다.

##  <a name="attachdataobject"></a>  COleClientItem::AttachDataObject

초기화 하려면이 함수를 호출을 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목의 데이터에 액세스 합니다.

```
void AttachDataObject(COleDataObject& rDataObject) const;
```

### <a name="parameters"></a>매개 변수

*rDataObject*<br/>
에 대 한 참조를 `COleDataObject` OLE 항목의 데이터에 액세스할 수 있도록 초기화 될 개체입니다.

##  <a name="canactivate"></a>  COleClientItem::CanActivate

OLE 항목의 내부 활성화를 요청 하는 사용자 경우 프레임 워크에서 호출 이 함수의 반환 값에서 내부 활성화 허용 되는지 여부를 결정 합니다.

```
virtual BOOL CanActivate();
```

### <a name="return-value"></a>반환 값

내부 활성화가 허용 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

컨테이너 유효한 창에 있는 경우 내부 활성화를 허용 하는 기본 구현입니다. 수락 또는 거절 활성화 요청에 대 한 특별 한 논리를 구현 하려면이 함수를 재정의 합니다. 예를 들어 OLE 항목이 너무 작거나 현재 보이지 이면 활성화 요청을 거부할 수 있습니다.

자세한 내용은 [IOleInPlaceSite::CanInPlaceActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-caninplaceactivate) Windows SDK에 있습니다.

##  <a name="cancreatefromdata"></a>  COleClientItem::CanCreateFromData

컨테이너 응용 프로그램에서 포함 된 개체를 만들 수 있는지 여부를 확인 합니다 지정 `COleDataObject` 개체입니다.

```
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
에 대 한 포인터를 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목을 만들려는 개체입니다.

### <a name="return-value"></a>반환 값

0이 아닌 컨테이너에서 포함 된 개체를 만들 수는 `COleDataObject` 개체 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`COleDataObject` 클래스 끌어 놓기를 통해 클립보드에서 또는 포함 된 OLE 항목에서 다양 한 형식에서 데이터를 검색 하는 것에 대 한 데이터 전송에 사용 됩니다.

컨테이너 해당 붙여넣기 편집 하 고 편집 하 여 붙여넣기 명령을 사용할지 여부를 결정이 함수를 사용할 수 있습니다.

자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.

##  <a name="cancreatelinkfromdata"></a>  COleClientItem::CanCreateLinkFromData

컨테이너 응용 프로그램에서 연결 된 개체를 만들 수 있는지 여부를 확인 합니다 지정 `COleDataObject` 개체입니다.

```
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
에 대 한 포인터를 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목을 만들려는 개체입니다.

### <a name="return-value"></a>반환 값

컨테이너에서 연결된 된 개체를 만들 수 있으면 0이 아닌 값을 `COleDataObject` 개체입니다.

### <a name="remarks"></a>설명

`COleDataObject` 클래스 끌어 놓기를 통해 클립보드에서 또는 포함 된 OLE 항목에서 다양 한 형식에서 데이터를 검색 하는 것에 대 한 데이터 전송에 사용 됩니다.

컨테이너는 해당 편집 하 여 붙여넣기 및 편집 링크 붙여넣기 명령을 사용할지 여부를 결정이 함수를 사용할 수 있습니다.

자세한 내용은 문서 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md)합니다.

##  <a name="canpaste"></a>  COleClientItem::CanPaste

포함된 OLE 항목 클립보드에서 붙여 넣을 수 있는지 여부를 확인 하려면이 함수를 호출 합니다.

```
static BOOL PASCAL CanPaste();
```

### <a name="return-value"></a>반환 값

포함된 OLE 항목; 클립보드에서 붙여 넣을 수 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [OleGetClipboard](/windows/desktop/api/ole2/nf-ole2-olegetclipboard) 하 고 [OleQueryCreateFromData](/windows/desktop/api/ole2/nf-ole2-olequerycreatefromdata) Windows SDK의 합니다.

##  <a name="canpastelink"></a>  COleClientItem::CanPasteLink

연결 된 OLE 항목을 클립보드에서 붙여 넣을 수 있는지 여부를 확인 하려면이 함수를 호출 합니다.

```
static BOOL PASCAL CanPasteLink();
```

### <a name="return-value"></a>반환 값

연결된 된 OLE 항목; 클립보드에서 붙여 넣을 수 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [OleGetClipboard](/windows/desktop/api/ole2/nf-ole2-olegetclipboard) 하 고 [OleQueryLinkFromData](/windows/desktop/api/ole2/nf-ole2-olequerylinkfromdata) Windows SDK의 합니다.

##  <a name="close"></a>  COleClientItem::Close

하지만 실행 하지 않는 서버 메모리에 해당 처리기를 사용 하 여 로드 즉, 로드 된 상태로 실행 중인 상태에서 OLE 항목의 상태를 변경 하려면이 함수를 호출 합니다.

```
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```

### <a name="parameters"></a>매개 변수

*dwCloseOption*<br/>
OLE 항목 로드 된 상태로 돌아오면 어떤 상황에서 저장을 지정 하는 플래그입니다. 다음 값 중 하나일 수 있습니다.

- OLECLOSE_SAVEIFDIRTY 저장 OLE 항목입니다.

- OLECLOSE_NOSAVE OLE 항목을 저장 하지 않습니다.

- OLECLOSE_PROMPTSAVE에서 OLE 항목을 저장할 것인지 여부를 묻는 메시지를 표시 합니다.

### <a name="remarks"></a>설명

이 함수는 OLE 항목 실행 중이지 않을 때에 영향이 없습니다.

자세한 내용은 [IOleObject::Close](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-close) Windows SDK에 있습니다.

##  <a name="coleclientitem"></a>  COleClientItem::COleClientItem

생성 된 `COleClientItem` 만 생성 하는 문서 항목의 컨테이너 문서의 컬렉션에 추가 하는 개체를 C++ 개체 및 모든 OLE 초기화를 수행 하지 않습니다.

```
COleClientItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>매개 변수

*pContainerDoc*<br/>
이 항목을 포함 하는 컨테이너 문서에 대 한 포인터입니다. 이 하나일 수 있습니다 [COleDocument](../../mfc/reference/coledocument-class.md) 파생 합니다.

### <a name="remarks"></a>설명

NULL 포인터를 전달 하는 경우에 컨테이너 문서에 추가 되지 않습니다 이루어집니다. 명시적으로 호출 해야 합니다 [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)합니다.

OLE 항목을 사용 하기 전에 생성 멤버 함수는 다음 중 하나를 호출 해야 합니다.

- [CreateFromClipboard](#createfromclipboard)

- [CreateFromData](#createfromdata)

- [CreateFromFile](#createfromfile)

- [CreateStaticFromClipboard](#createstaticfromclipboard)

- [CreateStaticFromData](#createstaticfromdata)

- [CreateLinkFromClipboard](#createlinkfromclipboard)

- [CreateLinkFromData](#createlinkfromdata)

- [CreateLinkFromFile](#createlinkfromfile)

- [CreateNewItem](#createnewitem)

- [CreateCloneFrom](#createclonefrom)

##  <a name="convertto"></a>  COleClientItem::ConvertTo

이 멤버 함수를 호출 하 여 지정 된 형식 항목 변환 *clsidNew*합니다.

```
virtual BOOL ConvertTo(REFCLSID clsidNew);
```

### <a name="parameters"></a>매개 변수

*clsidNew*<br/>
클래스의 ID는 대상 형식입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 자동으로 호출 됩니다 [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)합니다. 메서드를 직접 호출 하는 데 필요한 것입니다.

##  <a name="copytoclipboard"></a>  COleClientItem::CopyToClipboard

OLE 항목을 클립보드에 복사 하려면이 함수를 호출 합니다.

```
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>매개 변수

*bIncludeLink*<br/>
링크 정보를 붙여 넣을 수 있습니다; 연결된 된 항목 허용 클립보드에 복사 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

일반적으로 편집 메뉴에서 복사 또는 잘라내기 명령에 대 한 메시지 처리기를 작성 하는 경우이 함수를 호출 합니다. 복사 또는 잘라내기 명령 구현 하려는 경우 컨테이너 응용 프로그램에서 선택 항목을 구현 해야 합니다.

자세한 내용은 [OleSetClipboard](/windows/desktop/api/ole2/nf-ole2-olesetclipboard) Windows SDK에 있습니다.

##  <a name="createclonefrom"></a>  COleClientItem::CreateCloneFrom

지정된 된 OLE 항목의 복사본을 만드는이 함수를 호출 합니다.

```
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```

### <a name="parameters"></a>매개 변수

*pSrcItem*<br/>
중복 될 OLE 항목에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

복사본을 소스 항목 동일합니다. 실행 취소 작업을 지원 하도록이 함수를 사용할 수 있습니다.

##  <a name="createfromclipboard"></a>  COleClientItem::CreateFromClipboard

클립보드의 내용에서 포함 된 항목을 만들려면이 함수를 호출 합니다.

```
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

일반적으로 편집 메뉴에서 붙여넣기 명령에 대 한 메시지 처리기에서이 함수를 호출 합니다. (경우에 붙여넣기 명령을 프레임 워크에서 사용할 수는 [CanPaste](#canpaste) 멤버 함수는 0이 아닌 반환 합니다.)

자세한 내용은 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) 하 고 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 합니다.

##  <a name="createfromdata"></a>  COleClientItem::CreateFromData

포함 된 항목을 만드는이 함수 호출을 `COleDataObject` 개체입니다.

```
BOOL CreateFromData(
    COleDataObject* pDataObject,
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
에 대 한 포인터를 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목을 만들려는 개체입니다.

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

클립보드 또는 끌어서 놓기 작업에서 붙여넣기 등의 데이터 전송 작업을 제공 `COleDataObject` 서버 응용 프로그램에서 제공 하는 정보가 들어 있는 개체입니다. 재정의 일반적으로 [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop)합니다.

자세한 내용은 [OleCreateFromData](/windows/desktop/api/ole2/nf-ole2-olecreatefromdata), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

##  <a name="createfromfile"></a>  COleClientItem::CreateFromFile

파일에서 포함 된 OLE 항목을 만들려면이 함수를 호출 합니다.

```
BOOL CreateFromFile(
    LPCTSTR lpszFileName,
    REFCLSID clsid = CLSID_NULL,
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
OLE 항목을 만들려는 파일의 이름에 대 한 포인터입니다.

*clsid*<br/>
나중에 사용하기 위해 예약되어 있습니다.

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출 하는 프레임 워크 [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem) 파일 단추에서 만들기를 선택 하면 사용자 개체 삽입 대화 상자에서 확인을 선택 합니다.

자세한 내용은 [OleCreateFromFile](/windows/desktop/api/ole/nf-ole-olecreatefromfile), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

##  <a name="createlinkfromclipboard"></a>  COleClientItem::CreateLinkFromClipboard

클립보드의 내용에서 연결 된 항목을 만드는이 함수를 호출 합니다.

```
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

일반적으로 편집 메뉴에서 연결 하 여 붙여넣기 명령에 대 한 메시지 처리기에서이 함수를 호출 합니다. (연결 하 여 붙여넣기 명령이의 기본 구현에서 사용 되는지 [COleDocument](../../mfc/reference/coledocument-class.md) 클립보드에 연결할 수 있는 OLE 항목을 포함 하는 경우입니다.)

자세한 내용은 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) 하 고 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 합니다.

##  <a name="createlinkfromdata"></a>  COleClientItem::CreateLinkFromData

연결 된 항목을 만들려면이 함수를 호출 하는 `COleDataObject` 개체입니다.

```
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
에 대 한 포인터를 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목을 만들려는 개체입니다.

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용자 링크를 나타내는 경우 놓기 작업 중이 만들도록 호출 합니다. 편집 붙여넣기 명령을 처리 하도록 데도 수 있습니다. 프레임 워크에서 호출 됩니다 `COleClientItem::CreateLinkFromClipboard` 고 [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) 링크 옵션을 선택한 경우.

자세한 내용은 [OleCreateLinkFromData](/windows/desktop/api/ole2/nf-ole2-olecreatelinkfromdata), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

##  <a name="createlinkfromfile"></a>  COleClientItem::CreateLinkFromFile

파일에서 연결된 된 OLE 항목을 만들려면이 함수를 호출 합니다.

```
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
OLE 항목을 만들려는 파일의 이름에 대 한 포인터입니다.

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

프레임 워크 만들기 파일 단추에서 선택한 링크 확인란이 하는 경우 사용자 개체 삽입 대화 상자에서 확인을 선택 하는 경우이 함수를 호출 합니다. 호출한 [COleInsertDialog::CreateItem](../../mfc/reference/coleinsertdialog-class.md#createitem)합니다.

자세한 내용은 [OleCreateLinkToFile](/windows/desktop/api/ole2/nf-ole2-olecreatelinktofile), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

##  <a name="createnewitem"></a>  COleClientItem::CreateNewItem

포함 된 항목을 만들려면이 함수를 호출 이 함수는 사용자가 OLE 항목을 만들 수 있도록 서버 응용 프로그램을 시작 합니다.

```
BOOL CreateNewItem(
    REFCLSID clsid,
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
만들 OLE 항목의 형식을 고유 하 게 식별 하는 ID입니다.

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

새로 만들기 단추를 선택한 경우 사용자 개체 삽입 대화 상자에서 확인을 선택 하는 경우이 함수를 호출 하는 프레임 워크입니다.

자세한 내용은 [OleCreate](/windows/desktop/api/ole/nf-ole-olecreate), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

##  <a name="createstaticfromclipboard"></a>  COleClientItem::CreateStaticFromClipboard

클립보드의 내용에서 정적 항목을 만드는이 함수를 호출 합니다.

```
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

프레젠테이션 데이터는 있지만 네이티브 데이터가 아니라; 정적 항목 포함 결과적으로 편집할 수 없습니다. 하는 경우 일반적으로이 함수를 호출 합니다 [CreateFromClipboard](#createfromclipboard) 멤버 함수가 실패 합니다.

자세한 내용은 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) 하 고 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows SDK의 합니다.

##  <a name="createstaticfromdata"></a>  COleClientItem::CreateStaticFromData

이 함수는 정적 항목 만들기를 호출을 `COleDataObject` 개체입니다.

```
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,
    OLERENDER render = OLERENDER_DRAW,
    CLIPFORMAT cfFormat = 0,
    LPFORMATETC lpFormatEtc = NULL);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
에 대 한 포인터를 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE 항목을 만들려는 개체입니다.

*render*<br/>
서버에서 OLE 항목을 렌더링 되는 방식을 지정 하는 플래그입니다. 가능한 값을 참조 하세요 [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender) Windows SDK에 있습니다.

*cfFormat*<br/>
OLE 항목을 만들 때 캐시할 클립보드 데이터 형식을 지정 합니다.

*lpFormatEtc*<br/>
에 대 한 포인터를 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) 경우에 사용 되는 구조 *렌더링* OLERENDER_FORMAT 인지 OLERENDER_DRAW 합니다. 이 매개 변수 값을 제공 하 여 지정 된 클립보드 형식 이외의 추가 형식 정보를 지정 하려는 경우에 *cfFormat*합니다. 다른 필드에 대 한 기본 값이 사용은이 매개 변수를 생략 하면는 `FORMATETC` 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

프레젠테이션 데이터는 있지만 네이티브 데이터가 아니라; 정적 항목 포함 결과적으로 편집할 수 있습니다. 이것은 기본적으로 동일 [CreateStaticFromClipboard](#createstaticfromclipboard) 제외 하 고 있는 임의의에서 정적 항목을 만들 수 있습니다 `COleDataObject`클립보드에서 뿐 아니라, 합니다.

레지스트리에 [COlePasteSpecialDialog::CreateItem](../../mfc/reference/colepastespecialdialog-class.md#createitem) 정적 선택 된 경우.

자세한 내용은 [OleCreateStaticFromData](/windows/desktop/api/ole2/nf-ole2-olecreatestaticfromdata), [OLERENDER](/windows/desktop/api/oleidl/ne-oleidl-tagolerender), 및 [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) Windows sdk에서입니다.

##  <a name="deactivate"></a>  COleClientItem::Deactivate

OLE 항목을 비활성화 하 고 연결 된 리소스를 해제 하려면이 함수를 호출 합니다.

```
void Deactivate();
```

### <a name="remarks"></a>설명

일반적으로 항목의 경계 외부의 클라이언트 영역에서 마우스를 클릭할 때 전체 활성 OLE 항목을 비활성화 합니다. OLE 항목을 비활성화 실행 취소 상태로 호출할 수 없도록 취소는 참고 합니다 [ReactivateAndUndo](#reactivateandundo) 멤버 함수.

응용 프로그램 실행 취소를 지 원하는 경우 호출 하지 마세요 `Deactivate`대신 호출 [DeactivateUI](#deactivateui)합니다.

자세한 내용은 [IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) Windows SDK에 있습니다.

##  <a name="deactivateui"></a>  COleClientItem::DeactivateUI

사용자는 내부에서 활성화 된 항목을 비활성화 하는 경우이 함수를 호출 합니다.

```
void DeactivateUI();
```

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤 숨기기, 원래 상태로 복원 합니다.

이 함수는 항목에 대 한 실행 취소 상태 정보를 플러시하지 않습니다. 정보가 유지 됩니다 있도록 [ReactivateAndUndo](#reactivateandundo) 있습니다 나중에 사용할 서버 응용 프로그램을 실행 취소 명령을 실행 하려면 항목을 비활성화 한 후에 즉시 컨테이너의 실행 취소 명령이 선택 된 경우.

자세한 내용은 [IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) Windows SDK에 있습니다.

##  <a name="delete"></a>  COleClientItem::Delete

OLE 항목이 컨테이너 문서에서 삭제 하려면이 함수를 호출 합니다.

```
void Delete(BOOL bAutoDelete = TRUE);
```

### <a name="parameters"></a>매개 변수

*bAutoDelete*<br/>
문서에서 제거할 항목 인지 여부를 지정 합니다.

### <a name="remarks"></a>설명

이 함수를 호출 합니다 [릴리스](#release) 차례로 삭제 하는 멤버 함수는 C++ 는 항목을 영구적으로 OLE 항목을 문서에서 제거 하는 것에 대 한 개체입니다. OLE 항목을 포함 하는 경우에 항목에 대 한 기본 데이터가 삭제 됩니다. 실행 중인 서버에 항상 닫기 따라서 항목 열기 링크 이면이 함수를 닫습니다.

##  <a name="dodragdrop"></a>  COleClientItem::DoDragDrop

호출 된 `DoDragDrop` 멤버 함수를 끌어서 놓기 작업을 수행 합니다.

```
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>매개 변수

*lpItemRect*<br/>
클라이언트 좌표 (픽셀) 화면에서 항목의 사각형입니다.

*ptOffset*<br/>
오프셋 *lpItemRect* 끌기 시 마우스 위치가 있습니다.

*bIncludeLink*<br/>
이 TRUE가 링크를 설정 데이터를 클립보드에 복사 해야 합니다. 서버 응용 프로그램 링크를 지원 하지 않는 경우 FALSE로 설정 합니다.

*dwEffects*<br/>
끌기 소스가 끌기 작업에서 허용 하는 효과 확인 합니다.

*lpRectStartDrag*<br/>
끌기 실제로 시작 위치를 정의 하는 사각형에 대 한 포인터입니다. 자세한 내용은 아래 설명 부분을 참조하십시오.

### <a name="return-value"></a>반환 값

DROPEFFECT 값입니다. DROPEFFECT_MOVE 인 경우 원래의 데이터 제거 해야 합니다.

### <a name="remarks"></a>설명

끌어서 놓기 작업이 즉시 시작 되지 않습니다. 마우스 커서가 지정 된 사각형에서 벗어날 때까지 기다렸다가 *lpRectStartDrag* 또는 지정 된 기간 (밀리초)이 경과한 때까지 합니다. 하는 경우 *lpRectStartDrag* 가 null 인 경우 사각형의 크기는 1 픽셀입니다.

레지스트리 키 설정 지연 시간 지정 됩니다. 호출 하 여 지연 시간을 변경할 수 있습니다 [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) 하거나 [cwinapp:: Writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)합니다. 지연 시간을 지정 하지 않으면 기본값은 200 시간 (밀리초)이 사용 됩니다. 끌어서 지연 시간을 다음과 같이 저장 됩니다.

- Windows NT 끌어서 지연 시간 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay에 저장 됩니다.

- Windows 3.x 끌어서 지연 시간 WIN에 저장 됩니다. INI 파일 [Windows} 섹션입니다.

- Windows 95/98 끌어서 지연 시간 WIN의 캐시 된 버전에 저장 됩니다. INI 합니다.

지연 정보 중 하나는 레지스트리에 저장 된 방법에 대 한 자세한 내용은 끌어에 대 한 또는 합니다. INI 파일을 참조 하세요 [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) Windows SDK에 있습니다.

##  <a name="doverb"></a>  COleClientItem::DoVerb

호출 `DoVerb` 지정된 된 동사를 실행 합니다.

```
virtual BOOL DoVerb(
    LONG nVerb,
    CView* pView,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>매개 변수

*nVerb*<br/>
실행 하는 동사를 지정 합니다. 다음 중 하나를 포함할 수 있습니다.

|값|의미|기호|
|-----------|-------------|------------|
|- 0|기본 동사|OLEIVERB_PRIMARY|
|- 1|보조 동사|(None)|
|- 1|편집을 위해 표시 항목|OLEIVERB_SHOW|
|- 2|별도 창에서 항목 편집|OLEIVERB_OPEN|
|- 3|항목 숨기기|OLEIVERB_HIDE|

일반적으로-1 값은 다른 동사에 대 한 별칭입니다. 열린 편집 지원 되지 않는 경우-2는 것과 동일한 효과가-1입니다. 추가 값을 참조 하세요 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK에 있습니다.

*pView*<br/>
보기 창에 대 한 포인터 내부 활성화에 대 한 서버에서 사용 됩니다. 이 매개 변수는 컨테이너 응용 프로그램이 내부 활성화를 허용 하지 않는 경우 NULL 이어야 합니다.

*lpMsg*<br/>
항목을 활성화할 수를 발생 시킨 메시지에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

0이 아닌 동사 성공적으로 실행 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출 합니다 [활성화](#activate) 동사를 실행 하는 멤버 함수입니다. 또한 예외를 catch 및 throw 되는 경우 사용자에 게 메시지 상자를 표시 합니다.

기본 동사는 편집 및 0에 지정 된 경우는 *nVerb* OLE 항목을 편집할 수 있도록 매개 변수를 서버 응용 프로그램이 시작 됩니다. 컨테이너 응용 프로그램에서 내부 활성화를 지 원하는 경우 편집 가능 진행에서 합니다. 컨테이너 내부 활성화 (또는 Open 동사 지정 된 경우)를 지원 하지 않습니다 별도 창에서 서버를 시작 하 고 편집 할 수 있습니다. 컨테이너 응용 프로그램의 사용자 OLE 항목을 기본 동사에 대 한 값을가 하는 경우 일반적으로 *nVerb* 매개 변수는 사용자가 수행할 수 있는 작업을 결정 합니다. 그러나 서버에서 하나의 작업을 지 원하는 경우 걸립니다 값에 지정 된 관계 없이 해당 작업에는 *nVerb* 매개 변수입니다.

##  <a name="draw"></a>  COleClientItem::Draw

지정 된 디바이스 컨텍스트를 사용 하 여 지정된 된 경계 사각형에 OLE 항목을 그릴이 함수를 호출 합니다.

```
BOOL Draw(
    CDC* pDC,
    LPCRECT lpBounds,
    DVASPECT nDrawAspect = (DVASPECT)-1);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
에 대 한 포인터를 [CDC](../../mfc/reference/cdc-class.md) OLE 항목을 그리는 데 사용 되는 개체입니다.

*lpBounds*<br/>
에 대 한 포인터를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 `RECT` (논리 단위는 장치 컨텍스트에 의해 결정)에서 OLE 항목을 그릴 경계 사각형을 정의 하는 구조입니다.

*nDrawAspect*<br/>
OLE의 모양을 항목, 즉, 표시 하는 방법을 지정 합니다. 하는 경우 *nDrawAspect* 가-1을 사용 하 여 설정 마지막 측면 [SetDrawAspect](#setdrawaspect) 사용 됩니다. 이 플래그에 대 한 가능한 값에 대 한 자세한 내용은 참조 하세요. [SetDrawAspect](#setdrawaspect)합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

함수에 의해 만들어진 OLE 항목의 메타 파일 표시를 사용할 수는 [OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw) 멤버 함수 `COleServerItem`합니다.

일반적으로 사용 `Draw` 화면 표시를 위해으로 화면 장치 컨텍스트를 전달 *pDC*합니다. 이 경우 처음 두 매개 변수를 지정 해야 합니다.

합니다 *lpBounds* 매개 변수 (기준으로 현재 매핑 모드) 대상 장치 컨텍스트의 사각형을 식별 합니다. 렌더링 그림 확장 될 수 있습니다 및 표시 된 보기와 인쇄 된 최종 이미지 간에 크기를 조정 하는 뷰를 적용 하려면 컨테이너 응용 프로그램에서 사용할 수 있습니다.

자세한 내용은 [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw) Windows SDK에 있습니다.

##  <a name="getactiveview"></a>  COleClientItem::GetActiveView

항목에 내부 활성화 하는 뷰를 반환 합니다.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>반환 값

뷰에 대 한 포인터 그렇지 않으면 항목이 내부 활성화 되지 않은 경우 NULL입니다.

##  <a name="getcachedextent"></a>  COleClientItem::GetCachedExtent

OLE 항목의 크기를 검색 하려면이 함수를 호출 합니다.

```
BOOL GetCachedExtent(
    LPSIZE lpSize,
    DVASPECT nDrawAspect = (DVASPECT)-1);
```

### <a name="parameters"></a>매개 변수

*lpSize*<br/>
에 대 한 포인터를 `SIZE` 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 크기 정보를 받게 될 개체입니다.

*nDrawAspect*<br/>
검색할 해당 경계는 해당 OLE 항목의 모양을 지정 합니다. 가능한 값을 참조 하세요 [SetDrawAspect](#setdrawaspect)합니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 OLE 항목을이 비어 있으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 동일한 정보를 제공 [GetExtent](#getextent)합니다. 호출할 수 있습니다 `GetCachedExtent` 정보를 가져올 익스텐트 처리 하는 동안 다른 OLE 처리기와 같은 [OnChange](#onchange)합니다. 차원은 MM_HIMETRIC 단위에서입니다.

이것이 가능 때문에 `GetCachedExtent` 사용 합니다 [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2) 사용 하는 것이 아니라 인터페이스는 [IOleObject](/windows/desktop/api/oleidl/nn-oleidl-ioleobject) 를이 항목의 범위를 가져오는 인터페이스입니다. 합니다 `IViewObject2` COM 개체에 대 한 이전 호출에서 사용 하는 범위 정보를 캐시 [IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw)합니다.

자세한 내용은 [IViewObject2::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-iviewobject2-getextent) Windows SDK에 있습니다.

##  <a name="getclassid"></a>  COleClientItem::GetClassID

가 가리키는 메모리에 항목의 클래스 ID를 반환 *pClassID*합니다.

```
void GetClassID(CLSID* pClassID) const;
```

### <a name="parameters"></a>매개 변수

*pClassID*<br/>
형식의 식별자에 대 한 포인터 [CLSID](/windows/desktop/com/clsid-key-hklm) 클래스 ID를 검색 CLSID에 대 한 내용은 Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

클래스 ID는 고유 하 게 항목을 편집 하는 응용 프로그램을 식별 하는 128 비트 숫자입니다.

자세한 내용은 [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK에 있습니다.

##  <a name="getclipboarddata"></a>  COleClientItem::GetClipboardData

가져오려면이 함수를 호출 하는 `COleDataSource` 개체를 호출 하 여 클립보드에 배치 됩니다 모든 데이터를 포함 하는 [CopyToClipboard](#copytoclipboard) 멤버 함수입니다.

```
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>매개 변수

*pDataSource*<br/>
에 대 한 포인터를 [COleDataSource](../../mfc/reference/coledatasource-class.md) OLE 항목에 포함 된 데이터를 받게 될 개체입니다.

*bIncludeLink*<br/>
데이터 연결;에 포함 해야 하면 TRUE 그렇지 않으면 FALSE입니다.

*lpOffset*<br/>
픽셀에서 개체의 원점부터 마우스 커서의 오프셋입니다.

*lpSize*<br/>
크기 (픽셀 단위)는 개체입니다.

### <a name="remarks"></a>설명

`GetClipboardData` 기본 구현으로 이라고 [OnGetClipboardData](#ongetclipboarddata)합니다. 재정의 `OnGetClipboardData` 데이터 형식에서 제공 하는 것 외에도 제공 하려는 경우에 `CopyToClipboard`합니다. 해당 형식에 배치 합니다 `COleDataSource` 전이나 호출한 후 개체 `CopyToClipboard`, 전달를 `COleDataSource` 개체를 [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) 함수. 예를 들어, 클립보드에 함께 해당 컨테이너 문서의 OLE 항목의 위치를 하려는 경우 해당 정보를 전달 하기 위한 고유한 형식을 정의 하는 그 안에 배치 합니다 `COleDataSource` 호출 하기 전에 `CopyToClipboard`입니다.

##  <a name="getdocument"></a>  COleClientItem::GetDocument

OLE 항목을 포함 하는 문서에 대 한 포인터를 가져오려면이 함수를 호출 합니다.

```
COleDocument* GetDocument() const;
```

### <a name="return-value"></a>반환 값

OLE 항목을 포함 하는 문서에 대 한 포인터입니다. 항목이 문서의 일부가 아닌 경우 NULL입니다.

### <a name="remarks"></a>설명

이 포인터에 대 한 액세스를 허용 합니다 `COleDocument` 인수로 전달 하는 개체는 `COleClientItem` 생성자입니다.

##  <a name="getdrawaspect"></a>  COleClientItem::GetDrawAspect

호출 된 `GetDrawAspect` 현재 "모양" 또는 항목의 보기를 결정 하는 멤버 함수입니다.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>반환 값

값에 대 한 참조에 나열 된 DVASPECT 열거형에서 값을 [SetDrawAspect](#setdrawaspect)합니다.

### <a name="remarks"></a>설명

측면에 항목을 렌더링 하는 하는 방법을 지정 합니다.

##  <a name="getextent"></a>  COleClientItem::GetExtent

OLE 항목의 크기를 검색 하려면이 함수를 호출 합니다.

```
BOOL GetExtent(
    LPSIZE lpSize,
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```

### <a name="parameters"></a>매개 변수

*lpSize*<br/>
에 대 한 포인터를 `SIZE` 구조 또는 `CSize` 크기 정보를 받게 될 개체입니다.

*nDrawAspect*<br/>
검색할 해당 경계는 해당 OLE 항목의 모양을 지정 합니다. 가능한 값을 참조 하세요 [SetDrawAspect](#setdrawaspect)합니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 OLE 항목을이 비어 있으면 0입니다.

### <a name="remarks"></a>설명

이 함수로 인해 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 작성 된 경우는 [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent) 멤버 함수는 해당 `COleServerItem` 호출할 개체입니다. 검색된 크기를 마지막으로 설정한 크기와에서 다를 수 있습니다 하는 [SetExtent](#setextent) 멤버 함수, 지정 된 크기 `SetExtent` 제안으로 처리 됩니다. 차원은 MM_HIMETRIC 단위에서입니다.

> [!NOTE]
>  호출 하지 마세요 `GetExtent` 는 OLE 처리기를 처리 하는 동안 같은 [OnChange](#onchange)합니다. 호출 [GetCachedExtent](#getcachedextent) 대신 합니다.

자세한 내용은 [IOleObject::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getextent) Windows SDK에 있습니다.

##  <a name="geticonfromregistry"></a>  COleClientItem::GetIconFromRegistry

특정 CLSID의 서버에 연결 된 아이콘 리소스에 대 한 핸들을 검색 하려면이 멤버 함수를 호출 합니다.

```
HICON GetIconFromRegistry() const;

static HICON GetIconFromRegistry(CLSID& clsid);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
아이콘을 사용 하 여 연결 된 서버에 대 한 CLSID에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

올바른 아이콘 리소스에 대 한 핸들 또는 서버의 아이콘 또는 기본 아이콘을 찾을 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 서버 시작 않거나 서버가 이미 실행 중인 경우에 동적으로 아이콘을 가져옵니다. 대신이 멤버 함수 서버의 실행 가능 이미지 열리고 서버에 연결 된 등록 된 고정 아이콘을 검색 합니다.

##  <a name="geticonicmetafile"></a>  COleClientItem::GetIconicMetafile

항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 검색 합니다.

```
HGLOBAL GetIconicMetafile();
```

### <a name="return-value"></a>반환 값

성공할 경우 메타 파일에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

현재 아이콘이 없는 경우에 기본 아이콘이 반환 됩니다. 이 MFC/OLE 대화 상자에서 자동으로 호출 되 고는 직접 호출 되지 않습니다.

이 함수 호출 [SetIconicMetafile](#seticonicmetafile) 나중에 사용할 메타 파일을 캐시 합니다.

##  <a name="getinplacewindow"></a>  COleClientItem::GetInPlaceWindow

호출 된 `GetInPlaceWindow` 멤버 함수 내부 편집에 대 한 항목에 열려 있는 창에 대 한 포인터를 가져오려고 합니다.

```
CWnd* GetInPlaceWindow();
```

### <a name="return-value"></a>반환 값

항목의 전체 편집 창에 대 한 포인터 항목이 활성화 되지 않은 경우 또는 해당 서버를 사용할 수 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 함수는 내부 활성화 된 항목에 대해서만 호출 되어야 합니다.

##  <a name="getitemstate"></a>  COleClientItem::GetItemState

OLE 항목의 현재 상태를 가져오려면이 함수를 호출 합니다.

```
UINT GetItemState() const;
```

### <a name="return-value"></a>반환 값

A `COleClientItem::ItemState` 열거형 값 중 하나일 수 있습니다: `emptyState`를 `loadedState`, `openState`를 `activeState`, `activeUIState`합니다. 이러한 상태에 대 한 자세한 문서를 참고 [컨테이너: 클라이언트 항목 상태](../../mfc/containers-client-item-states.md)합니다.

### <a name="remarks"></a>설명

OLE 항목의 상태가 변경 될 때 알림을 받으려면를 사용 합니다 [OnChange](#onchange) 멤버 함수입니다.

자세한 내용은 문서를 참조 하세요. [컨테이너: 클라이언트 항목 상태](../../mfc/containers-client-item-states.md)합니다.

##  <a name="getlaststatus"></a>  COleClientItem::GetLastStatus

마지막 OLE 작업의 상태 코드를 반환합니다.

```
SCODE GetLastStatus() const;
```

### <a name="return-value"></a>반환 값

SCODE 값입니다.

### <a name="remarks"></a>설명

NULL을 반환 하는 함수는 부울 값 FALSE 또는 다른 멤버를 반환 하는 멤버 함수에 대 한 `GetLastStatus` 자세한 오류 정보를 반환 합니다. 대부분의 OLE 멤버 함수 보다 심각한 오류에 대 한 예외를 throw 하에 유의 합니다. SCODE 해석에 특정 정보를 마지막으로 SCODE 값을 반환 하는 기본 OLE 호출에 따라 달라 집니다.

SCODE에 대 한 자세한 내용은 참조 하세요. [COM 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) Windows SDK 설명서의 합니다.

##  <a name="getlinkupdateoptions"></a>  COleClientItem::GetLinkUpdateOptions

OLE 항목에 대 한 연결 업데이트 옵션의 현재 값을 가져오려면이 함수를 호출 합니다.

```
OLEUPDATE GetLinkUpdateOptions();
```

### <a name="return-value"></a>반환 값

다음 값 중 하나입니다.

- OLEUPDATE_ALWAYS 가능 하면 연결 된 항목을 업데이트 합니다. 이 옵션은 연결 대화 상자에서 자동 링크 업데이트 라디오 단추를 지원 합니다.

- OLEUPDATE_ONCALL 컨테이너 응용 프로그램의 요청에만 연결 된 항목을 업데이트 (때 합니다 [UpdateLink](#updatelink) 멤버 함수가 호출 됩니다). 이 옵션은 연결 대화 상자에서 수동 링크 업데이트 라디오 단추를 지원 합니다.

### <a name="remarks"></a>설명

이 작업은 고급 작업입니다.

이 함수는 자동으로 호출 합니다 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) 클래스입니다.

자세한 내용은 [IOleLink::GetUpdateOptions](/windows/desktop/api/oleidl/nf-oleidl-iolelink-getupdateoptions) Windows SDK에 있습니다.

##  <a name="gettype"></a>  COleClientItem::GetType

OLE 항목을 포함 또는 연결 하는 여부 또는 static을 결정 하는이 함수를 호출 합니다.

```
OLE_OBJTYPE GetType() const;
```

### <a name="return-value"></a>반환 값

다음 값 중 하나를 사용 하 여 부호 없는 정수:

- OT_LINK OLE 항목에는 링크입니다.

- OT_EMBEDDED OLE 항목이 포함 되어 있습니다.

- OT_STATIC OLE 항목은 정적, 즉, 네이티브가 아닌 데이터 프레젠테이션 데이터만 포함 하 고 편집할 수 없습니다.

##  <a name="getusertype"></a>  COleClientItem::GetUserType

"Word 문서입니다."와 같은 OLE 항목의 형식을 설명 하는 사용자에 게 표시 되는 문자열을 가져오려면이 함수를 호출 합니다.

```
void GetUserType(
    USERCLASSTYPE nUserClassType,
    CString& rString);
```

### <a name="parameters"></a>매개 변수

*nUserClassType*<br/>
OLE 항목의 형식을 설명 하는 문자열의 원하는 값을 나타내는 값입니다. 이 다음 값 중 하나가 있습니다.

- USERCLASSTYPE_FULL 전체 이름을 사용자에 게 표시 합니다.

- USERCLASSTYPE_SHORT 짧은 이름 (최대 15 자) 팝업 메뉴 및 연결 편집 대화 상자에 사용 합니다.

- 클래스를 서비스 응용 프로그램의 USERCLASSTYPE_APPNAME 이름입니다.

*rString*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) OLE 항목의 형식을 설명 하는 문자열을 반환할 개체입니다.

### <a name="remarks"></a>설명

이 항목은 시스템 등록 데이터베이스에 항목 경우가 많습니다.

전체 형식 이름을 요청 하지만 사용할 수 없는 경우 짧은 이름은 대신 사용 됩니다. OLE 항목의 형식에 대 한 항목이 등록 데이터베이스에 없거나 OLE 항목의 형식에 등록 된 사용자가 없는 경우 다음 사용자 형식에 현재 저장 된 경우 OLE 항목이 사용 됩니다. 해당 사용자 형식 이름의 빈 문자열인 경우 "알 수 없는 개체" 사용 됩니다.

자세한 내용은 [IOleObject::GetUserType](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getusertype) Windows SDK에 있습니다.

##  <a name="isinplaceactive"></a>  COleClientItem::IsInPlaceActive

OLE 항목의 전체 활성 인지 여부를 확인 하려면이 함수를 호출 합니다.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>반환 값

OLE 항목이 전체 활성; 이면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

항목 위치에서 편집 되는 여부에 따라 다른 논리를 실행 하는 일반적인 경우 함수는 현재 항목 상태가 같을 인지 확인 합니다 `activeState` 또는 `activeUIState`합니다.

##  <a name="islinkuptodate"></a>  COleClientItem::IsLinkUpToDate

OLE 항목이 최신 상태 인지 여부를 확인 하려면이 함수를 호출 합니다.

```
BOOL IsLinkUpToDate() const;
```

### <a name="return-value"></a>반환 값

OLE 항목이 최신; 이면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

연결 된 항목을 원본 문서에 업데이트 된 경우 만료 될 수 있습니다. 마찬가지로 포함 된 항목에 대 한 링크를 포함 하는 만료 될 수 있습니다. 함수는 해당 OLE 항목의 재귀 확인을 수행합니다. OLE 항목을 최신 인지 확인으로 실제로 업데이트를 수행할 때 비용이 많이 들 수 note 합니다.

이 자동으로 호출 되는 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md) 구현 합니다.

자세한 내용은 [IOleObject::IsUpToDate](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-isuptodate) Windows SDK에 있습니다.

##  <a name="ismodified"></a>  COleClientItem::IsModified

OLE 항목 인지 더티 (마지막으로 저장 된 이후 수정)이이 함수를 호출 합니다.

```
BOOL IsModified() const;
```

### <a name="return-value"></a>반환 값

OLE 항목이 더티; 이면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [IPersistStorage::IsDirty](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-isdirty) Windows SDK에 있습니다.

##  <a name="isopen"></a>  COleClientItem::IsOpen

OLE 항목을 열어 하는지 여부를 확인 하려면이 함수를 호출 합니다. 즉, 별도 창에서 실행 중인 서버 응용 프로그램 인스턴스에서 열립니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>반환 값

OLE 항목이 열려 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

해칭 패턴을 사용 하 여 개체를 그릴 때를 결정 하는 것이 됩니다. 열려 있는 개체에 개체를 기반으로 그린 빗살 무늬가 있어야 합니다. 사용할 수는 [CRectTracker](../../mfc/reference/crecttracker-class.md) 이 작업을 수행 하는 개체입니다.

##  <a name="isrunning"></a>  COleClientItem::IsRunning

OLE 항목을 실행 하는지 여부를 확인 하려면이 함수를 호출 합니다. 즉, 항목 인지 서버 응용 프로그램에서 실행 되 고 로드 합니다.

```
BOOL IsRunning() const;
```

### <a name="return-value"></a>반환 값

OLE 항목을 실행 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 [OleIsRunning](/windows/desktop/api/ole2/nf-ole2-oleisrunning) Windows SDK에 있습니다.

##  <a name="onactivate"></a>  COleClientItem::OnActivate

바로 활성화 된 위치에서 항목에 알리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnActivate();
```

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램에서 해당 사용자 인터페이스 설치 되어 있는지를 나타내는 것이 아니라 서버 실행 중임을 나타내는 라고 하는 참고 합니다. 이 시점에서 개체를 활성 사용자 인터페이스가 없는 (아닙니다 `activeUIState`). 해당 메뉴 또는 도구 모음에는 설치 되지 않았습니다. 합니다 [OnActivateUI](#onactivateui) 경우 멤버 함수를 호출 합니다.

기본 구현 호출 합니다 [OnChange](#onchange) OLE_CHANGEDSTATE 매개 변수로 사용 하 여 멤버 함수입니다. 항목에 내부 활성화 되 면 사용자 지정 처리를 수행 하려면이 함수를 재정의 합니다.

##  <a name="onactivateui"></a>  COleClientItem::OnActivateUI

프레임 워크 호출 `OnActivateUI` 개체 활성 UI 상태로 입력 하는 경우.

```
virtual void OnActivateUI();
```

### <a name="remarks"></a>설명

개체는 이제 해당 도구 모음 및 메뉴에 설치 됩니다.

기본 구현은 나중에 서버의 HWND를 기억 `GetServerWindow` 호출 합니다.

##  <a name="onchange"></a>  COleClientItem::OnChange

사용자 수정, 저장, 또는 OLE 항목을 닫을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnChange(
    OLE_NOTIFICATION nCode,
    DWORD dwParam);
```

### <a name="parameters"></a>매개 변수

*nCode*<br/>
이 항목 변경 하는 이유는 서버. 다음 값 중 하나일 수 있습니다.

- OLE_CHANGED OLE 항목의 모양 변경 되었습니다.

- OLE_SAVED OLE 항목 저장 되었습니다.

- OLE_CLOSED OLE 항목 종료 되었습니다.

- OLE_CHANGED_STATE OLE 항목은 다른 한 상태에서 변경 되었습니다.

*dwParam*<br/>
하는 경우 *nCode* OLE_SAVED 인지 OLE_CLOSED,이 매개 변수는 없습니다. 하는 경우 *nCode* OLE_CHANGED에는이 매개 변수 변경 된 OLE 항목의 모양을 지정 합니다. 가능한 값에 대 한 참조를 *dwParam* 의 매개 변수 [COleClientItem::Draw](#draw)합니다. 하는 경우 *nCode* OLE_CHANGED_STATE에는이 매개 변수는는 `COleClientItem::ItemState` 값을 열거 하 고 입력 되는 상태를 설명 합니다. 다음 값 중 하나일 수 있습니다: `emptyState`, `loadedState`, `openState`, `activeState`, 또는 `activeUIState`합니다.

### <a name="remarks"></a>설명

(서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 기록 되 면이 함수를 대 한 응답으로 호출 합니다 `Notify` 의 멤버 함수 `COleServerDoc` 또는 `COleServerItem`.) 기본 구현을 수정 하는 경우 컨테이너 문서 표시 *nCode* OLE_CHANGED 인지 OLE_SAVED 합니다.

OLE_CHANGED_STATE, 현재 상태에서 반환 [GetItemState](#getitemstate) 이 상태 변경 하기 전에 현재 상태를 의미 하는 이전 상태를 계속 됩니다.

OLE 항목의 상태 변경에 응답 하도록이 함수를 재정의 합니다. 일반적으로 항목이 표시 되는 영역을 무효화 하 여 항목의 모양을 업데이트 합니다. 기본 클래스 구현을 재정의의 시작 부분에서 호출 합니다.

##  <a name="onchangeitemposition"></a>  COleClientItem::OnChangeItemPosition

OLE 항목의 범위는 현재 위치 활성화 하는 동안 변경 된 컨테이너에 알리기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```

### <a name="parameters"></a>매개 변수

*rectPos*<br/>
컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 항목의 위치를 나타냅니다.

### <a name="return-value"></a>반환 값

항목의 위치가 성공적으로 변경 되 면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 결정 호출이 고 OLE 항목의 표시 되는 새 사각형 [SetItemRects](#setitemrects) 새 값으로. 기본 구현은 항목의 표시 사각형을 계산 하 고 서버에 해당 정보를 전달 합니다.

크기 조정/이동 작업에 특수 규칙을 적용 하려면이 함수를 재정의 합니다. 서버에서 호출 되므로이 호출으로 인해 응용 프로그램에 기록 된다면 mfc에서 [COleServerDoc::RequestPositionChange](../../mfc/reference/coleserverdoc-class.md#requestpositionchange)합니다.

##  <a name="ondeactivate"></a>  COleClientItem::OnDeactivate

OLE 항목은 전체 활성 상태에서 전환 될 때 프레임 워크에서 호출 ( `activeState`) 로드 된 상태로, 현재 위치 활성화 후에 비활성화 됩니다 것을 의미 합니다.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>설명

이 함수는 OLE 항목 닫혀 있지 컨테이너 응용 프로그램에서 제거 된 해당 사용자 인터페이스를 나타내기 위해 호출 되는 note 합니다. 이 경우는 [OnDeactivateUI](#ondeactivateui) 멤버 함수를 호출 합니다.

기본 구현 호출 합니다 [OnChange](#onchange) OLE_CHANGEDSTATE 매개 변수로 사용 하 여 멤버 함수입니다. 전체 활성 항목 비활성화 되 면 사용자 지정 처리를 수행 하려면이 함수를 재정의 합니다. 예를 들어, 실행 취소 명령을 컨테이너 응용 프로그램에서 지 원하는 경우 재정의할 수 있습니다 실행 취소 상태를 삭제 하려면이 함수는 OLE 항목에 수행 된 마지막 작업 실행 취소할 수 없습니다 항목 비활성화 되 면 나타내는.

##  <a name="ondeactivateandundo"></a>  COleClientItem::OnDeactivateAndUndo

사용자 위치에 있는 OLE 항목을 활성화 한 후 실행 취소 명령을 호출 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnDeactivateAndUndo();
```

### <a name="remarks"></a>설명

기본 구현 호출 [DeactivateUI](#deactivateui) 서버 사용자 인터페이스를 비활성화 하려면. Undo 명령 컨테이너 응용 프로그램에서 구현 하는 경우이 함수를 재정의 합니다. 재정의에서 기본 클래스 버전의 함수를 호출 하 고 응용 프로그램에서 실행 되는 마지막 명령 실행 취소 합니다.

자세한 내용은 [IOleInPlaceSite::DeactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-deactivateandundo) Windows SDK에 있습니다.

##  <a name="ondeactivateui"></a>  COleClientItem::OnDeactivateUI

사용자는 내부에서 활성화 된 항목을 비활성화 하는 경우 호출 됩니다.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>매개 변수

*bUndoable*<br/>
편집 변경 맞지 않을 지 여부를 지정 합니다.

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤 숨기기, 원래 상태로 복원 합니다.

하는 경우 *bUndoable* 은 FALSE, 컨테이너는 서버에서 수행 된 마지막 작업은 취소할 수 없습니다를 나타내기 때문에 컨테이너의 실행 취소 상태를 실제로 삭제 실행 취소 명령을 사용 하지 않도록 설정 해야 합니다.

##  <a name="ondiscardundostate"></a>  COleClientItem::OnDiscardUndoState

사용자가 OLE 항목을 편집 하는 동안 실행 취소 상태를 삭제 하는 작업을 수행 하는 경우 프레임 워크에서 호출 합니다.

```
virtual void OnDiscardUndoState();
```

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다. Undo 명령 컨테이너 응용 프로그램에서 구현 하는 경우이 함수를 재정의 합니다. 재정의에서 컨테이너 응용 프로그램의 실행 취소 상태를 삭제 합니다.

서버는 Microsoft Foundation Class 라이브러리를 사용 하 여 작성 된, 서버가이 호출 될이 함수를 호출 하 여 발생할 수 있습니다 [COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate)합니다.

자세한 내용은 [IOleInPlaceSite::DiscardUndoState](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-discardundostate) Windows SDK에 있습니다.

##  <a name="ongetclipboarddata"></a>  COleClientItem::OnGetClipboardData

가져오려는 프레임 워크에서 호출을 `COleDataSource` 개체를 호출 하 여 클립보드에 배치 됩니다 모든 데이터를 포함 하는 [CopyToClipboard](#copytoclipboard) 또는 [DoDragDrop](#dodragdrop) 멤버 함수입니다.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>매개 변수

*bIncludeLink*<br/>
이 경우 TRUE로 설정 링크 데이터를 클립보드에 복사 해야 합니다. 서버의 경우에는 FALSE로 설정 응용 프로그램 링크를 지원 하지 않습니다.

*lpOffset*<br/>
픽셀에서 개체의 원점부터 마우스 커서의 오프셋 포인터입니다.

*lpSize*<br/>
픽셀에서 개체의 크기에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [COleDataSource](../../mfc/reference/coledatasource-class.md) 클립보드 데이터를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현이 호출 [GetClipboardData](#getclipboarddata)합니다.

##  <a name="ongetcliprect"></a>  COleClientItem::OnGetClipRect

프레임 워크 호출을 `OnGetClipRect` 멤버 함수를 현재 위치에서 편집 중인 항목의 클리핑 사각형 좌표를 가져옵니다.

```
virtual void OnGetClipRect(CRect& rClipRect);
```

### <a name="parameters"></a>매개 변수

*rClipRect*<br/>
클래스의 개체에 대 한 포인터 [CRect](../../atl-mfc-shared/reference/crect-class.md) 항목의 클리핑 사각형 좌표를 보유할입니다.

### <a name="remarks"></a>설명

좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 픽셀입니다.

기본 구현은 단순히 항목에 있는 활성 뷰의 클라이언트 사각형을 반환 합니다.

##  <a name="ongetitemposition"></a>  COleClientItem::OnGetItemPosition

프레임 워크 호출을 `OnGetItemPosition` 멤버 함수를 현재 위치에서 편집 중인 항목의 좌표를 가져옵니다.

```
virtual void OnGetItemPosition(CRect& rPosition);
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
에 대 한 참조를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 항목의 위치 좌표를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 픽셀입니다.

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 내부 편집을 지 원하는 응용 프로그램에는 구현이 필요 합니다.

##  <a name="ongetwindowcontext"></a>  COleClientItem::OnGetWindowContext

항목 위치에서 활성화 되 면 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,
    CFrameWnd** ppDocFrame,
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```

### <a name="parameters"></a>매개 변수

*ppMainFrame*<br/>
주 프레임 창에 대 한 포인터에 대 한 포인터입니다.

*ppDocFrame*<br/>
문서 프레임 창에 대 한 포인터에 대 한 포인터입니다.

*lpFrameInfo*<br/>
에 대 한 포인터를 [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) 프레임 창 정보를 받는 구조체입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 OLE 항목의 부모 창에 대 한 정보를 검색에 사용 됩니다.

컨테이너는 MDI 응용 프로그램인 경우 기본 구현은에 대 한 포인터를 반환 합니다 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md) 개체 *ppMainFrame* 활성에 대 한 포인터 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)개체의 *ppDocFrame*합니다. 컨테이너가 SDI 응용 프로그램의 경우 기본 구현에 대 한 포인터를 반환 하는 합니다 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 개체 *ppMainFrame* 에 NULL을 반환 하 고 *ppDocFrame*합니다. 멤버의 기본 구현에서는 또한 채웁니다 *lpFrameInfo*합니다.

기본 구현에서는 응용 프로그램에 적합 하지 않습니다 하는 경우에이 함수를 재정의 합니다. 예를 들어 다음과 같이 응용 프로그램에 다른 SDI 또는 MDI 사용자 인터페이스 패러다임입니다. 이 고급 재정의할 수 있습니다.

자세한 내용은 [IOleInPlaceSite::GetWindowContext](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-getwindowcontext) 하며 [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) Windows SDK의 구조입니다.

##  <a name="oninsertmenus"></a>  COleClientItem::OnInsertMenus

빈 메뉴에 컨테이너 응용 프로그램의 메뉴를 삽입할 위치에서 활성화 하는 동안 프레임 워크에서 호출 됩니다.

```
virtual void OnInsertMenus(
    CMenu* pMenuShared,
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```

### <a name="parameters"></a>매개 변수

*pMenuShared*<br/>
빈 메뉴를 가리킵니다.

*lpMenuWidths*<br/>
다음 메뉴 그룹의 각 메뉴의 수를 나타내는 6 긴 값의 배열 가리킵니다. 파일, 편집, 컨테이너, 개체, 창 도움말입니다. 컨테이너 응용 프로그램은 파일, 컨테이너 및 창 메뉴 그룹의 경우 0, 2 및 4이 배열의 요소에 해당 합니다.

### <a name="remarks"></a>설명

그러면이 메뉴는 자체 메뉴, 합성 메뉴 만들기를 삽입 하는 서버에 전달 됩니다. 이 함수는 여러 복합 메뉴 빌드를 반복적으로 호출할 수 있습니다.

기본 구현은 삽입 *pMenuShared* 전체 컨테이너 메뉴, 즉, 파일, 컨테이너 및 창 메뉴 그룹입니다. [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) 이 메뉴 리소스를 설정 하는 데 사용 됩니다. 기본 구현에서는 0, 2 및 4에서 요소에 적절 한 값을 할당 *lpMenuWidths*메뉴 리소스에 따라 합니다. 기본 구현에서는 응용 프로그램에 적합 하지 않은 경우이 함수를 재정의 합니다. 예를 들어, 응용 프로그램 문서 형식을 사용 하 여 리소스를 연결 하기 위한 문서 템플릿을 사용 하지 않는 경우. 이 함수를 재정의 하면 재정의 해야 [OnSetMenu](#onsetmenu) 하 고 [OnRemoveMenus](#onremovemenus)합니다. 이 고급 재정의할 수 있습니다.

자세한 내용은 [IOleInPlaceFrame::InsertMenus](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceframe-insertmenus) Windows SDK에 있습니다.

##  <a name="onremovemenus"></a>  COleClientItem::OnRemoveMenus

내부 활성화 종료 될 때 지정 된 합성 메뉴에서 컨테이너의 메뉴를 제거 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnRemoveMenus(CMenu* pMenuShared);
```

### <a name="parameters"></a>매개 변수

*pMenuShared*<br/>
호출 하 여 생성 된 합성 메뉴를 가리키는 합니다 [OnInsertMenus](#oninsertmenus) 멤버 함수입니다.

### <a name="remarks"></a>설명

기본 구현에서 제거 *pMenuShared* 된 전체 컨테이너 메뉴, 파일, 컨테이너 및 창 메뉴 그룹입니다. 기본 구현에서는 응용 프로그램에 적합 하지 않은 경우이 함수를 재정의 합니다. 예를 들어, 응용 프로그램 문서 형식을 사용 하 여 리소스를 연결 하기 위한 문서 템플릿을 사용 하지 않는 경우. 이 함수를 재정의 하는 경우 아마도 재정의 해야 [OnInsertMenus](#oninsertmenus) 하 고 [OnSetMenu](#onsetmenu) 도 합니다. 이 고급 재정의할 수 있습니다.

에 하위 메뉴가 *pMenuShared* 서버에 반복 해 서 호출 하는 경우 둘 이상의 합성 메뉴에서 공유할 수 있습니다 `OnInsertMenus`합니다. 재정의에서 모든 하위 메뉴를 삭제 하면 안 되는 따라서 `OnRemoveMenus`;만 분리 해야 합니다.

자세한 내용은 [IOleInPlaceFrame::RemoveMenus](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceframe-removemenus) Windows SDK에 있습니다.

##  <a name="onscrollby"></a>  COleClientItem::OnScrollBy

서버에서 요청에 따라에서 OLE 항목을 스크롤하여 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnScrollBy(CSize sizeExtent);
```

### <a name="parameters"></a>매개 변수

*sizeExtent*<br/>
거리를 픽셀 x 축 및 y 방향 스크롤을 지정 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 항목 스크롤 했습니다. 항목을 스크롤할 수 있는 경우 0입니다.

### <a name="remarks"></a>설명

예를 들어 OLE 항목을 부분적으로 표시 된 경우 내부 편집을 수행 하는 동안 표시 되는 영역 외부 사용자가 커서를 계속 표시 되도록 하려면이 함수가 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 지정된 된 크기 만큼 항목을 스크롤하여 하려면이 함수를 재정의 합니다. 스크롤의 결과로 표시 부분 OLE 항목을 변경할 수 있습니다 note 합니다. 호출 [SetItemRects](#setitemrects) 항목의 표시 사각형을 업데이트 합니다.

자세한 내용은 [IOleInPlaceSite::Scroll](/windows/desktop/api/oleidl/nf-oleidl-ioleinplacesite-scroll) Windows SDK에 있습니다.

##  <a name="onsetmenu"></a>  COleClientItem::OnSetMenu

프레임 워크에서 두 번 호출 내부 활성화를 시작 하 고 끝나는 경우 합성 메뉴 및 두 번째 설치를 위해 첫 번째 시간 (사용 하 여 *holemenu* NULL과 같음)를 제거 합니다.

```
virtual void OnSetMenu(
    CMenu* pMenuShared,
    HOLEMENU holemenu,
    HWND hwndActiveObject);
```

### <a name="parameters"></a>매개 변수

*pMenuShared*<br/>
호출 하 여 생성 된 합성 메뉴에 대 한 포인터를 [OnInsertMenus](#oninsertmenus) 멤버 함수 및 `InsertMenu` 함수입니다.

*holemenu*<br/>
반환 된 메뉴 설명자에 대 한 핸들을 `OleCreateMenuDescriptor` 함수 또는 디스패치 코드가 제거 될 경우 NULL입니다.

*hwndActiveObject*<br/>
OLE 항목에 대 한 편집 창에 대 한 핸들입니다. 이 ole에서 편집 명령을 받는 창입니다.

### <a name="remarks"></a>설명

기본 구현에서는 설치 또는 합성 메뉴를 제거 하 고 호출 된 [OleSetMenuDescriptor](/windows/desktop/api/ole2/nf-ole2-olesetmenudescriptor) 함수를 설치 하거나 디스패치 코드를 제거 합니다. 기본 구현에서는 응용 프로그램에 적합 하지 않은 경우이 함수를 재정의 합니다. 이 함수를 재정의 하는 경우 아마도 재정의 해야 [OnInsertMenus](#oninsertmenus) 하 고 [OnRemoveMenus](#onremovemenus) 도 합니다. 이 고급 재정의할 수 있습니다.

자세한 내용은 [OleCreateMenuDescriptor](/windows/desktop/api/ole2/nf-ole2-olecreatemenudescriptor), [OleSetMenuDescriptor](/windows/desktop/api/ole2/nf-ole2-olesetmenudescriptor), 및 [IOleInPlaceFrame::SetMenu](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceframe-setmenu) Windows sdk에서입니다.

##  <a name="onshowcontrolbars"></a>  COleClientItem::OnShowControlBars

표시 및 컨테이너 응용 프로그램의 컨트롤 막대를 숨기기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*pFrameWnd*<br/>
컨테이너 응용 프로그램의 프레임 창에 대 한 포인터입니다. 메인 프레임 창 또는 MDI 자식 창에 수 있습니다.

*bShow*<br/>
컨트롤 막대를 표시 하거나 숨길 수 있는지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

함수 호출에서 컨트롤 막대의 상태를 변경 하면 0이 아닌 값 0 호출은 변경 없음, 아니면 *pFrameWnd* 컨테이너의 프레임 창을 가리키지 않습니다.

### <a name="remarks"></a>설명

컨트롤 막대에서 지정한 상태 이미 있는 경우이 함수는 0을 반환 *bShow 합니다.* 이 발생 하는 예를 들어, 컨트롤 막대 숨겨져 있는 경우 및 *bShow* 은 FALSE입니다.

기본 구현에서는 최상위 프레임 창에서 도구 모음을 제거합니다.

##  <a name="onshowitem"></a>  COleClientItem::OnShowItem

편집 하는 동안 완전히 표시 되도록 OLE 항목을 표시 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnShowItem();
```

### <a name="remarks"></a>설명

컨테이너 응용 프로그램에서 포함 된 항목에 대 한 링크를 지 원하는 경우 사용 됩니다 (즉,에서 문서 클래스 파생 시킨 경우 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)). 이 함수는 내부 활성화 또는 때 OLE 항목을 링크 소스 이며 사용자가 편집 하려는 동안 호출 됩니다. 컨테이너 문서에서 첫 번째 보기를 활성화 하는 기본 구현입니다. OLE 항목을 볼 수 있도록 문서를 스크롤합니다 하려면이 함수를 재정의 합니다.

##  <a name="onupdateframetitle"></a>  COleClientItem::OnUpdateFrameTitle

프레임 창의 제목 표시줄을 업데이트 하려면 내부 활성화 동안 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnUpdateFrameTitle();
```

### <a name="return-value"></a>반환 값

이 0이 아닌 함수를 업데이트 했습니다. 프레임 제목, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 프레임 창 제목을 변경 되지 않습니다. 예를 들어 응용 프로그램에 대 한 다른 프레임 title을 원하는 경우이 함수를 재정의 합니다. " *서버 앱* - *항목* 에서 *docname*" (예: "Microsoft Excel-보고서에서 스프레드시트입니다. DOC ")입니다. 이 고급 재정의할 수 있습니다.

##  <a name="reactivateandundo"></a>  COleClientItem::ReactivateAndUndo

OLE 항목을 다시 활성화 하 고 전체 편집 하는 동안 사용자가 수행한 마지막 작업을 취소 하려면이 함수를 호출 합니다.

```
BOOL ReactivateAndUndo();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

컨테이너 응용 프로그램을 실행 취소 명령의 지 원하는 경우 사용자가 OLE 항목을 비활성화 한 후에 즉시 실행 취소 명령을 선택할 경우이 함수를 호출 합니다.

이 함수를 호출 하는 서버 사용 하면 Microsoft Foundation 클래스 라이브러리를 사용 하 여 서버 응용 프로그램에 기록 [COleServerDoc::OnReactivateAndUndo](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo)합니다.

자세한 내용은 [IOleInPlaceObject::ReactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) Windows SDK에 있습니다.

##  <a name="release"></a>  COleClientItem::Release

OLE 항목을 사용 하는 리소스를 정리 하려면이 함수를 호출 합니다.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>매개 변수

*dwCloseOption*<br/>
OLE 항목 로드 된 상태로 돌아오면 어떤 상황에서 저장을 지정 하는 플래그입니다. 가능한 값 목록을 참조 하세요 [COleClientItem::Close](#close)합니다.

### <a name="remarks"></a>설명

`Release` 호출한는 `COleClientItem` 소멸자입니다.

자세한 내용은 [iunknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) Windows SDK에 있습니다.

##  <a name="reload"></a>  COleClientItem::Reload

페이지를 닫고 다시 로드 하는 항목입니다.

```
BOOL Reload();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 된 `Reload` 함수를 호출 하 여 다른 형식의 항목으로 항목을 활성화 한 후 [ActivateAs](#activateas)합니다.

##  <a name="run"></a>  COleClientItem::Run

이 항목과 연결 된 응용 프로그램을 실행 합니다.

```
void Run();
```

### <a name="remarks"></a>설명

호출 된 `Run` 멤버 함수는 항목을 활성화 하기 전에 서버 응용 프로그램을 시작 합니다. 이 자동으로 수행 됩니다 [활성화](#activate) 하 고 [DoVerb](#doverb)이므로 일반적으로 필요 없는이 함수를 호출 합니다. 같은 항목 특성을 설정 하기 위해 서버를 실행 하는 데 필요한 경우이 함수를 호출 [SetExtent](#setextent)를 실행 하기 전에 [DoVerb](#doverb)합니다.

##  <a name="setdrawaspect"></a>  COleClientItem::SetDrawAspect

호출 된 `SetDrawAspect` 멤버 함수를 "모양" 또는 항목의 보기를 설정 합니다.

```
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```

### <a name="parameters"></a>매개 변수

*nDrawAspect*<br/>
DVASPECT 열거형에서 사용 되는 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 해당 컨테이너 내에서 포함 된 개체로 표시할 수 있습니다 하는 방식으로 표시 됩니다.

- 검색 도구에 표시 될 수 있도록 "미리 보기" 표현에서 DVASPECT_THUMBNAIL 항목이 렌더링 됩니다.

- DVASPECT_ICON 항목 아이콘으로 표시 됩니다.

- 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 DVASPECT_DOCPRINT 항목이 표시 됩니다.

### <a name="remarks"></a>설명

측면에 의해 렌더링 되는 항목은 하는 방법을 지정 [그릴](#draw) 는 기본값이 해당 함수에 대 한 *nDrawAspect* 인수를 사용 합니다.

아이콘 변경 (및 아이콘 변경 대화 상자를 직접 호출 하는 다른 대화 상자)에서이 함수를 자동으로 호출 아이콘 표시 측면을 사용자가 요청할 때 사용할 수 있도록 합니다.

##  <a name="setextent"></a>  COleClientItem::SetExtent

OLE 항목에 사용 가능한 공간의 양을 지정 하려면이 함수를 호출 합니다.

```
void SetExtent(
    const CSize& size,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
A [CSize](../../atl-mfc-shared/reference/csize-class.md) 크기 정보를 포함 하는 개체입니다.

*nDrawAspect*<br/>
해당 경계는 설정할 OLE 항목의 모양을 지정 합니다. 가능한 값을 참조 하세요 [SetDrawAspect](#setdrawaspect)합니다.

### <a name="remarks"></a>설명

이 인해 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 작성 된 경우는 [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent) 멤버 함수는 해당 `COleServerItem` 호출할 개체입니다. 그런 다음 OLE 항목의 표시를 적절 하 게 조정할 수 있습니다. 차원은 MM_HIMETRIC 단위 여야 합니다. 사용자가 OLE 항목 크기 조정 또는 레이아웃 협상 형태의 지 원하는 경우이 함수를 호출 합니다.

자세한 내용은 [IOleObject::SetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setextent) Windows SDK에 있습니다.

##  <a name="sethostnames"></a>  COleClientItem::SetHostNames

포함된 OLE 항목에 대 한 컨테이너의 이름과 컨테이너 응용 프로그램의 이름을 지정 하려면이 함수를 호출 합니다.

```
void SetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>매개 변수

*lpszHost*<br/>
컨테이너 응용 프로그램의 사용자 표시 이름에 대 한 포인터입니다.

*lpszHostObj*<br/>
OLE 항목을 포함 하는 컨테이너의 식별 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수를 호출 하는 서버 응용 프로그램이 Microsoft Foundation Class 라이브러리를 사용 하 여 작성 된 경우는 [OnSetHostNames](../../mfc/reference/coleserverdoc-class.md#onsethostnames) 멤버 함수는 `COleServerDoc` OLE 항목을 포함 하는 문서입니다. OLE 항목을 편집 하는 경우이 정보 창 제목에 사용 됩니다. 컨테이너 문서 로드 될 때마다 프레임 워크 문서에서 모든 OLE 항목에 대 한이 함수를 호출 합니다. `SetHostNames` 포함 된 항목에만 적용 됩니다. 편집을 위해 포함 된 OLE 항목이 활성화 될 때마다가이 함수를 호출 하는 데 필요한 것입니다.

또한이 호출 됩니다 자동으로 응용 프로그램 이름과 문서를 사용 하 여 개체를 로드할 때 또는 다른 이름으로 파일을 저장할 때. 따라서 일반적으로이 함수를 직접 호출할 필요는 없습니다.

자세한 내용은 [IOleObject::SetHostNames](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-sethostnames) Windows SDK에 있습니다.

##  <a name="seticonicmetafile"></a>  COleClientItem::SetIconicMetafile

항목의 아이콘을 그리는 데 사용 하 여 메타 파일을 캐시 합니다.

```
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```

### <a name="parameters"></a>매개 변수

*hMetaPict*<br/>
항목의 아이콘을 그리는 데 사용 하 여 메타 파일 핸들입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 [GetIconicMetafile](#geticonicmetafile) 메타 파일을 검색할 합니다.

합니다 *hMetaPict* 매개 변수는 항목에 복사 됩니다 따라서 *hMetaPict* 호출자가 해제 해야 합니다.

##  <a name="setitemrects"></a>  COleClientItem::SetItemRects

경계 사각형 또는 OLE 항목의 표시 사각형을 설정 하려면이 함수를 호출 합니다.

```
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,
    LPCRECT lpClipRect = NULL);
```

### <a name="parameters"></a>매개 변수

*lprcPosRect*<br/>
부모 창의 클라이언트 좌표에서를 기준으로 OLE 항목의 범위를 포함 하는 사각형에 대 한 포인터입니다.

*lprcClipRect*<br/>
부모 창의 클라이언트 좌표에서를 기준으로 OLE 항목의 표시 부분 범위가 포함 된 사각형에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않을 경우 0입니다.

### <a name="remarks"></a>설명

기본 구현에 의해이 함수가 호출 되는 [OnChangeItemPosition](#onchangeitemposition) 멤버 함수입니다. 위치 또는 표시 되는 부분 OLE 항목 변경 될 때마다이 함수를 호출 해야 합니다. 즉, 일반적으로 보기의에서 호출할 [OnSize](../../mfc/reference/cwnd-class.md#onsize) 하 고 [OnScrollBy](../../mfc/reference/cview-class.md#onscrollby) 멤버 함수입니다.

자세한 내용은 [IOleInPlaceObject::SetObjectRects](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) Windows SDK에 있습니다.

##  <a name="setlinkupdateoptions"></a>  COleClientItem::SetLinkUpdateOptions

지정된 된 연결 된 항목의 표시에 대 한 연결 업데이트 옵션을 설정 하려면이 함수를 호출 합니다.

```
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```

### <a name="parameters"></a>매개 변수

*dwUpdateOpt*<br/>
이 항목에 대 한 연결 업데이트 옵션의 값입니다. 이 값에는 다음 중 하나 여야 합니다.

- OLEUPDATE_ALWAYS 가능 하면 연결 된 항목을 업데이트 합니다. 이 옵션은 연결 대화 상자에서 자동 링크 업데이트 라디오 단추를 지원 합니다.

- OLEUPDATE_ONCALL 컨테이너 응용 프로그램의 요청에만 연결 된 항목을 업데이트 (때 합니다 [UpdateLink](#updatelink) 멤버 함수가 호출 됩니다). 이 옵션은 연결 대화 상자에서 수동 링크 업데이트 라디오 단추를 지원 합니다.

### <a name="remarks"></a>설명

일반적으로 연결 대화 상자에서 사용자가 선택한 업데이트 옵션을 변경 하지 않아야 합니다.

자세한 내용은 [IOleLink::SetUpdateOptions](/windows/desktop/api/oleidl/nf-oleidl-iolelink-setupdateoptions) Windows SDK에 있습니다.

##  <a name="setprintdevice"></a>  COleClientItem::SetPrintDevice

이 항목에 대 한 인쇄 대상 장치를 변경 하려면이 함수를 호출 합니다.

```
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);
BOOL SetPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>매개 변수

*ptd*<br/>
에 대 한 포인터를 [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) 새 대상 인쇄 장치에 대 한 정보를 포함 하는 데이터 구조입니다. NULL 일 수 있습니다.

*ppd*<br/>
에 대 한 포인터를 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) 새 대상 인쇄 장치에 대 한 정보를 포함 하는 데이터 구조입니다. NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 항목에 대 한 인쇄 대상 장치를 업데이트 하지만 프레젠테이션 캐시를 새로 고치지 않습니다. 항목에 대 한 프레젠테이션 캐시를 업데이트 하려면 호출 [UpdateLink](#updatelink)합니다.

이 함수에 인수 OLE 시스템에서 대상 장치를 식별 하는 정보를 포함 합니다. `PRINTDLG` 구조 Windows 공용 인쇄 대화 상자를 초기화 하는 데 사용 하는 정보가 들어 있습니다. 사용자 대화 상자를 닫은 후 Windows는이 구조에서 사용자의 선택 항목에 대 한 정보를 반환 합니다. 합니다 `m_pd` 의 멤버를 [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체가 `PRINTDLG` 구조입니다.

이 구조에 대 한 자세한 내용은 참조 하세요. [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Windows SDK에 있습니다.

자세한 내용은 [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) Windows SDK에 있습니다.

##  <a name="updatelink"></a>  COleClientItem::UpdateLink

OLE 항목의 프레젠테이션 데이터를 즉시 업데이트 하려면이 함수를 호출 합니다.

```
BOOL UpdateLink();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

연결 된 항목에 대 한 함수는 OLE 항목에 대 한 새 프레젠테이션을 가져오려면 소스를 링크를 찾습니다. 이 프로세스는 하나 이상의 서버 응용 프로그램을 실행 시간이 오래 걸릴 수 있는 포함 될 수 있습니다. 포함 된 항목에 대 한 함수를 재귀적으로 만료 될 수 있는 링크가 포함된 된 항목에 포함 되는지 여부를 확인 하 고 고 업데이트 하 여 작동 합니다. 사용자를 수동으로 업데이트할 수도 연결 대화 상자를 사용 하 여 개별 링크입니다.

자세한 내용은 [IOleLink::Update](/windows/desktop/api/oleidl/nf-oleidl-iolelink-update) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CDocItem 클래스](../../mfc/reference/cdocitem-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)
