---
title: CDocument 클래스
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: 2d87ff67000fb5b70c0a5c965638875e6f50b22c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774185"
---
# <a name="cdocument-class"></a>CDocument 클래스

사용자 정의 문서 클래스에 대한 기본 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDocument::CDocument](#cdocument)|`CDocument` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDocument::AddView](#addview)|문서에 뷰를 연결합니다.|
|[CDocument::BeginReadChunks](#beginreadchunks)|초기화 읽기를 청크 합니다.|
|[CDocument::CanCloseFrame](#cancloseframe)|고급 재정의할 수 있습니다. 이 문서를 확인 하는 프레임 창을 닫기 전에 호출 됩니다.|
|[CDocument::ClearChunkList](#clearchunklist)|청크 목록을 지웁니다.|
|[CDocument::ClearPathName](#clearpathname)|문서 개체의 경로 지웁니다.|
|[CDocument::DeleteContents](#deletecontents)|문서의 정리를 수행 하기 위해 호출 됩니다.|
|[CDocument::FindChunk](#findchunk)|지정 된 GUID 사용 하 여 청크를 찾습니다.|
|[CDocument::GetAdapter](#getadapter)|구현 하는 개체에 대 한 포인터를 반환 합니다. `IDocument` 인터페이스입니다.|
|[CDocument::GetDocTemplate](#getdoctemplate)|문서 형식을 설명 하는 서식 파일에 대 한 포인터를 반환 합니다.|
|[CDocument::GetFile](#getfile)|포인터를 원하는 반환 `CFile` 개체입니다.|
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|첫 번째 위치를 반환 합니다. 뷰의; 목록에서 반복을 시작 하는 데 사용 합니다.|
|[CDocument::GetNextView](#getnextview)|뷰는 문서와 연결 된 목록을 반복 합니다.|
|[CDocument::GetPathName](#getpathname)|문서 데이터 파일의 경로 반환합니다.|
|[CDocument::GetThumbnail](#getthumbnail)|미리 보기를 표시할 축소판 그림 공급자에서 사용할 비트맵 만들기 위해 호출 됩니다.|
|[CDocument::GetTitle](#gettitle)|문서의 제목을 반환합니다.|
|[CDocument::InitializeSearchContent](#initializesearchcontent)|검색 처리기에 대 한 콘텐츠 검색을 초기화 하기 위해 호출 됩니다.|
|[CDocument::IsModified](#ismodified)|문서 마지막으로 저장 된 이후 수정 되었는지 여부를 나타냅니다.|
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|지시 하는지 여부를이 인스턴스의 `CDocument` 개체 검색 및 구성 처리기에 대해 생성 된 합니다.|
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|스트림에서 문서 데이터를 로드 하기 위해 호출 됩니다.|
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|다양 한 미리 보기 글꼴 변경 되기 전에 호출 됩니다.|
|[CDocument::OnChangedViewList](#onchangedviewlist)|보기에 추가 하거나 문서에서 제거 된 후 호출 됩니다.|
|[CDocument::OnCloseDocument](#onclosedocument)|문서를 닫기 위해 호출 됩니다.|
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|다양 한 미리 보기에 대 한 미리 보기 프레임을 만들도록 할 때 프레임 워크에서 호출 됩니다.|
|[CDocument::OnDocumentEvent](#ondocumentevent)|문서 이벤트에 대 한 응답으로 프레임 워크에서 호출 됩니다.|
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|미리 보기의 콘텐츠를 그릴 파생된 클래스에서이 메서드를 재정의 합니다.|
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|스트림에서 문서 데이터를 로드 해야 할 때 프레임 워크에서 호출 됩니다.|
|[CDocument::OnNewDocument](#onnewdocument)|새 문서를 작성 하기 위해 호출 됩니다.|
|[CDocument::OnOpenDocument](#onopendocument)|기존 문서 열기 위해 호출 됩니다.|
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|GetFocus 함수 호출에서 HWND를 반환 하는 미리 보기 처리기를 전달 합니다.|
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|미리 보기 처리기를 실행 하는 프로세스의 메시지 펌프에서 전달 하는 키 입력을 처리 하는 미리 보기 처리기를 전달 합니다.|
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|다양 한 미리 보기 배경 색이 변경 되 면 호출 됩니다.|
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|다양 한 미리 보기 글꼴 변경 될 때 호출 됩니다.|
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|다양 한 미리 보기 사이트 변경 될 때 호출 됩니다.|
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|다양 한 미리 보기 텍스트 색이 변경 되 면 호출 됩니다.|
|[CDocument::OnSaveDocument](#onsavedocument)|문서 디스크를 저장 하기 위해 호출 됩니다.|
|[CDocument::OnUnloadHandler](#onunloadhandler)|미리 보기 처리기 언로드되는 때 프레임 워크에서 호출 됩니다.|
|[CDocument::PreCloseFrame](#precloseframe)|프레임 창을 닫기 전에 호출 됩니다.|
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|다음 청크 값을 읽습니다.|
|[CDocument::ReleaseFile](#releasefile)|다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 파일을 해제 합니다.|
|[CDocument::RemoveChunk](#removechunk)|지정 된 GUID 사용 하 여 청크를 제거합니다.|
|[CDocument::RemoveView](#removeview)|문서에서 보기를 분리합니다.|
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|고급 재정의할 수 있습니다. 열려 있는 경우 호출 되거나 저장 작업이 예외로 인해 완료할 수 없습니다.|
|[CDocument::SaveModified](#savemodified)|고급 재정의할 수 있습니다. 문서를 저장할지 여부를 사용자에 게 요청 하기 위해 호출 됩니다.|
|[CDocument::SetChunkValue](#setchunkvalue)|청크 값을 설정 합니다.|
|[CDocument::SetModifiedFlag](#setmodifiedflag)|마지막으로 저장 되므로 문서를 수정 했습니다 나타내는 플래그를 설정 합니다.|
|[CDocument::SetPathName](#setpathname)|문서에 사용 된 데이터 파일의 경로 설정 합니다.|
|[CDocument::SetTitle](#settitle)|문서 제목을 설정합니다.|
|[CDocument::UpdateAllViews](#updateallviews)|수정 된 문서는 모든 보기에 알립니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CDocument::OnFileSendMail](#onfilesendmail)|연결 된 문서와 메일 메시지를 보냅니다.|
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|메일 지원 있으면 메일 보내기 명령을 활성화 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|지정 `CDocument` dllhost 미리 보기에 대 한 개체가 있습니다. 체크 인 않아야 `CView::OnDraw`합니다.|
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|형식임 `CDocument` 개체에 대 한 prevhost 만들어졌거나 `Rich Preview`합니다. 체크 인 않아야 `CView::OnDraw`합니다.|
|[CDocument::m_bSearchMode](#m_bsearchmode)|지정 `CDocument` 인덱서 또는 다른 검색 응용 프로그램에서 생성 된 개체입니다.|
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|다양 한 미리 보기 창의 배경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.|
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|다양 한 미리 보기 창의 전경색을 지정합니다. 이 색은 호스트에 의해 설정 됩니다.|
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|다양 한 미리 보기 창에 대 한 텍스트 글꼴을 지정합니다. 이 글꼴 정보는 호스트에 의해 설정 됩니다.|

## <a name="remarks"></a>설명

문서를 일반적으로 파일 열기 명령을 사용 하 여 열고 파일 저장 명령을 사용 하 여 저장 하는 데이터의 단위를 나타냅니다.

`CDocument` 문서 만들기, 로드, 저장 등 표준 작업을 지원 합니다. 프레임 워크에서 정의 된 인터페이스를 사용 하 여 문서를 조작 `CDocument`합니다.

응용 프로그램에서 둘 이상의 유형의 문서를 지원할 수 있습니다. 예를 들어, 응용 프로그램에 스프레드시트 및 텍스트 문서를 모두 지원할 수 있습니다. 각 형식의 문서에 연결 된 문서 템플릿; 문서 템플릿에 해당 형식의 문서에 대해 사용 되는 리소스 (예: 메뉴, 아이콘 또는 액셀러레이터 키 테이블)을 지정 합니다. 해당 연결에 대 한 포인터를 포함 하는 각 문서 `CDocTemplate` 개체입니다.

사용자를 통해 문서와 상호 작용 합니다 [CView](../../mfc/reference/cview-class.md) 연결 된 개체입니다. 뷰를 문서 프레임 창에 이미지를 렌더링 하 고 문서에 대 한 작업으로 사용자 입력을 해석 합니다. 문서에 연결 된 여러 뷰가 있을 수 있습니다. 사용자가 문서에 표시 된 창을 열면 프레임 워크는 뷰를 만들고 문서에 연결 합니다. 문서 템플릿을 각 형식의 문서를 표시 하 되는 뷰 및 프레임 창의 유형을 지정 합니다.

프레임 워크의 표준의 일부인 문서 라우팅 명령 및 결과적으로 표준 사용자 인터페이스 구성 요소 (예: 파일 저장 메뉴 항목)에서 명령을 수신 합니다. 문서를 현재 보기에서 전달 된 명령을 받습니다. 문서에서 지정된 된 명령을 처리 하지 않는 경우이 관리 하는 서식 파일에 명령을 전달 합니다.

문서의 데이터가 수정 되 면 이러한 수정 내용을 반영 해야 각 해당 보기. `CDocument` 제공 된 [UpdateAllViews](#updateallviews) 멤버 함수가 보기 수 자동으로 그려지도록 필요에 따라 하므로 이러한 변경 사항을 보기를 알릴 수 있습니다. 프레임 워크는 또한 수정 된 파일을 닫기 전에 저장 하 라는입니다.

일반적인 응용 프로그램에서 문서를 구현 하려면 다음을 수행 해야 합니다.

- 클래스를 파생 `CDocument` 각 문서 유형에 대 한 합니다.

- 각 문서의 데이터를 저장 하는 멤버 변수를 추가 합니다.

- 읽기 및 문서 데이터 수정에 대 한 멤버 함수를 구현 합니다. 문서의 뷰는 이러한 멤버 함수 중 가장 중요 한 사용자입니다.

- 재정의 된 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 문서의 데이터를 디스크에서 읽고 쓰는 데 문서 클래스에서 멤버 함수입니다.

`CDocument` 메일 지원 (MAPI)이 있으면 메일을 통해 문서 전송을 지원 합니다. 문서를 참조 하세요 [MAPI](../../mfc/mapi.md) 하 고 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.

에 대 한 자세한 `CDocument`를 참조 하세요 [Serialization](../../mfc/serialization-in-mfc.md)를 [문서/뷰 아키텍처 항목](../../mfc/document-view-architecture.md), 및 [문서/뷰 만들기](../../mfc/document-view-creation.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="addview"></a>  CDocument::AddView

문서에 뷰를 연결 하려면이 함수를 호출 합니다.

```
void AddView(CView* pView);
```

### <a name="parameters"></a>매개 변수

*pView*<br/>
추가 되 고 보기를 가리킵니다.

### <a name="remarks"></a>설명

이 함수는 지정 된 뷰를 문서와 관련 된 보기 목록에 추가 또한 함수는이 문서 보기의 문서 포인터를 설정합니다. 프레임 워크가 문서;에 새로 만든된 뷰 개체를 연결 하는 경우이 함수를 호출 이 창에 분할 될 때 또는 새 파일, 파일 열기, 또는 새 창 명령에 대 한 응답으로 발생 합니다.

수동으로 만들고 뷰를 연결 하는 경우에이 함수를 호출 합니다. 일반적으로 프레임 워크를 정의 하 여 문서 및 뷰를 연결 하면 한 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 문서 클래스, 클래스 뷰 및 프레임 창 클래스를 연결 하는 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks

초기화 읽기를 청크 합니다.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>설명

##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame

문서를 표시 하는 프레임 창 닫히기 전에 프레임 워크에서 호출 됩니다.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
문서에 연결 하는 보기의 프레임 창을 가리킵니다.

### <a name="return-value"></a>반환 값

프레임 창을; 닫으려면 안전 하 고 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 프레임 창과 문서를 표시 되어 있는지 확인 합니다. 지정 된 프레임 창 개가 문서를 표시 하는 경우 함수 사용자가 수정 된 경우 문서를 저장 하 라는 메시지가 표시 됩니다. 프레임 창의 닫을 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 이 고급 재정의할 수 있습니다.

##  <a name="cdocument"></a>  CDocument::CDocument

`CDocument` 개체를 생성합니다.

```
CDocument();
```

### <a name="remarks"></a>설명

프레임 워크에는 문서 만들기를 처리합니다. 재정의 [OnNewDocument](#onnewdocument) 문서별 기준 초기화를 수행 하는 멤버 함수는 단일 문서 인터페이스 (SDI) 응용 프로그램에서 특히 중요 합니다.

##  <a name="clearchunklist"></a>  CDocument::ClearChunkList

청크 목록을 지웁니다.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>설명

##  <a name="clearpathname"></a>  CDocument::ClearPathName

문서 개체의 경로 지웁니다.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>설명

지우기 경로 `CDocument` 개체 하면 응용 프로그램이 문서를 저장한 다음 사용자를 표시 합니다. 이렇게 하면를 **저장** 명령 처럼를 **다른 이름으로 저장** 명령입니다.

##  <a name="deletecontents"></a>  CDocument::DeleteContents

제거 하지 않고 문서의 데이터를 삭제 하기 위해 프레임 워크에서 호출 된 `CDocument` 개체 자체입니다.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>설명

문서가 소멸 되기 직전 호출 됩니다. 이 재사용 되기 전에 문서 비어 있는지 확인 하는 것이 라고도 합니다. 이 특히 중요 한 문서를 사용 하 여 SDI 응용 프로그램에 대 한 문서에는 사용자가 만들거나 다른 문서를 열 때마다 다시 사용 됩니다. "편집 모두 지우기" 또는 모든 문서의 데이터를 삭제 하는 유사한 명령을 구현 하려면이 함수를 호출 합니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 문서에서 데이터를 삭제 하려면이 함수를 재정의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="findchunk"></a>  CDocument::FindChunk

지정 된 GUID 사용 하 여 청크를 찾습니다.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>매개 변수

*guid*<br/>
찾을 청크의 GUID를 지정 합니다.

*pid*<br/>
찾으려는 청크의 PID를 지정 합니다.

### <a name="return-value"></a>반환 값

성공 하는 경우 내부 청크 목록의 위치입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="getadapter"></a>  CDocument::GetAdapter

구현 하는 개체에 대 한 포인터를 반환 합니다 `IDocument` 인터페이스입니다.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>반환 값

구현 하는 개체에 대 한 포인터를 `IDocument` 인터페이스입니다.

### <a name="remarks"></a>설명

##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate

이 문서 유형에 대 한 서식 파일에 대 한 포인터를 가져오려면이 함수를 호출 합니다.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>반환 값

이 문서 형식 또는 문서를 문서 템플릿에 의해 관리 되지 않는 경우 NULL에 대 한 서식 파일에 대 한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="getfile"></a>  CDocument::GetFile

에 대 한 포인터를 가져오려면이 멤버 함수 호출을 `CFile` 개체입니다.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
문자열은 원하는 파일을 경로입니다. 상대 또는 절대 경로일 수 있습니다.

*pError*<br/>
작업의 완료 상태를 표시 하는 기존 파일 예외 개체에 대 한 포인터입니다.

*nOpenFlags*<br/>
공유 및 액세스 모드입니다. 파일을 열 때 수행할 동작을 지정 합니다. CFile 생성자에 나열 된 옵션을 결합할 수 있습니다 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) 비트 OR를 사용 하 여 (&#124;) 연산자. 에 대 한 액세스 권한과 하나 공유 옵션은 필요한; 합니다 `modeCreate` 고 `modeNoInherit` 모드는 선택 사항입니다.

### <a name="return-value"></a>반환 값

`CFile` 개체에 대한 포인터입니다.

##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition

문서와 관련 된 보기 목록에서 첫 번째 보기의 위치를 가져오려면이 함수를 호출 합니다.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>반환 값

반복에 대해 사용할 수 있는 위치 값을 [GetNextView](#getnextview) 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getnextview"></a>  CDocument::GetNextView

문서 보기의 모든 반복 하려면이 함수를 호출 합니다.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
에 대 한 이전 호출에서 반환 된 위치 값에 대 한 참조를 `GetNextView` 나 [GetFirstViewPosition](#getfirstviewposition) 멤버 함수입니다. 이 값에 NULL이 아니어야 합니다.

### <a name="return-value"></a>반환 값

로 식별 되는 보기에 대 한 포인터 *rPosition*합니다.

### <a name="remarks"></a>설명

로 식별 되는 뷰를 반환 하는 함수 *rPosition* 설정한 *rPosition* 목록의 다음 뷰의 위치 값입니다. 검색된 보기는 목록에서 마지막 *rPosition* NULL로 설정 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getpathname"></a>  CDocument::GetPathName

문서의 디스크 파일의 정규화 된 경로 가져오려면이 함수를 호출 합니다.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>반환 값

문서의 정규화 된 경로입니다. 문서 저장 되지 않은 또는 연결 된 디스크 파일에 없는 경우이 문자열이 비어 있습니다.

##  <a name="getthumbnail"></a>  CDocument::GetThumbnail

미리 보기를 표시할 축소판 그림 공급자에서 사용할 비트맵을 만듭니다.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>매개 변수

*cx*<br/>
비트맵의 높이 너비를 지정합니다.

*phbmp*<br/>
함수는 성공적으로 반환 하는 경우 비트맵에 대 한 핸들을 포함 합니다.

*pdwAlpha*<br/>
함수가 성공적으로 반환할 때 알파 채널 값을 지정 하는 DWORD를 포함 합니다.

### <a name="return-value"></a>반환 값

미리 보기에 대 한 비트맵 있으면 TRUE를 반환을 만들었습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="gettitle"></a>  CDocument::GetTitle

일반적으로 해당 문서의 파일 이름에서 파생 되는 문서의 제목을 가져오려면이 함수를 호출 합니다.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>반환 값

문서의 제목입니다.

##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent

검색 처리기에 대 한 콘텐츠 검색을 초기화 하기 위해 호출 됩니다.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>설명

콘텐츠 검색을 초기화 하는 파생된 클래스에서이 메서드를 재정의 합니다. 콘텐츠를 구분 하는 파트를 사용 하 여 문자열 이어야 합니다 ";"입니다. 예를 들어, "point; 직사각형을 그립니다. ole 항목 "입니다.

##  <a name="ismodified"></a>  CDocument::IsModified

문서 마지막으로 저장 된 이후 수정 되었는지 여부를 결정 하는이 함수를 호출 합니다.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>반환 값

문서 마지막으로 저장 된 이후 수정 되었는지 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler

지시 하는지 여부를이 인스턴스의 `CDocument` 검색 및 구성 처리기에 대해 생성 된 합니다.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>반환 값

반환 TRUE 이면이 인스턴스의 `CDocument` 검색 및 구성 처리기에 대 한 생성 되었습니다.

### <a name="remarks"></a>설명

현재이 함수는 아웃 프로세스 서버에서 구현 되는 다양 한 미리 보기 처리기에 대해서만 TRUE를 반환 합니다. 이 함수가 TRUE를 반환 하면 응용 프로그램 수준 (m_bPreviewHandlerMode, m_bSearchMode m_bGetThumbnailMode) 적절 한 플래그를 설정할 수 있습니다.

##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream

스트림에서 문서 데이터를 로드 하기 위해 호출 됩니다.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
스트림에 대 한 포인터입니다. 이 스트림에 셸에서 제공 됩니다.

*dwGrfMode*<br/>
스트림에 액세스 모드입니다.

### <a name="return-value"></a>반환 값

로드 작업이 성공 하면이 고 그렇지 HRESULT 오류 코드를 사용 하 여 S_OK입니다.

### <a name="remarks"></a>설명

스트림에서 데이터를 로드 하는 방법을 사용자 지정 파생된 클래스에서이 메서드를 재정의할 수 있습니다.

##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode

지정 된 `CDocument` 미리 보기에 대 한 dllhost에서 개체가 만들어졌는지 합니다. 체크 인 않아야 `CView::OnDraw`합니다.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>설명

`TRUE` 문서 미리 보기에 대 한 dllhost으로 만들어졌음을 나타냅니다.

##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode

지정 된 `CDocument` for Rich Preview prevhost에서 개체가 만들어졌는지 합니다. 체크 인 않아야 `CView::OnDraw`합니다.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>설명

TRUE for Rich Preview prevhost 하 여 문서를 만든 것을 나타냅니다.

##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode

지정 된 `CDocument` 인덱서 또는 다른 검색 응용 프로그램에서 개체가 만들어진 합니다.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>설명

`TRUE` 인덱서 또는 다른 검색 응용 프로그램에서 문서 만들어졌음을 나타냅니다.

##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor

다양 한 미리 보기 창의 배경색을 지정 합니다. 이 색은 호스트에 의해 설정 됩니다.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>설명

##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor

다양 한 미리 보기 창의 전경색을 지정 합니다. 이 색은 호스트에 의해 설정 됩니다.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>설명

##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont

다양 한 미리 보기 창에 대 한 텍스트 글꼴을 지정합니다. 이 글꼴 정보는 호스트에 의해 설정 됩니다.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>설명

##  <a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged

다양 한 미리 보기 글꼴 변경 되기 전에 호출 됩니다.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>설명

##  <a name="onchangedviewlist"></a>  CDocument::OnChangedViewList

보기에 추가 하거나 문서에서 제거 후에 프레임 워크에서 호출 됩니다.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현은 확인 여부를 마지막 보기 제거 하는 중, 그렇다면 문서를 삭제 합니다. 프레임 워크를 추가 하거나 뷰를 제거 하는 경우에 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어, 문서에 연결 하는 뷰가 없습니다. 필요한 경우에 열려를 원한다 면이 함수를 재정의 합니다.

##  <a name="onclosedocument"></a>  CDocument::OnCloseDocument

문서가 닫힐 때 일반적으로 파일 닫기 명령의 일부로 프레임 워크에서 호출 됩니다.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현은 모든 문서를 확인에 사용 되는 프레임을 제거, 보기를 닫습니다, 문서의 콘텐츠를 정리 및 호출 된 [DeleteContents](#deletecontents) 멤버 함수는 문서를 삭제 하려면 데이터입니다.

프레임 워크 문서를 닫을 때 처리 하는 특별 한 정리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어, 문서 데이터베이스에서 레코드를 나타내는 경우이 함수는 데이터베이스를 재정의 하는 것이 좋습니다. 재정의에서이 함수의 기본 클래스 버전을 호출 해야 합니다.

##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame

다양 한 미리 보기에 대 한 미리 보기 프레임을 만들도록 할 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>반환 값

프레임이 성공적으로 생성 된 경우 TRUE를 반환합니다 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent

문서 이벤트에 대 한 응답으로 프레임 워크에서 호출 됩니다.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>매개 변수

*deEvent*<br/>
[in] 이벤트의 형식을 설명 하는 열거형된 데이터 형식입니다.

### <a name="remarks"></a>설명

문서 이벤트 여러 클래스에 영향을 줄 수 있습니다. 이 메서드는 이외의 클래스에 영향을 주는 문서 이벤트를 처리 하는 일을 담당 합니다 [CDocument 클래스](../../mfc/reference/cdocument-class.md)합니다. 현재 문서 이벤트에 응답 해야 하는 유일한 클래스는 합니다 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다. 합니다 `CDocument` 클래스 메서드가 다른 재정의할 수 있습니다에 결과 처리 하는 일을 담당 합니다 `CDocument`합니다.

다음 표에서 대 한 가능한 값 *deEvent* 및 해당 하는 이벤트입니다.

|값|해당 이벤트|
|-----------|-------------------------|
|`onAfterNewDocument`|새 문서를 만들었습니다.|
|`onAfterOpenDocument`|새 문서를 열었습니다.|
|`onAfterSaveDocument`|문서를 저장 합니다.|
|`onAfterCloseDocument`|문서가 닫혔습니다.|

##  <a name="ondrawthumbnail"></a>  CDocument::OnDrawThumbnail

축소판 그림을 그릴 파생된 클래스에서이 메서드를 재정의 합니다.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
장치 컨텍스트에 대 한 참조입니다.

*lprcBounds*<br/>
미리 보기 그려야 영역의 경계 사각형을 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="onfilesendmail"></a>  CDocument::OnFileSendMail

메시지를 보냅니다 상주 메일 호스트를 통해 (있는 경우) 문서와 첨부 파일로.

```
void OnFileSendMail();
```

### <a name="remarks"></a>설명

`OnFileSendMail` 호출 [OnSaveDocument](#onsavedocument) (저장) 한 다음 전자 메일을 통해 전송 되는 임시 파일에 제목이 없는 및 수정 된 문서를 serialize 하 합니다. 문서를 수정 하지 않았으면, 임시 파일 필요 하지 않습니다. 원래 전송 됩니다. `OnFileSendMail` MAPI32를 로드합니다. DLL 로드 되지 않았으면입니다.

구현 하는 특수 `OnFileSendMail` 에 대 한 [COleDocument](../../mfc/reference/coledocument-class.md) 복합 파일 올바르게 처리 합니다.

`CDocument` 메일 지원 (MAPI)이 있으면 메일을 통해 문서 전송을 지원 합니다. 문서를 참조 하세요 [MAPI 항목](../../mfc/mapi.md) 하 고 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.

##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream

스트림에서 문서 데이터를 로드 해야 할 때 프레임 워크에서 호출 됩니다.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
들어오는 스트림에 대 한 포인터입니다.

*grfMode*<br/>
스트림에 액세스 모드입니다.

### <a name="return-value"></a>반환 값

부하에 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

##  <a name="onnewdocument"></a>  CDocument::OnNewDocument

새 파일 명령 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>반환 값

0이 아닌 문서를 초기화 했습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현을 호출 합니다 [DeleteContents](#deletecontents) 문서 비어 및 그런 다음 새 문서를 정리으로 표시 되도록 멤버 함수입니다. 새 문서에 대 한 데이터 구조를 초기화 하려면이 함수를 재정의 합니다. 재정의에서이 함수의 기본 클래스 버전을 호출 해야 합니다.

SDI 응용 프로그램에서 새 파일 명령을 선택한 경우에 프레임 워크 새로 만드는 대신 기존 문서를 다시 초기화 하려면이 함수를 사용 합니다. 사용자가 여러 문서 MDI (인터페이스) 응용 프로그램에서 새 파일을 한 경우 프레임 워크 될 때마다 새 문서를 만들고 및 초기화 하려면이 함수를 호출 합니다. SDI 응용 프로그램에 적용 되도록 새 파일 명령에 대 한 생성자에서이 함수 대신에 초기화 코드를 배치 해야 합니다.

에서는 인 사례 `OnNewDocument` 두 번 호출 됩니다. 이 문서는 ActiveX 문서 서버로 포함 된 경우 발생 합니다. 함수를 먼저 호출한를 `CreateInstance` 메서드 (의해 노출 되는 `COleObjectFactory`-파생 클래스) 및 두 번째는 시간을 `InitNew` 메서드 (에 의해 노출는 `COleServerDoc`-파생 클래스).

### <a name="example"></a>예제

다음 예제에서는 document 개체를 초기화 하는 대체 메서드를 보여 줍니다.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="onopendocument"></a>  CDocument::OnOpenDocument

파일 열기 명령 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
열려는 문서 경로를 가리킵니다.

### <a name="return-value"></a>반환 값

0이 아닌 문서를 로드 했습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 기본 구현 호출 지정된 된 파일을 엽니다는 [DeleteContents](#deletecontents) 문서가 비어 있도록 멤버 함수 호출 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 읽을 파일의 수 콘텐츠를 하 고 깨끗 문서를 표시 합니다. 보관 메커니즘 또는 파일 메커니즘 이외의 것을 사용 하려는 경우이 함수를 재정의 합니다. 예를 들어, 문서 위치 별도 파일이 아니라 데이터베이스의 레코드를 나타내며 응용 프로그램을 작성할 수 있습니다.

이 함수를 사용 하 여 기존 다시 초기화 하도록 프레임 워크 사용자 SDI 응용 프로그램에서 파일 열기 명령을 선택 하면 `CDocument` 새로 만들기 보다는 개체입니다. 프레임 워크가 생성 하는 새 사용자가 MDI 응용 프로그램에서 파일 열기 선택, `CDocument` 때마다 개체 다음 초기화 하는 데이 함수를 호출 합니다. SDI 응용 프로그램에 적용 되도록 파일 열기 명령에 대 한 생성자에서이 함수 대신에 초기화 코드를 배치 해야 합니다.

### <a name="example"></a>예제

다음 예제에서는 document 개체를 초기화 하는 대체 메서드를 보여 줍니다.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus

호출에서 검색 된 HWND를 반환 하는 미리 보기 처리기를 전달 합니다 `GetFocus` 함수입니다.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>매개 변수

*phwnd*<br/>
[out] 이 메서드가 반환 될 때 호출에서 반환 된 HWND에 대 한 포인터를 포함 합니다 `GetFocus` 미리 보기 처리기의 포그라운드 스레드에서 함수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 반환 하거나 그렇지 않으면 오류 값을 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator

미리 보기 처리기를 실행 하는 프로세스의 메시지 펌프에서 전달 하는 키 입력을 처리 하는 미리 보기 처리기를 전달 합니다.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>매개 변수

*pmsg*<br/>
[in] 창 메시지에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

미리 보기 처리기에서 키 입력 메시지를 처리할 수 하는 경우 처리기를 처리 하 고 S_OK를 반환 합니다. 통해 호스트에 제공이 미리 보기 처리기는 키 입력 메시지를 처리할 수 없습니다, 경우 `IPreviewHandlerFrame::TranslateAccelerator`합니다. 호스트에서 메시지를 처리 하는 경우이 메서드는 S_OK를 반환 합니다. 호스트에서 메시지를 처리 하지 않습니다, 경우이 메서드는 S_FALSE를 반환 합니다.

### <a name="remarks"></a>설명

##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged

다양 한 미리 보기 배경색 변경 될 때 호출 됩니다.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>설명

##  <a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged

다양 한 미리 보기 글꼴 변경 될 때 호출 됩니다.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>설명

##  <a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged

다양 한 미리 보기 사이트 변경 될 때 호출 됩니다.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>설명

##  <a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged

다양 한 미리 보기 텍스트 색이 변경 되 면 호출 됩니다.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>설명

##  <a name="onsavedocument"></a>  CDocument::OnSaveDocument

파일 저장 또는 다른 이름으로 저장 명령의 일부로 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
파일을 저장할 수는 정규화 된 경로를 가리킵니다.

### <a name="return-value"></a>반환 값

0이 아닌 문서 저장 되었습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 기본 구현 호출 지정된 된 파일을 엽니다 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 문서의 데이터를 쓸 파일을 선택한 다음 표시로 문서를 정리 합니다. 프레임 워크는 문서를 저장할 때 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어, 문서 위치 별도 파일이 아니라 데이터베이스의 레코드를 나타내며 응용 프로그램을 작성할 수 있습니다.

##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler

미리 보기 처리기 언로드될 때 프레임 워크에서 호출 됩니다.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>설명

##  <a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail

메일 지원 (MAPI)이 있으면 ID_FILE_SEND_MAIL 명령을 활성화 합니다.

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
에 대 한 포인터를 [CCmdUI](../../mfc/reference/ccmdui-class.md) ID_FILE_SEND_MAIL 명령과 연결 된 개체입니다.

### <a name="remarks"></a>설명

그렇지 않으면 함수 위나 아래 메뉴 항목을 적절 하 게 구분 기호를 포함 하 여 메뉴에서 ID_FILE_SEND_MAIL 명령을 제거 합니다. MAPI는 경우 사용할 수 MAPI32 합니다. DLL 경로 및 win [메일] 섹션에 없는 경우 INI 파일, MAPI = 1입니다. 대부분의 응용 프로그램 파일 메뉴에서이 명령을 배치합니다.

`CDocument` 메일 지원 (MAPI)이 있으면 메일을 통해 문서 전송을 지원 합니다. 문서를 참조 하세요 [MAPI 항목](../../mfc/mapi.md) 하 고 [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md)합니다.

##  <a name="precloseframe"></a>  CDocument::PreCloseFrame

이 멤버 함수는 프레임 창을 소멸 되기 전에 프레임 워크에서 호출 됩니다.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
에 대 한 포인터를 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 보유 하는 연결 된 `CDocument` 개체입니다.

### <a name="remarks"></a>설명

사용자 지정 정리를 제공 하 고 기본 클래스도 호출 해야 재정의할 수 있습니다.

기본값인 `PreCloseFrame` 아무 작업도 수행 하지 `CDocument`합니다. 합니다 `CDocument`-파생 클래스 [COleDocument](../../mfc/reference/coledocument-class.md) 하 고 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 이 멤버 함수를 사용 합니다.

##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue

다음 청크 값을 읽습니다.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>매개 변수

*ppValue*<br/>
[out] 함수는 반환 될 때 *ppValue* 읽은 값을 포함 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##  <a name="releasefile"></a>  CDocument::ReleaseFile

이 멤버 함수는 다른 응용 프로그램에서 사용 하기 위해 사용할 수 있도록 파일을 해제 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
릴리스될 CFile 개체에 대 한 포인터입니다.

*bAbort*<br/>
파일을 사용 하 여 출시 될 지 여부를 지정 `CFile::Close` 또는 `CFile::Abort`합니다. 파일을 사용 하 여 해제 되어야 하면 FALSE [CFile::Close](../../mfc/reference/cfile-class.md#close); 파일을 사용 하 여 해제 되어야 하면 TRUE [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.

### <a name="remarks"></a>설명

하는 경우 *bAbort* 가 TRUE 인 `ReleaseFile` 호출 `CFile::Abort`, 파일 해제 됩니다. `CFile::Abort` 예외를 throw 하지 않습니다.

하는 경우 *bAbort* 은 FALSE `ReleaseFile` 호출 `CFile::Close` 파일 해제 됩니다.

파일 해제 되기 전에 사용자가 작업을 요구 하려면이 멤버 함수를 재정의 합니다.

##  <a name="removechunk"></a>  CDocument::RemoveChunk

지정된 된 GUID 사용 하 여 청크를 제거합니다.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>매개 변수

*Guid*<br/>
제거할 청크의 GUID를 지정 합니다.

*Pid*<br/>
제거할 청크의 PID를 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="removeview"></a>  CDocument::RemoveView

문서에서 보기를 분리 하려면이 함수를 호출 합니다.

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>매개 변수

*pView*<br/>
제거할 보기를 가리킵니다.

### <a name="remarks"></a>설명

이 함수는 문서와 관련 된 보기 목록에서 지정 된 뷰를 제거 합니다. 또한 뷰의 문서 포인터를 NULL로 설정합니다. 이 함수는 프레임 창이 닫힐 또는 분할자 창 창이 닫힐 때 프레임 워크에서 호출 됩니다.

보기를 수동으로 분리 된 경우에이 함수를 호출 합니다. 일반적으로 프레임 워크를 정의 하 여 문서 및 뷰를 분리 하면 한 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 문서 클래스, 클래스 뷰 및 프레임 창 클래스를 연결 하는 개체입니다.

예제를 참조 하세요 [AddView](#addview) 샘플 구현에 대 한 합니다.

##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException

예외가 throw 되 면 호출 됩니다 (일반적으로 [CFileException](../../mfc/reference/cfileexception-class.md) 또는 [CArchiveException](../../mfc/reference/carchiveexception-class.md)) 문서를 로드 하거나 저장 하는 동안.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
되는 문서의 이름을 가리키는 저장 되거나 로드 합니다.

*e*<br/>
Throw 된 예외를 가리킵니다. NULL 일 수 있습니다.

*bSaving*<br/>
어떤 작업이 진행에서을 나타내는 플래그입니다. 문서 저장 된 경우 되 고, 0은 문서를 로드 하는 경우에 0이 아닙니다.

*nIDPDefault*<br/>
함수는 더 구체적인 절을 지정 하지 않는 경우 표시할 오류 메시지의 식별자입니다.

### <a name="remarks"></a>설명

기본 구현은 예외 개체를 검사 하 고 원인을 구체적으로 설명 하는 오류 메시지를 찾습니다. 특정 메시지를 찾을 수 없으면 여부나 *e* 가 null 인 경우 지정 된 일반 메시지를 *nIDPDefault* 매개 변수를 사용 합니다. 함수는 다음 오류 메시지를 포함 하는 메시지 상자를 표시 합니다. 추가, 사용자 지정 오류 메시지를 제공 하려는 경우이 함수를 재정의 합니다. 이 고급 재정의할 수 있습니다.

##  <a name="savemodified"></a>  CDocument::SaveModified

수정 된 문서를 닫아야 되기 전에 프레임 워크에서 호출 됩니다.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>반환 값

안전 하 게 문서를 닫고 계속 진행 하는 경우 0이 아닌 값 문서를 닫을 수 해야 하는 경우 0입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 모든 내용이 있으면 사용자는 문서에 변경 내용을 저장할 것인지 여부를 묻는 메시지 상자가 표시 됩니다. 다른 프롬프트 프로시저 프로그램에 필요한 경우이 함수를 재정의 합니다. 이 고급 재정의할 수 있습니다.

##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue

청크 값을 설정 합니다.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
청크 값 집합을 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag

문서에 대 한 수정은 수행한 후이 함수를 호출 합니다.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>매개 변수

*bModified*<br/>
문서 수정 되었는지 여부를 나타내는 플래그입니다.

### <a name="remarks"></a>설명

이 함수를 일관 되 게를 호출 하면 프레임 워크는 사용자는 문서를 닫기 전에 변경 내용을 저장 하 라는 메시지가 표시 됩니다. 일반적으로 true 기본값을 사용 해야 합니다 *bModified* 매개 변수입니다. 정리 하는 대로 문서 (수정 되지 않은)를 표시 하려면 값이 FALSE 사용 하 여이 함수를 호출 합니다.

##  <a name="setpathname"></a>  CDocument::SetPathName

문서의 디스크 파일의 정규화 된 경로 지정 하려면이 함수를 호출 합니다.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
문서에 대 한 경로로 사용할 문자열을 가리킵니다.

*bAddToMRU*<br/>
가장 최근에 (사용한 MRU) 파일 목록의 사용한 파일 이름에 추가 됩니다 있는지 여부를 결정 합니다. True 이면 파일 이름이 추가 됩니다. FALSE 인 경우 추가 되지 않습니다.

### <a name="remarks"></a>설명

값에 따라 *baddtomru입니다* 경로 추가 되었거나 응용 프로그램에서 유지 관리 MRU 목록에 추가할가 없습니다. 참고 일부 문서는 디스크 파일을 사용 하 여 연결 하지 않습니다. 프레임 워크에서 사용 되는 파일 열기 및 저장에 대 한 기본 구현을 재정의 하는 경우에이 함수를 호출 합니다.

##  <a name="settitle"></a>  CDocument::SetTitle

문서의 제목 (프레임 창의 제목 표시줄에 표시 되는 문자열)을 지정 하려면이 함수를 호출 합니다.

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>매개 변수

*lpszTitle*<br/>
문서의 제목으로 사용할 문자열을 가리킵니다.

### <a name="remarks"></a>설명

이 함수를 호출 합니다. 문서를 표시 하는 모든 프레임 창의 제목을 업데이트 합니다.

##  <a name="updateallviews"></a>  CDocument::UpdateAllViews

문서를 수정한 후이 함수를 호출 합니다.

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
문서를 수정 하는 뷰를 가리키는 모든 뷰는 업데이트할 경우 null입니다.

*lHint*<br/>
수정에 대 한 정보를 포함합니다.

*pHint*<br/>
수정에 대 한 정보를 저장 하는 개체를 가리킵니다.

### <a name="remarks"></a>설명

호출한 후에이 함수를 호출 해야 합니다 [SetModifiedFlag](#setmodifiedflag) 멤버 함수입니다. 이 함수에서 지정한 보기를 제외 하 고 문서에 연결 된 각 뷰에 알립니다 *pSender*, 수정 된 문서입니다. 일반적으로 사용자가 뷰를 통해 문서를 변경한 후 뷰 클래스에서이 함수를 호출 합니다.

이 함수를 호출 합니다 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) 전달 전송을 제외한 문서 보기의 각 멤버 함수 보기 *pHint* 하 고 *lHint*. 이러한 매개 변수를 사용 하 여 문서를 수정 하는 방법에 대 한 보기에 정보를 전달. 사용 하 여 정보를 인코딩할 수 있습니다 *lHint* 정의할 수 있습니다 및/또는 [CObject](../../mfc/reference/cobject-class.md)-수정에 대 한 정보를 저장 하 고 사용 하 여 해당 클래스의 개체를 전달 하는 클래스를 파생 *pHint*. 재정의 된 `CView::OnUpdate` 멤버 함수에 [CView](../../mfc/reference/cview-class.md)-전달 된 정보를 기반으로 하는 보기의 디스플레이의 업데이트를 최적화 하는 클래스를 파생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)
