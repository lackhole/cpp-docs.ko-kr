---
title: COleServerDoc 클래스
ms.date: 11/04/2016
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
ms.openlocfilehash: 4cada70723c7fadc9c91c40380b8a7e9fc46a07a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777261"
---
# <a name="coleserverdoc-class"></a>COleServerDoc 클래스

OLE 서버 문서의 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleServerDoc::COleServerDoc](#coleserverdoc)|`COleServerDoc` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleServerDoc::ActivateDocObject](#activatedocobject)|연결된 된 DocObject 문서를 활성화합니다.|
|[COleServerDoc::ActivateInPlace](#activateinplace)|내부 편집에 대 한 문서를 활성화합니다.|
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|서버 사용자 인터페이스를 비활성화합니다.|
|[COleServerDoc::DiscardUndoState](#discardundostate)|실행 취소 상태 정보를 삭제합니다.|
|[COleServerDoc::GetClientSite](#getclientsite)|기본 포인터를 검색 `IOleClientSite` 인터페이스입니다.|
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|전체 문서를 나타내는 항목에 대 한 포인터를 반환 합니다.|
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|내부 편집에 대 한 현재 클리핑 사각형을 반환합니다.|
|[COleServerDoc::GetItemPosition](#getitemposition)|내부 편집에 대 한 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 현재 위치 사각형을 반환 합니다.|
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|확대/축소 비율을 픽셀 단위로 반환 합니다.|
|[COleServerDoc::IsDocObject](#isdocobject)|DocObject 문서 인지 확인 합니다.|
|[COleServerDoc::IsEmbedded](#isembedded)|문서를 컨테이너 문서의 포함 되거나 독립 실행형 실행 여부를 나타냅니다.|
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|항목 위치에서 현재 활성화 된 경우 TRUE를 반환 합니다.|
|[COleServerDoc::NotifyChanged](#notifychanged)|사용자가 문서를 변경 된 컨테이너에 알립니다.|
|[COleServerDoc::NotifyClosed](#notifyclosed)|사용자가 문서를 닫은 컨테이너를 알립니다.|
|[COleServerDoc::NotifyRename](#notifyrename)|사용자의 문서는 이름이 컨테이너에 알립니다.|
|[COleServerDoc::NotifySaved](#notifysaved)|사용자가 문서를 저장할에 컨테이너를 알립니다.|
|[COleServerDoc::OnDeactivate](#ondeactivate)|사용자가 내부에서 활성화 된 항목 비활성화 하면 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|컨트롤 및 내부 활성화에 대해 생성 하는 기타 사용자 인터페이스 요소를 제거 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|컨테이너의 문서 프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnResizeBorder](#onresizeborder)|컨테이너 응용 프로그램의 프레임 창이 나 문서 창을 크기를 조정할 때 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|내부 편집에 대 한 컨트롤 막대 표시 또는 숨기기 위해 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|포함 된 항목에는 서버 문서를 저장할 항목의 컨테이너의 복사본을 업데이트 하는 경우 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|내부 편집 프레임의 위치를 변경합니다.|
|[COleServerDoc::SaveEmbedding](#saveembedding)|문서를 저장할 컨테이너 응용 프로그램에 알려줍니다.|
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|컨테이너 문서를 스크롤합니다.|
|[COleServerDoc::UpdateAllItems](#updateallitems)|사용자가 문서를 변경 된 컨테이너에 알립니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|내부 편집을 위해 프레임 창을 만들기 위해 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|내부 편집을 위해 프레임 창을 제거 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|이 함수를 만들기 위한 재정의 `CDocObjectServer` 개체 및이 문서의 DocObject 컨테이너 임을 나타냅니다.|
|[COleServerDoc::OnClose](#onclose)|문서를 닫으려면 컨테이너를 요청 하는 경우 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|지정 된 명령을 실행 하거나 명령에 대 한 도움말을 표시 합니다.|
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|컨테이너의 프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|가져오기 위해 호출을 `COleServerItem` 는 전체 문서를 나타내는; 포함 된 항목을 가져오는 데 사용 합니다. 필요한 구현입니다.|
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|내부 편집 하는 동안 변경한 내용을 실행 취소 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnSetHostNames](#onsethostnames)|컨테이너 창 제목이 포함된 된 개체에 설정 하는 경우 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|컨테이너 응용 프로그램의 창 내에서 내부 편집 프레임 창을 배치 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleServerDoc::OnShowDocument](#onshowdocument)|표시 하거나 숨기려면 문서 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

서버 문서에 포함 될 수 있습니다 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체를 포함 또는 연결 된 항목에는 서버 인터페이스를 나타냅니다. 항목이 자체 서버 문서로 로드 되는 서버 응용 프로그램 컨테이너가 포함 된 항목을 편집 하 여 시작 되 면 `COleServerDoc` 개체를 하나만 포함 `COleServerItem` 전체 문서의 구성 된 개체입니다. 기존 문서를 디스크에서 로드 되는 서버 응용 프로그램 연결 된 항목을 편집 하려면 컨테이너가 시작 되 면 문서 내용 부분 링크 된 항목을 나타내기 위해 강조 표시 됩니다.

`COleServerDoc` 개체의 항목을 포함할 수도 있습니다는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 클래스입니다. 이 옵션을 사용 하면 컨테이너-서버 응용 프로그램을 만들 수 있습니다. 프레임 워크를 제대로 저장할 함수를 제공 합니다 `COleClientItem` 항목이 서비스 하는 동안는 `COleServerItem` 개체.

서버 응용 프로그램 링크를 지원 하지 않는 경우 서버 문서 문서로 포함된 된 전체 개체를 나타내는 하나의 서버 항목을 항상 포함 됩니다. 서버 응용 프로그램에서 연결을 지원 하는 경우 만들어야 서버 항목을 될 때마다 선택 영역을 클립보드에 복사 됩니다.

사용 하도록 `COleServerDoc`클래스에서 파생 되 고 구현 합니다 [OnGetEmbeddedItem](#ongetembeddeditem) 포함 된 항목을 지원 하도록 서버를 허용 하는 멤버 함수. 클래스를 파생 `COleServerItem` 문서에서 항목을 구현 하 고 해당 클래스의 개체를 반환 하려면 `OnGetEmbeddedItem`합니다.

링크 된 항목을 지원 하기 위해 `COleServerDoc` 제공 합니다 [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) 멤버 함수입니다. 기본 구현을 사용할 수도 있고 원하는 방식으로 문서 항목을 관리 하는 경우 재정의할 수 있습니다.

필요한 `COleServerDoc`-각 서버 유형의 응용 프로그램에서 지원할 문서에 대 한 클래스를 파생 합니다. 예를 들어 서버 응용 프로그램에서 워크시트 및 차트를 지 원하는 경우 두 `COleServerDoc`-클래스를 파생 합니다.

서버에 대 한 자세한 내용은 문서를 참조 하세요. [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject

연결된 된 DocObject 문서를 활성화합니다.

```
void ActivateDocObject();
```

### <a name="remarks"></a>설명

기본적으로 `COleServerDoc` 액티브 문서 (DocObjects 라고도 함)를 지원 하지 않습니다. 이 지원을 사용 하려면 [GetDocObjectServer](#getdocobjectserver) 및 클래스 [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)합니다.

##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace

내부 편집에 대 한 항목을 활성화합니다.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않으면 0, 항목 임을 나타냅니다 완전 개방 합니다.

### <a name="remarks"></a>설명

이 함수는 내부 활성화에 필요한 모든 작업을 수행합니다. 이 내부 프레임 창을 만듭니다, 그리고 활성화 및 항목 크기, 공유 메뉴 및 기타 컨트롤을 설정, 항목, 스크롤하여 내부 프레임 창에 포커스를 설정 합니다.

이 함수는 기본 구현에 의해 호출 됩니다 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)합니다. 응용 프로그램 (예: 재생) 내부 활성화에 대 한 다른 동사를 지 원하는 경우이 함수를 호출 합니다.

##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc

생성 된 `COleServerDoc` OLE 시스템 Dll 사용 하 여 연결 하지 않고도 개체입니다.

```
COleServerDoc();
```

### <a name="remarks"></a>설명

호출 해야 합니다 [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) OLE를 사용 하 여 통신을 열려고 합니다. 사용 중인 경우 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 응용 프로그램에서 `COleLinkingDoc::Register` 에서 자동으로 호출 됩니다 `COleLinkingDoc`의 구현의 `OnNewDocument`를 `OnOpenDocument`, 및 `OnSaveDocument`합니다.

##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame

프레임 워크 내부 편집을 위해 프레임 창을 만들려면이 함수를 호출 합니다.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
컨테이너 응용 프로그램의 부모 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

내부 프레임 창 또는 실패 한 경우 NULL 포인터입니다.

### <a name="remarks"></a>설명

기본 구현은 문서 서식 파일에 지정 된 정보를 사용 하 여 프레임을 만듭니다. 사용 되는 뷰는 문서에 대해 만든 첫 번째 뷰입니다. 이 보기는 일시적으로 원래 프레임에서 분리 되며 새로 만든된 프레임에 연결 됩니다.

이 고급 재정의할 수 있습니다.

##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo

응용 프로그램에서 지원할 실행 취소 하 고 사용자가 항목을 활성화 한 후 하지만 편집 하기 전에 실행 취소를 선택 하는 경우이 함수를 호출 합니다.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

Microsoft Foundation Class 라이브러리를 사용 하 여 컨테이너 응용 프로그램 기록 되는 경우이 함수를 호출 하면 [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) 서버 사용자 인터페이스를 비활성화 하는 호출 될 수 있습니다.

##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame

프레임 워크는 내부 프레임 창을 소멸 하 고 서버 응용 프로그램의 문서 창 바로 활성화 하기 전에 해당 상태로 반환 하려면이 함수를 호출 합니다.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>매개 변수

*pFrameWnd*<br/>
제거할 내부 프레임 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 고급 재정의할 수 있습니다.

##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState

사용자 작업은 실행 취소할 수 없는 편집 작업을 수행 하는 경우 해당 실행 취소 상태 정보를 삭제 하려는 컨테이너 응용 프로그램에서이 함수를 호출 합니다.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

이 함수는 실행 취소를 지 원하는 서버를 사용할 수 없는 실행 취소 상태 정보로 사용할 수 있는 리소스를 확보할 수 있도록 제공 됩니다.

##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite

기본 포인터를 검색 `IOleClientSite` 인터페이스입니다.

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>반환 값

기본 포인터를 검색 [IOleClientSite](/windows/desktop/api/oleidl/nn-oleidl-ioleclientsite) 인터페이스입니다.

##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer

이 함수를 만들기 위한 재정의 `CDocObjectServer` 항목 및에 대 한 포인터를 반환 합니다.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>매개 변수

*pDocSite*<br/>
에 대 한 포인터를 `IOleDocumentSite` 이 문서를 서버에 연결 하는 인터페이스입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CDocObjectServer`; 작업에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

DocObject 서버 활성화 되 면 NULL이 아닌 포인터를 반환 되는 클라이언트 DocObjects를 지원할 수 있는지 보여 줍니다. 기본 구현은 NULL을 반환합니다.

DocObjects를 지 원하는 문서에 대 한 일반적인 구현은 단순히 새 할당 `CDocObjectServer` 개체와 호출자에 게 반환 합니다. 예를 들어:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem

전체 문서를 나타내는 항목에 대 한 포인터를 가져오려면이 함수를 호출 합니다.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>반환 값

전체 문서를 나타내는 항목에 대 한 포인터 작업에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

호출한 [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), 기본 구현이 없는 가상 함수입니다.

##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect

호출 된 `GetItemClipRect` 멤버 함수를 현재 위치에서 편집 중인 항목의 클리핑 사각형 좌표를 가져옵니다.

```
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>매개 변수

*lpClipRect*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 항목의 클리핑 사각형 좌표를 받을 개체입니다.

### <a name="remarks"></a>설명

좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 픽셀입니다.

클리핑 사각형을 외부 그리기 발생 하지 않습니다. 일반적으로 그리기는 자동으로 제한 됩니다. 이 함수를 사용 하 여 문서에 보이는 부분 외부 사용자가 스크롤 여부를 확인 하려면 그렇다면을 호출 하 여 필요에 따라 컨테이너 문서를 스크롤합니다 [ScrollContainerBy](#scrollcontainerby)합니다.

##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition

호출 된 `GetItemPosition` 멤버 함수를 현재 위치에서 편집 중인 항목의 좌표를 가져옵니다.

```
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 항목의 좌표를 받을 개체입니다.

### <a name="remarks"></a>설명

좌표는 컨테이너 응용 프로그램 창의 클라이언트 영역을 기준으로 픽셀입니다.

항목의 위치는 항목을 표시 (또는 표시 되지 않는) 범위를 확인 하려면 현재 클리핑 사각형을 비교할 수 화면의 합니다.

##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor

`GetZoomFactor` 멤버 함수는 내부 편집에 대 한 활성화 된 항목의 "확대/축소 비율"을 결정 합니다.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpSizeNum*<br/>
클래스의 개체에 대 한 포인터 `CSize` 확대/축소 비율의 분자를 보유할입니다. NULL 일 수 있습니다.

*lpSizeDenom*<br/>
클래스의 개체에 대 한 포인터 `CSize` 확대/축소 비율의 분모를 보유할입니다. NULL 일 수 있습니다.

*lpPosRect*<br/>
클래스의 개체에 대 한 포인터 `CRect` 하는 항목의 새 위치에 설명 합니다. 이 인수가 NULL 이면 함수는 항목의 현재 위치를 사용 합니다.

### <a name="return-value"></a>반환 값

항목의 위치에 대 한 활성화 된 경우 0이 아닌 편집 하 고 해당 확대/축소 비율은 100% (1:1) 이외의 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

확대/축소 비율을 픽셀 단위로 나타낸는 현재 범위에 해당 하는 항목의 크기의 비율입니다. 컨테이너 응용 프로그램 항목의 범위 내에서 자연스럽 게 그 범위가 설정 되지 않은 경우 (에 따른 [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) 사용 됩니다.

처음 두 인수로 분자와 분모의 항목의 "확대/축소 비율입니다."를 설정 하는 함수 항목 위치에서 편집 중인 되지 경우 함수는 기본값은 100% (또는 1:1)에 이러한 인수를 설정 하 고 0을 반환 합니다. 자세한 내용은 기술 참고 40을 참조 하세요 [MFC/OLE 내부 크기 조정 및 확대/축소](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)합니다.

##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject

DocObject 문서 인지 확인 합니다.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 문서가 DocObject; 그렇지 않으면 FALSE입니다.

##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded

호출 된 `IsEmbedded` 문서 컨테이너에 포함 된 개체를 나타내는지 여부를 결정 하는 멤버 함수입니다.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `COleServerDoc` 개체는 개체를 나타내는 문서 컨테이너에 포함 된 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

파일에서 로드 하는 문서 링크로 컨테이너 응용 프로그램에서 조작할 수 있지만 포함 되지 않습니다. 컨테이너 문서의 포함 된 문서를 포함할 수로 간주 됩니다.

##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive

호출 된 `IsInPlaceActive` 항목이 현재 전체 활성 상태 인지 여부를 결정 하는 멤버 함수입니다.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `COleServerDoc` 개체가 현재 위치에서 활성화 그렇지 않으면 0입니다.

##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged

문서 변경 된 문서에 연결 된 모든 연결 된 항목을 알리지이 함수를 호출 합니다.

```
void NotifyChanged();
```

### <a name="remarks"></a>설명

일반적으로 사용자의 서버 문서 크기와 같은 일부 전역 특성을 변경한 후이 함수를 호출 합니다. OLE 항목은 자동 링크를 사용 하 여 문서에 연결 된, 항목의 변경 내용을 반영 하도록 업데이트 됩니다. Microsoft Foundation Class 라이브러리를 사용 하 여 작성 하는 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 함수 `COleClientItem` 라고 합니다.

> [!NOTE]
>  이 함수는 OLE 1을 사용 하 여 호환성을 위해 포함 합니다. 새 응용 프로그램을 사용할지 [UpdateAllItems](#updateallitems)합니다.

##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed

문서 닫 혔 음을 컨테이너에 알리기 위해이 함수를 호출 합니다.

```
void NotifyClosed();
```

### <a name="remarks"></a>설명

파일 메뉴에서 [닫기] 명령을 선택 하면 `NotifyClosed` 호출한 `COleServerDoc`의 구현의 합니다 [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) 멤버 함수입니다. Microsoft Foundation Class 라이브러리를 사용 하 여 작성 하는 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 함수 `COleClientItem` 라고 합니다.

##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename

사용자의 서버 문서의 이름을 후이 함수를 호출 합니다.

```
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>매개 변수

*lpszNewName*<br/>
서버 문서;의 새 이름을 지정 하는 문자열에 대 한 포인터 이것이 일반적으로 정규화 된 경로입니다.

### <a name="remarks"></a>설명

파일 메뉴에서 이름으로 저장 명령을 선택 하면 `NotifyRename` 호출한 `COleServerDoc`의 구현의 합니다 [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) 멤버 함수입니다. 이 함수는 OLE 시스템을 컨테이너에 알리는 하는 Dll에 알립니다. Microsoft Foundation Class 라이브러리를 사용 하 여 작성 하는 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 함수 `COleClientItem` 라고 합니다.

##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved

서버 문서를 저장 한 후이 함수를 호출 합니다.

```
void NotifySaved();
```

### <a name="remarks"></a>설명

저장 명령을 파일 메뉴에서 선택 하면 `NotifySaved` 에서 자동으로 호출 됩니다 `COleServerDoc`의 구현을 [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument)합니다. 이 함수는 OLE 시스템을 컨테이너에 알리는 하는 Dll에 알립니다. Microsoft Foundation Class 라이브러리를 사용 하 여 작성 하는 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 함수 `COleClientItem` 라고 합니다.

##  <a name="onclose"></a>  COleServerDoc::OnClose

컨테이너에서 요청 하는 서버 문서의 닫을 수 있음을 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>매개 변수

*dwCloseOption*<br/>
OLECLOSE 열거형에서 사용 되는 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- OLECLOSE_SAVEIFDIRTY가 수정 된 경우 파일 저장 됩니다.

- OLECLOSE_NOSAVE 파일 내용이 저장 되지 않고 닫혀 있습니다.

- OLECLOSE_PROMPTSAVE 파일 수정 되었으면, 저장 하는 방법에 대 한 메시지가 표시 됩니다.

### <a name="remarks"></a>설명

기본 구현 호출 `CDocument::OnCloseDocument`합니다.

자세한 내용 및 추가 값을 참조 하세요 [OLECLOSE](/windows/desktop/api/oleidl/ne-oleidl-tagoleclose) Windows SDK에 있습니다.

##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate

사용자가 현재 내부 활성화 하는 포함 되거나 연결 된 항목이 비활성화 하면 프레임 워크에서 호출 됩니다.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원 하 고 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤을 제거 합니다.

실행 취소 상태 정보를이 시점에서 무조건 릴리스될 해야 합니다.

자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)...

##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI

사용자는 내부에서 활성화 된 항목을 비활성화 하는 경우 호출 됩니다.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>매개 변수

*bUndoable*<br/>
편집 변경 내용을 실행 취소할 수 있는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

이 함수는 컨테이너 응용 프로그램의 사용자 인터페이스 모든 메뉴 및 내부 활성화에 대해 생성 된 다른 컨트롤 숨기기, 원래 상태로 복원 합니다.

프레임 워크는 항상 설정 *bUndoable* FALSE로 합니다. 서버에서 실행 취소를 지원 되며 실행 취소할 수 있는 작업을 하는 경우 사용 하 여 기본 클래스 구현을 호출 *bUndoable* TRUE로 설정 합니다.

##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate

프레임 워크를 활성화 또는 비활성화 문서 창 바로 편집 기능에 대 한이 함수를 호출 합니다.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
문서 창 활성화 또는 비활성화 될 지 여부를 지정 합니다.

### <a name="remarks"></a>설명

기본 구현은 제거 하거나 적절 하 게 프레임 수준의 사용자 인터페이스 요소를 추가 합니다. 항목을 포함 하는 문서 활성화 또는 비활성화 하는 경우 추가 작업을 수행 하려는 경우이 함수를 재정의 합니다.

자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)...

##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd

프레임 워크는 지정된 된 명령을 실행 하거나 명령에 대 한 도움말을 표시 하려면이 함수를 호출 합니다.

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>매개 변수

*pguidCmdGroup*<br/>
명령 집합을 식별 하는 GUID에 대 한 포인터입니다. 기본 명령 그룹을 나타내는 NULL을 수 있습니다.

*nCmdID*<br/>
실행할 명령입니다. 로 식별 된 그룹에 있어야 *pguidCmdGroup*합니다.

*nCmdExecOut*<br/>
서 개체 OLECMDEXECOPT 열거형에서 다음 값 중 명령, 하나 이상의 실행 해야 합니다.

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargIn*<br/>
명령의 입력된 인수를 포함 하는 VARIANTARG에 대 한 포인터입니다. NULL 일 수 있습니다.

*pvarargOut*<br/>
명령에서 값을 반환 하는 출력을 받을 VARIANTARG에 대 한 포인터입니다. NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 반환 다음 오류 코드 중이 고, 그렇지:

|값|설명|
|-----------|-----------------|
|E_UNEXPECTED|예기치 않은 오류가 발생 했습니다.|
|E_FAIL|오류가 발생 했습니다.|
|E_NOTIMPL|MFC 나타냅니다 변환 하 고 명령 디스패치 하려고 시도해 야 자체|
|OLECMDERR_E_UNKNOWNGROUP|*pguidCmdGroup* NULL이 아닌 하지만 인식할 수 있는 명령 그룹을 지정 하지 않습니다|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* 그룹에서 유효한 명령으로 인식 되지 않습니다 *pguidCmdGroup*|
|OLECMDERR_DISABLED|로 식별 되는 명령을 *nCmdID* 비활성화 되 고 실행할 수 없습니다|
|OLECMDERR_NOHELP|호출자에서 지정 된 명령에 도움을 요청 *nCmdID* 도움말을 사용할 수 있지만|
|OLECMDERR_CANCELED|사용자가 실행 취소 했습니다.|

### <a name="remarks"></a>설명

`COleCmdUI` 사용 하도록 설정, 업데이트 및 DocObject 사용자 인터페이스 명령의 기타 속성 설정에 사용할 수 있습니다. 명령을 초기화 된 후 사용 하 여 실행할 수 있습니다 `OnExecOleCmd`합니다.

프레임 워크를 변환 및 OLE 문서 명령을 발송 하기 전에 함수를 호출 합니다. 표준 OLE 문서 명령을 처리 하려면이 함수를 재정의할 필요는 없지만 사용자 지정 명령을 직접 처리 하거나 매개 변수를 수락 하거나 결과 반환 하는 명령을 처리 하려는 경우이 함수에는 재정의 제공 해야 합니다.

대부분의 명령은 인수를 사용 하지 않거나 값을 반환 합니다. 대부분의 명령에 대 한 호출자에 게 전달할 수 Null에 대 한 *pvarargIn* 하 고 *pvarargOut*합니다. 입력된 값을 필요로 하는 명령에 대 한 호출자 선언 및 VARIANTARG 변수를 초기화 하 고 수에서 변수에 대 한 포인터를 전달 *pvarargIn*합니다. 단일 값을 필요로 하는 명령에 대 한 인수는 VARIANTARG에 직접 저장 고 함수에 전달 될 수 있습니다. 지원 되는 형식 중 하나를 사용 하 여 VARIANTARG 내에서 여러 개의 인수를 패키지 해야 합니다 (같은 `IDispatch` 및 SAFEARRAY).

명령 호출자는 VARIANTARG 선언 될 인수를 반환 하면 값을 vt_empty로, 초기화 하 고 주소를 전달 합니다. 마찬가지로 *pvarargOut*합니다. 개체에서 직접 값을 저장할 수 명령에서 단일 값을 반환 하는 경우 *pvarargOut*합니다. 여러 출력 값을 VARIANTARG에 대 한 적절 한 어떤 방식으로든 패키지 해야 합니다.

이 함수의 기본 클래스 구현을 명령 대상과 연결 된 OLE_COMMAND_MAP 구조 탐색를 적절 한 처리기를 명령 디스패치 하려고 합니다. 기본 클래스 구현을 인수를 수락 하거나 값을 반환 하지 않는 명령 에서만 작동 합니다. 인수 또는 반환 값을 수행 하는 명령을 처리 해야 할 경우이 함수를 재정의 하 고 사용 해야 합니다 *pvarargIn* 하 고 *pvarargOut* 매개 변수 직접.

##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate

컨테이너 응용 프로그램의 프레임 창이 활성화 또는 비활성화 하는 경우이 함수를 호출 하는 프레임 워크입니다.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
프레임 창 활성화 또는 비활성화 될 지 여부를 지정 합니다.

### <a name="remarks"></a>설명

기본 구현은 프레임 창에 있을 수 있는 도움말 모드를 취소 합니다. 프레임 창이 활성화 또는 비활성화 하는 경우에 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다.

자세한 내용은 문서 참조 [활성화](../../mfc/activation-cpp.md)...

##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem

컨테이너 응용 프로그램을 작성 또는 포함 된 항목을 편집 하는 서버 응용 프로그램을 호출할 때 프레임 워크에서 호출 합니다.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>반환 값

전체 문서를 나타내는 항목에 대 한 포인터 작업에 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

기본 구현은 없습니다. 전체 문서를 나타내는 항목을 반환 하려면이 함수를 재정의 해야 합니다. 이 반환 값은 개체 여야 합니다.는 `COleServerItem`-클래스를 파생 합니다.

##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo

프레임 워크 내부에서 활성화, 변경 및 이후에 비활성화 된 항목에 대 한 변경 내용을 취소 하려면 사용자가이 함수를 호출 합니다.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행 하지 실패를 나타내는 FALSE를 반환 하는 제외 합니다.

응용 프로그램이 실행 취소를 지 원하는 경우이 함수를 재정의 합니다. 일반적으로 실행 취소 작업을 수행 하면 호출 하 여 항목을 활성화 `ActivateInPlace`합니다. Microsoft Foundation Class 라이브러리를 사용 하 여 컨테이너 응용 프로그램에 기록 호출 `COleClientItem::ReactivateAndUndo` 이 함수를 호출할 수 있습니다.

##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder

컨테이너 응용 프로그램의 프레임 창 크기를 변경 하는 경우이 함수를 호출 하는 프레임 워크입니다.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>매개 변수

*lpRectBorder*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 테두리 좌표를 지정 하는 개체입니다.

*lpUIWindow*<br/>
클래스의 개체에 대 한 포인터 `IOleInPlaceUIWindow` 현재 전체 편집 세션을 소유 하는 합니다.

*bFrame*<br/>
TRUE 이면 *lpUIWindow* 컨테이너 응용 프로그램의 최상위 프레임 창 또는 경우에는 FALSE를 가리키는 *lpUIWindow* 컨테이너 응용 프로그램의 문서 수준 프레임 창을 가리킵니다.

### <a name="remarks"></a>설명

이 함수는 크기를 조정 하 고 도구 모음 및 새 창 크기에 따라 다른 사용자 인터페이스 요소를 조정 합니다.

자세한 내용은 [IOleInPlaceUIWindow](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceuiwindow) Windows SDK에 있습니다.

이 고급 재정의할 수 있습니다.

##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames

컨테이너 설정 하거나이 문서에 대 한 호스트 이름을 변경 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>매개 변수

*lpszHost*<br/>
컨테이너 응용 프로그램의 이름을 지정 하는 문자열에 대 한 포인터입니다.

*lpszHostObj*<br/>
문서에 대 한 컨테이너의 이름을 지정 하는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 문서를 참조 하는 모든 보기에 대 한 문서 제목을 변경 하는 기본 구현입니다.

응용 프로그램이 다른 메커니즘을 통해 제목을 설정 하는 경우이 함수를 재정의 합니다.

##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects

프레임 워크의 내부 편집 프레임 창 컨테이너 응용 프로그램의 프레임 창 내에서 위치로이 함수를 호출 합니다.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 전체 프레임 창의 위치를 지정 하는 개체입니다.

*lpClipRect*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 전체 프레임 창의 클리핑 사각형을 지정 하는 개체입니다.

### <a name="remarks"></a>설명

필요한 경우 보기의 확대/축소 비율을 업데이트 하는이 함수를 재정의 합니다.

이 함수는 일반적으로 대 한 응답으로 호출을 `RequestPositionChange` 컨테이너 내부 항목에 대 한 위치 변경 요청에 의해 언제 든 지 호출할 수 있지만 호출 합니다.

##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars

이 함수에서 식별 된 프레임 창과 연결 된 서버 응용 프로그램의 컨트롤 막대 표시 또는 숨기기를 호출 하는 프레임 워크 *pFrameWnd*합니다.

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*pFrameWnd*<br/>
해당 컨트롤 막대를 숨기 거 나 표시 해야 프레임 창에 대 한 포인터입니다.

*bShow*<br/>
컨트롤 막대는 표시 하거나 숨길 여부를 결정 합니다.

### <a name="remarks"></a>설명

기본 구현은 해당 프레임 창을 소유 하는 모든 컨트롤 막대를 열거 하 고 숨기 거 나 표시 합니다.

##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument

프레임 워크 호출을 `OnShowDocument` 서버 문서를 숨기 거 나 표시 해야 하는 경우에 작동 합니다.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
문서에 사용자 인터페이스를 표시 하거나 숨길 수 있는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

하는 경우 *bShow* 가 TRUE 이면 기본 구현에서는 필요한 경우 서버 응용 프로그램을 활성화 하 고 항목은 볼 수 있도록 해당 창을 스크롤하여 컨테이너 응용 프로그램이 있습니다. 하는 경우 *bShow* 은 FALSE를 호출 하 여 항목을 비활성화 하는 기본 구현은 `OnDeactivate`삭제 한 다음, 첫 번째 문서에 대해 생성 된 모든 프레임 창을 숨깁니다. 표시 문서가 유지 하는 경우 기본 구현에서는 서버 응용 프로그램을 숨깁니다.

##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument

복합 문서에 포함 된 항목은 문서를 저장 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>반환 값

0이 아닌 문서 업데이트 되었습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현 호출 합니다 [COleServerDoc::NotifySaved](#notifysaved) 및 [COleServerDoc::SaveEmbedding](#saveembedding) 멤버 함수와 다음 깨끗 문서를 표시 합니다. 수행 하려는 특수 포함 된 항목을 업데이트 하는 경우를 처리 하는 경우이 함수를 재정의 합니다.

##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange

컨테이너 응용 프로그램을 항목의 위치를 변경 하려면이 멤버 함수를 호출 합니다.

```
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>매개 변수

*lpPosRect*<br/>
에 대 한 포인터를 `RECT` 구조 또는 `CRect` 항목의 새 위치를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 호출 (함께에서 `UpdateAllItems`) 내부 활성 항목에서 데이터가 변경 된 경우. 이 호출은 다음 컨테이너 수 또는 호출 하 여 변경 내용을 수행할 수 없는 `OnSetItemRects`합니다. 결과 위치는 요청 된에서 달라질 수 있습니다.

##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding

컨테이너 응용 프로그램에서 포함된 된 개체를 저장 하도록 하려면이 함수를 호출 합니다.

```
void SaveEmbedding();
```

### <a name="remarks"></a>설명

이 함수에서 자동으로 호출 됩니다 `OnUpdateDocument`합니다. 이 함수는 일반적으로 특정 사용자 작업 결과로 호출 되므로 디스크에서 업데이트할 항목을 발생 시키는 참고 합니다.

##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy

호출 된 `ScrollContainerBy` 멤버 함수 컨테이너 문서 크기를 픽셀에서 스크롤 막대를 나타내는 `sizeScroll`합니다.

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>매개 변수

*sizeScroll*<br/>
컨테이너 문서 스크롤해야 나타냅니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

양수를 오른쪽 아래로 스크롤 지정 음수 값 및를 왼쪽으로 스크롤을 나타냅니다.

##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems

문서 변경 된 문서에 연결 된 모든 연결 된 항목을 알리지이 함수를 호출 합니다.

```
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
문서를 수정 하는 항목에 대 한 포인터 또는 모든 항목을 업데이트 하려는 경우 NULL입니다.

*lHint*<br/>
수정에 대 한 정보를 포함합니다.

*pHint*<br/>
수정에 대 한 정보를 저장 하는 개체에 대 한 포인터입니다.

*nDrawAspect*<br/>
항목을 그릴 수 있도록 하는 방법을 확인 합니다. 이것이 DVASPECT 열거형의 값입니다. 이 매개 변수는 다음 값 중 하나를 가질 수 있습니다.

- DVASPECT_CONTENT 항목은 해당 컨테이너 내에서 포함 된 개체로 표시할 수 있습니다 하는 방식으로 표시 됩니다.

- 검색 도구에 표시 될 수 있도록 "미리 보기" 표현에서 DVASPECT_THUMBNAIL 항목이 렌더링 됩니다.

- DVASPECT_ICON 항목 아이콘으로 표시 됩니다.

- 파일 메뉴에서 인쇄 명령을 사용 하 여 인쇄할 때 처럼 DVASPECT_DOCPRINT 항목이 표시 됩니다.

### <a name="remarks"></a>설명

일반적으로 사용자는 서버 문서를 변경한 후이 함수를 호출 합니다. OLE 항목은 자동 링크를 사용 하 여 문서에 연결 된, 항목의 변경 내용을 반영 하도록 업데이트 됩니다. Microsoft Foundation Class 라이브러리를 사용 하 여 작성 하는 컨테이너 응용 프로그램에는 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) 멤버 함수 `COleClientItem` 라고 합니다.

이 함수를 호출 합니다 `OnUpdate` 각 항목, 전달 전송을 제외한 문서 항목에 대해 멤버 함수 *pHint*를 *lHint*, 및 *nDrawAspect*합니다. 이러한 매개 변수를 사용 하 여 문서에 대 한 수정에 대 한 항목 정보를 전달. 사용 하 여 정보를 인코딩할 수 있습니다 *lHint* 하거나 정의할 수 있습니다를 `CObject`-수정에 대 한 정보를 저장 하 고 사용 하 여 해당 클래스의 개체를 전달 하는 클래스를 파생 *pHint*합니다. 재정의 된 `OnUpdate` 멤버 함수에 `COleServerItem`-표시 변경 되었는지 여부에 따라 각 항목의 업데이트를 최적화 하는 클래스를 파생 합니다.

## <a name="see-also"></a>참고자료

[MFC Sample HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[COleLinkingDoc 클래스](../../mfc/reference/colelinkingdoc-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleDocument 클래스](../../mfc/reference/coledocument-class.md)<br/>
[COleLinkingDoc 클래스](../../mfc/reference/colelinkingdoc-class.md)<br/>
[COleTemplateServer 클래스](../../mfc/reference/coletemplateserver-class.md)
