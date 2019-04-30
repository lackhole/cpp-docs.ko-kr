---
title: CRichEditView 클래스
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: 60eeaa2a37dd824ae418b25e95743c21c65ae7ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372077"
---
# <a name="cricheditview-class"></a>CRichEditView 클래스

사용 하 여 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 하 고 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.

## <a name="syntax"></a>구문

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRichEditView::CRichEditView](#cricheditview)|`CRichEditView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRichEditView::AdjustDialogPosition](#adjustdialogposition)|현재 선택 영역을 가리는 하지 있도록 대화 상자를 이동 합니다.|
|[CRichEditView::CanPaste](#canpaste)|Rich edit 뷰의에 붙여 넣을 수 있는 데이터를 클립보드에 포함 되는지 여부를 알려 줍니다.|
|[CRichEditView::DoPaste](#dopaste)|Rich edit 뷰의에 OLE 항목을 붙여 넣습니다.|
|[CRichEditView::FindText](#findtext)|Waitcursor를 호출 합니다. 지정 된 텍스트를 찾습니다.|
|[CRichEditView::FindTextSimple](#findtextsimple)|지정된 된 텍스트를 찾습니다.|
|[CRichEditView::GetCharFormatSelection](#getcharformatselection)|현재 선택 영역에 대 한 특성을 형식 지정 문자를 검색 합니다.|
|[CRichEditView::GetDocument](#getdocument)|관련에 대 한 포인터를 검색 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)합니다.|
|[CRichEditView::GetInPlaceActiveItem](#getinplaceactiveitem)|서식 있는 편집 보기에서 현재 내부 활성화 된 OLE 항목을 검색 합니다.|
|[CRichEditView::GetMargins](#getmargins)|Rich edit 뷰의 여백을 검색합니다.|
|[CRichEditView::GetPageRect](#getpagerect)|이 서식 있는 편집 보기에 대 한 페이지 사각형을 검색합니다.|
|[CRichEditView::GetPaperSize](#getpapersize)|Rich edit 뷰의의 용지 크기를 검색합니다.|
|[CRichEditView::GetParaFormatSelection](#getparaformatselection)|단락 서식 현재 선택 영역에 대 한 특성을 검색 합니다.|
|[CRichEditView::GetPrintRect](#getprintrect)|이 서식 있는 편집 보기에 대 한 인쇄 사각형을 검색합니다.|
|[CRichEditView::GetPrintWidth](#getprintwidth)|Rich edit 뷰의 인쇄 너비를 검색합니다.|
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|Rich edit 컨트롤을 검색합니다.|
|[CRichEditView::GetSelectedItem](#getselecteditem)|서식 있는 편집 보기에서 선택한 항목을 검색합니다.|
|[CRichEditView::GetTextLength](#gettextlength)|서식 있는 편집 보기에서 텍스트의 길이 검색합니다.|
|[CRichEditView::GetTextLengthEx](#gettextlengthex)|Rich edit 뷰의 바이트 또는 문자 수를 검색 합니다. 길이 결정 하는 메서드에 대 한 확장 된 플래그 목록입니다.|
|[CRichEditView::InsertFileAsObject](#insertfileasobject)|OLE 항목으로 파일을 삽입합니다.|
|[CRichEditView::InsertItem](#insertitem)|OLE 항목으로 새 항목을 삽입 합니다.|
|[CRichEditView::IsRichEditFormat](#isricheditformat)|서식 있는 편집 또는 텍스트 형식으로 데이터를 클립보드에 포함 되는지 여부를 알려 줍니다.|
|[CRichEditView::OnCharEffect](#onchareffect)|현재 선택 영역에 대 한 형식 지정 문자를 전환 합니다.|
|[CRichEditView::OnParaAlign](#onparaalign)|단락 맞춤을 변경합니다.|
|[CRichEditView::OnUpdateCharEffect](#onupdatechareffect)|문자 공용 멤버 함수에 대 한 명령 UI를 업데이트합니다.|
|[CRichEditView::OnUpdateParaAlign](#onupdateparaalign)|단락 공용 멤버 함수에 대 한 명령 UI를 업데이트합니다.|
|[CRichEditView::PrintInsideRect](#printinsiderect)|지정된 된 사각형 내의 지정한 텍스트에 서식을 지정합니다.|
|[CRichEditView::PrintPage](#printpage)|지정된 된 페이지 내의 지정한 텍스트에 서식을 지정합니다.|
|[CRichEditView::SetCharFormat](#setcharformat)|현재 선택 영역에 대 한 특성을 형식 지정 문자를 설정 합니다.|
|[CRichEditView::SetMargins](#setmargins)|집합의 여백을이 다양 한 보기를 편집 합니다.|
|[CRichEditView::SetPaperSize](#setpapersize)|Rich edit 뷰의의 용지 크기를 설정합니다.|
|[CRichEditView::SetParaFormat](#setparaformat)|단락 서식 현재 선택 영역에 대 한 특성을 설정 합니다.|
|[CRichEditView::TextNotFound](#textnotfound)|컨트롤의 내부 검색 상태를 다시 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CRichEditView::GetClipboardData](#getclipboarddata)|Rich edit 뷰 범위에 대 한 클립보드 개체를 검색합니다.|
|[CRichEditView::GetContextMenu](#getcontextmenu)|오른쪽 마우스 단추에서 사용 하는 상황에 맞는 메뉴를 검색 합니다.|
|[CRichEditView::IsSelected](#isselected)|지정 된 OLE 항목을 선택 하는 경우를 나타냅니다.|
|[CRichEditView::OnFindNext](#onfindnext)|부분 문자열의 다음 항목을 찾습니다.|
|[CRichEditView::OnInitialUpdate](#oninitialupdate)|새로 고침 처음에 뷰를 문서에 연결 합니다.|
|[CRichEditView::OnPasteNativeObject](#onpastenativeobject)|OLE 항목에서 원시 데이터를 검색합니다.|
|[CRichEditView::OnPrinterChanged](#onprinterchanged)|지정된 된 장치에 인쇄 특성을 설정합니다.|
|[CRichEditView::OnReplaceAll](#onreplaceall)|지정된 된 문자열의 모든 항목을 새 문자열로 바꿉니다.|
|[CRichEditView::OnReplaceSel](#onreplacesel)|현재 선택 영역을 대체합니다.|
|[CRichEditView::OnTextNotFound](#ontextnotfound)|요청 된 텍스트를 찾을 수 없습니다는 사용자 알림을 처리 합니다.|
|[CRichEditView::QueryAcceptData](#queryacceptdata)|데이터에 대 한 참조에 대 한 쿼리는 `IDataObject`합니다.|
|[CRichEditView::WrapChanged](#wrapchanged)|이 rich edit 뷰의 값을 기반으로 대상 출력 장치 조정 `m_nWordWrap`합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CRichEditView::m_nBulletIndent](#m_nbulletindent)|글머리 기호 목록에 대 한 들여쓰기의 크기를 나타냅니다.|
|[CRichEditView::m_nWordWrap](#m_nwordwrap)|단어 줄 바꿈 제약 조건을 나타냅니다.|

## <a name="remarks"></a>설명

"Rich edit 컨트롤"에 사용자 입력 수 및 텍스트를 편집 하는 창입니다. 텍스트 문자와 단락 형식을 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트 서식 지정에 대 한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 서식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.

`CRichEditView` 텍스트 및 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc` 보기에는 OLE 클라이언트 항목 목록을 유지 관리 합니다. `CRichEditCntrItem` 컨테이너 쪽 OLE 클라이언트 항목에 대 한 액세스를 제공합니다.

이 Windows 공용 컨트롤 (및 따라서 합니다 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.

MFC 응용 프로그램에서 풍부한 편집 뷰를 사용 하는 예제를 보려면 합니다 [워드 패드](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxrich.h

##  <a name="adjustdialogposition"></a>  CRichEditView::AdjustDialogPosition

현재 선택 영역을 가리지 않습니다 있도록 지정된 된 대화 상자를 이동 하려면이 함수를 호출 합니다.

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>매개 변수

*pDlg*<br/>
`CDialog` 개체에 대한 포인터입니다.

##  <a name="canpaste"></a>  CRichEditView::CanPaste

클립보드 정보를이 rich edit 뷰의에 붙여 넣을 수 있는지 확인 하려면이 함수를 호출 합니다.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>반환 값

클립보드 rich edit 뷰의 수락할 수 있습니다; 형식의 데이터를 포함 하는 경우 0이 아닌 값 그렇지 않을 경우 0입니다.

##  <a name="cricheditview"></a>  CRichEditView::CRichEditView

이 함수를 만들려면 호출을 `CRichEditView` 개체입니다.

```
CRichEditView();
```

##  <a name="dopaste"></a>  CRichEditView::DoPaste

OLE 항목을 붙여 넣으려면이 함수를 호출 *dataobj* 이 풍부한 문서/뷰를 편집 합니다.

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>매개 변수

*dataobj*<br/>
합니다 [COleDataObject](../../mfc/reference/coledataobject-class.md) 붙여넣을 데이터가 들어 있는입니다.

*cf*<br/>
원하는 클립보드 형식입니다.

*hMetaPict*<br/>
메타 파일을 붙여 넣을 항목을 나타냅니다.

### <a name="remarks"></a>설명

기본 구현의 일환으로이 함수를 호출 하는 프레임 워크 [QueryAcceptData](#queryacceptdata)합니다.

이 함수는 붙여넣기에 대 한 처리기의 결과에 따라 붙여넣기의 형식을 결정 합니다. 하는 경우 *cf* 0 인 새 항목이 현재 아이콘 표현을 사용 합니다. 하는 경우 *cf* 가 0이 아닌 하 고 *hMetaPict* NULL이 아니면 새 항목을 사용 하 여 *hMetaPict* 표현에 대 한 합니다.

##  <a name="findtext"></a>  CRichEditView::FindText

지정 된 텍스트를 찾아 현재 선택 되도록 설정 하려면이 함수를 호출 합니다.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
검색할 문자열을 포함 합니다.

*bCase*<br/>
검색은 대/소문자 구분 하는 경우를 나타냅니다.

*bWord*<br/>
검색 단어 단위로 단어의 일부가 아니라 일치 해야 하는 경우를 나타냅니다.

*bNext*<br/>
검색 방향을 나타냅니다. TRUE 이면 검색 방향을 버퍼의 끝에 다가가입니다. FALSE 이면 검색 방향을 버퍼의 시작 부분입니다.

### <a name="return-value"></a>반환 값

0이 아닌 값을 *lpszFind* 텍스트 발견 되 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 찾기 작업 하는 동안 대기 커서를 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

##  <a name="findtextsimple"></a>  CRichEditView::FindTextSimple

지정 된 텍스트를 찾아 현재 선택 되도록 설정 하려면이 함수를 호출 합니다.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
검색할 문자열을 포함 합니다.

*bCase*<br/>
검색은 대/소문자 구분 하는 경우를 나타냅니다.

*bWord*<br/>
검색 단어 단위로 단어의 일부가 아니라 일치 해야 하는 경우를 나타냅니다.

*bNext*<br/>
검색 방향을 나타냅니다. TRUE 이면 검색 방향을 버퍼의 끝에 다가가입니다. FALSE 이면 검색 방향을 버퍼의 시작 부분입니다.

### <a name="return-value"></a>반환 값

0이 아닌 값을 *lpszFind* 텍스트 발견 되 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::FindText](#findtext)합니다.

##  <a name="getcharformatselection"></a>  CRichEditView::GetCharFormatSelection

현재 선택 영역의 특성을 형식 지정 문자를 가져오려면이 함수를 호출 합니다.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>반환 값

A [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) 서식 특성 현재 선택 영역의 문자를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

자세한 내용은 참조는 [EM_GETCHARFORMAT](/windows/desktop/Controls/em-getcharformat) 메시지 및 [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Windows SDK에는 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="getclipboarddata"></a>  CRichEditView::GetClipboardData

처리의 일부로이 함수를 호출 하는 프레임 워크 [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata)합니다.

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>매개 변수

*lpchrg*<br/>
에 대 한 포인터를 [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) 로 지정 된 데이터 개체에 복사할 문자 (및 OLE 항목)의 범위를 지정 하는 구조 *lplpdataobj*합니다.

*dwReco*<br/>
클립보드 작업 플래그입니다. 다음이 값 중 하나일 수 있습니다.

- 클립보드로 RECO_COPY 복사본입니다.

- RECO_CUT 클립보드로 잘라내 집니다.

- RECO_DRAG 끌어서 작업 (끌어서 놓기)입니다.

- RECO_DROP 삭제 작업 (끌어서 놓기)입니다.

- 클립보드에서 RECO_PASTE 붙여 넣습니다.

*lpRichDataObj*<br/>
에 대 한 포인터를 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) 컨트롤을 편집 하는에서 다양 한 클립보드 데이터를 포함 하는 개체 ( [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata)).

*lplpdataobj*<br/>
주소를 받는 포인터 변수의에 대 한 포인터를 `IDataObject` 에 지정 된 범위를 나타내는 개체를 *lpchrg* 매개 변수입니다. 변수의 *lplpdataobj* 오류를 반환 하는 경우 무시 됩니다.

### <a name="return-value"></a>반환 값

작업의 성공 여부를 보고 하는 HRESULT 값입니다. HRESULT에 대 한 자세한 내용은 참조 하세요. [COM 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) Windows SDK에 있습니다.

### <a name="remarks"></a>설명

반환 값은 성공을 나타내는 경우 `IRichEditOleCallback::GetClipboardData` 반환 합니다 `IDataObject` 액세스할 *lplpdataobj*고, 그렇지 않으면 액세스할 것을 반환 *lpRichDataObj*. 사용자 고유의 클립보드 데이터를 제공 하려면이 함수를 재정의 합니다. 이 함수의 기본 구현은 E_NOTIMPL을 반환합니다.

이 고급 재정의할 수 있습니다.

자세한 내용은 [IRichEditOle::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditole-getclipboarddata)를 [IRichEditOleCallback::GetClipboardData](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getclipboarddata), 및 [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) Windows SDK를 참조 하십시오 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) Windows SDK에에서 있습니다.

##  <a name="getcontextmenu"></a>  CRichEditView::GetContextMenu

처리의 일부로이 함수를 호출 하는 프레임 워크 [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu)합니다.

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>매개 변수

*seltyp*<br/>
선택 유형입니다. 선택 유형 값은 주의 섹션에 설명 되어 있습니다.

*lpoleobj*<br/>
에 대 한 포인터를 `OLEOBJECT` 구조 선택 영역이 하나 이상의 OLE 항목을 포함 하는 경우 첫 번째 선택된 된 OLE 개체를 지정 합니다. 선택 항목이 없는 경우 *lpoleobj* NULL입니다. `OLEOBJECT` 구조는 OLE 개체 v-테이블에 대 한 포인터를 보유 합니다.

*lpchrg*<br/>
에 대 한 포인터를 [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) 현재 선택을 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

상황에 맞는 메뉴에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 함수는 일반적인 부분 오른쪽 마우스 단추를 눌렀을 처리 합니다.

선택 형식을 플래그의 조합 수 있습니다.

- SEL_EMPTY 현재 선택 영역이 없는 임을 나타냅니다.

- SEL_TEXT 현재 선택 영역에 텍스트를 포함 됨을 나타냅니다.

- SEL_OBJECT 현재 선택 영역 OLE 항목을 하나 이상 포함을 나타냅니다.

- SEL_MULTICHAR 현재 선택 항목 텍스트의 문자를 여러 개 포함 되어 있는지를 나타냅니다.

- SEL_MULTIOBJECT 현재 선택 영역에 둘 이상의 OLE 개체가 포함 되어 있음을 나타냅니다.

기본 구현은 NULL을 반환합니다. 이 고급 재정의할 수 있습니다.

자세한 내용은 [IRichEditOleCallback::GetContextMenu](/windows/desktop/api/richole/nf-richole-iricheditolecallback-getcontextmenu) 하 고 [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) Windows SDK의 합니다.

##  <a name="getdocument"></a>  CRichEditView::GetDocument

에 대 한 포인터를 가져오려면이 함수를 호출 합니다 `CRichEditDoc` 이 보기를 사용 하 여 연결 합니다.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 연관 된 개체에 `CRichEditView` 개체입니다.

##  <a name="getinplaceactiveitem"></a>  CRichEditView::GetInPlaceActiveItem

항목 OLE를 가져오려면이 함수를 호출은이 위치에서 현재 활성화 되어 `CRichEditView` 개체입니다.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>반환 값

단일, 내부 활성화에 대 한 포인터 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) rich edit 뷰의;의 개체 OLE 항목이 없는 현재 전체 활성 상태인 경우 NULL입니다.

##  <a name="getmargins"></a>  CRichEditView::GetMargins

인쇄에 사용 되는 현재 여백을 검색 하려면이 함수를 호출 합니다.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>반환 값

인쇄에 사용 되는 여백 MM_TWIPS 단위로 지정 합니다.

##  <a name="getpagerect"></a>  CRichEditView::GetPageRect

인쇄에 사용 된 페이지의 크기를 가져오려면이 함수를 호출 합니다.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>반환 값

인쇄에 사용 된 페이지의 경계 MM_TWIPS 단위로 지정 합니다.

### <a name="remarks"></a>설명

이 값은 용지 크기를 기반으로 합니다.

##  <a name="getpapersize"></a>  CRichEditView::GetPaperSize

현재 문서 크기를 검색 하려면이 함수를 호출 합니다.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>반환 값

인쇄에 사용 되는 용지 크기 MM_TWIPS 단위로 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

##  <a name="getparaformatselection"></a>  CRichEditView::GetParaFormatSelection

단락 서식 특성의 현재 선택 영역을 가져오려면이 함수를 호출 합니다.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>반환 값

A [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) 단락 서식 현재 선택 영역의 특성을 포함 하는 구조입니다.

### <a name="remarks"></a>설명

자세한 내용은 [EM_GETPARAFORMAT](/windows/desktop/Controls/em-getparaformat) 메시지 및 [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Windows SDK에는 구조입니다.

##  <a name="getprintrect"></a>  CRichEditView::GetPrintRect

페이지 사각형 내에서 인쇄 영역의 범위를 검색 하려면이 함수를 호출 합니다.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>반환 값

인쇄에 사용 되는 이미지 영역 경계 MM_TWIPS 단위로 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

##  <a name="getprintwidth"></a>  CRichEditView::GetPrintWidth

인쇄 영역의 너비를 결정 하는이 함수를 호출 합니다.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>반환 값

인쇄 영역의 너비 MM_TWIPS 단위로 지정 합니다.

##  <a name="getricheditctrl"></a>  CRichEditView::GetRichEditCtrl

검색 하려면이 함수를 호출 합니다 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 연관 된 개체는 `CRichEditView` 개체입니다.

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>반환 값

`CRichEditCtrl` 이 보기에 대 한 개체입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::FindText](#findtext)합니다.

##  <a name="getselecteditem"></a>  CRichEditView::GetSelectedItem

OLE 항목을 검색 하려면이 함수를 호출 (한 `CRichEditCntrItem` 개체)이 현재 선택한 `CRichEditView` 개체입니다.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 에서 선택한 개체를 `CRichEditView` 개체 이 뷰에서 선택 된 항목이 없으면 NULL입니다.

##  <a name="gettextlength"></a>  CRichEditView::GetTextLength

이 텍스트의 길이 검색 하려면이 함수를 호출 `CRichEditView` 개체입니다.

```
long GetTextLength() const;
```

### <a name="return-value"></a>반환 값

이 텍스트의 길이 `CRichEditView` 개체입니다.

##  <a name="gettextlengthex"></a>  CRichEditView::GetTextLengthEx

이 텍스트의 길이 계산 하려면이 멤버 함수를 호출 `CRichEditView` 개체입니다.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
텍스트 길이 결정 하는 데 사용할 메서드를 지정 하는 값입니다. 이 멤버는 하나일 수 있습니다 또는 플래그 소속에 나열 된 값 중 더 [GETTEXTLENGTHEX](/windows/desktop/api/richedit/ns-richedit-_gettextlengthex) Windows SDK에 설명 합니다.

*uCodePage*<br/>
번역 (ANSI 코드 페이지를 유니코드에 대 한 1200 CP_ACP)에 대 한 코드 페이지입니다.

### <a name="return-value"></a>반환 값

문자 또는 편집 컨트롤의 바이트 수입니다. 호환 되지 않는 플래그 설정 된 경우 *dwFlags*를이 멤버 함수는 E_INVALIDARG를 반환 합니다.

### <a name="remarks"></a>설명

`GetTextLengthEx` 텍스트의 길이 결정 하는 추가 방법을 제공 합니다. Rich Edit 2.0 기능을 지원합니다. 자세한 내용은 [Rich Edit 컨트롤](/windows/desktop/Controls/about-rich-edit-controls) Windows SDK에 있습니다.

##  <a name="insertfileasobject"></a>  CRichEditView::InsertFileAsObject

지정된 된 파일을 삽입 하려면이 함수를 호출 (으로 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체)를 서식 있는 뷰를 편집 합니다.

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
삽입할 파일의 이름을 포함 하는 문자열입니다.

##  <a name="insertitem"></a>  CRichEditView::InsertItem

삽입 하려면이 함수를 호출을 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) rich edit 뷰 개체입니다.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
삽입할 항목에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

삽입의 성공 여부를 나타내는 HRESULT 값입니다.

### <a name="remarks"></a>설명

HRESULT에 대 한 자세한 내용은 참조 하세요. [COM 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) Windows SDK에 있습니다.

##  <a name="isricheditformat"></a>  CRichEditView::IsRichEditFormat

확인 하려면이 함수를 호출 *cf* 텍스트, 서식 있는 텍스트 또는 서식 있는 텍스트 OLE 항목을 사용 하 여 클립보드 형식입니다.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>매개 변수

*cf*<br/>
관심 클립보드 형식입니다.

### <a name="return-value"></a>반환 값

0이 아닌 경우 *cf* 은 다양 한 편집 또는 텍스트 클립보드 형식입니다.

##  <a name="isselected"></a>  CRichEditView::IsSelected

이 뷰에서 지정된 된 OLE 항목 현재 선택 되어 있는지 확인 하려면이 함수를 호출 합니다.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>매개 변수

*pDocItem*<br/>
뷰에서 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

개체 선택 되 면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

파생 된 뷰 클래스에 다양 한 OLE 항목을 처리 하기 위한 다른 방법을 하는 경우이 함수를 재정의 합니다.

##  <a name="m_nbulletindent"></a>  CRichEditView::m_nBulletIndent

글머리 기호 항목을 목록에 대 한 들여쓰기 기본적으로 720 단위는 1/2 인치입니다.

```
int m_nBulletIndent;
```

##  <a name="m_nwordwrap"></a>  CRichEditView::m_nWordWrap

이 서식 있는 편집 보기에 대 한 자동 줄 바꿈의 유형을 나타냅니다.

```
int m_nWordWrap;
```

### <a name="remarks"></a>설명

다음 값 중 하나입니다.

- `WrapNone` 단어 단위로 줄 바꿈 없음를 나타냅니다.

- `WrapToWindow` 창의 너비를 기준으로 단어 잘림 방지를 나타냅니다.

- `WrapToTargetDevice` 대상 장치의 특징을 기반으로 자동 줄 바꿈을 나타냅니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::WrapChanged](#wrapchanged)합니다.

##  <a name="onchareffect"></a>  CRichEditView::OnCharEffect

현재 선택 영역에 대 한 효과 서식 지정 문자를 설정/해제 하려면이 함수를 호출 합니다.

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>매개 변수

*dwMask*<br/>
현재 선택 영역에서을 수정 하는 효과 서식 지정 문자입니다.

*dwEffect*<br/>
원하는 목록 설정/해제 하는 효과 서식 지정 문자입니다.

### <a name="remarks"></a>설명

이 함수를 호출할 때마다 현재 선택 영역에 대 한 서식 지정된 효과 전환합니다.

대 한 자세한 내용은 합니다 *dwMask* 및 *dwEffect* 매개 변수와 해당 잠재적인 값의 해당 데이터 멤버를 확인할 [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) Windows SDK의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

##  <a name="onfindnext"></a>  CRichEditView::OnFindNext

찾기/바꾸기 대화 상자에서 명령을 처리할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 문자열입니다.

*bNext*<br/>
검색 방향: TRUE 이면 중지 하도록 합니다. FALSE를 설정 합니다.

*bCase*<br/>
검색은 대/소문자 구분 여부를 나타냅니다.

*bWord*<br/>
검색 단어 단위로 인지 여부를 나타냅니다.

### <a name="remarks"></a>설명

내에서 텍스트를 찾으려면이 함수를 호출 합니다 `CRichEditView`합니다. 파생 된 뷰 클래스에 대 한 검색 특성을 변경 하려면이 함수를 재정의 합니다.

##  <a name="oninitialupdate"></a>  CRichEditView::OnInitialUpdate

전에 호출 됩니다 프레임 워크에서 뷰를 먼저 문서에 연결한 후 뷰 처음에 표시 됩니다.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현을 호출를 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) 힌트 정보 없이 멤버 함수 (즉, 0에 대 한 기본값을 사용 하는 *lHint* 매개 변수 및 합니다 에대한NULL*pHint* 매개 변수). 문서에 대 한 정보를 필요로 하는 일회 초기화를 수행 하려면이 함수를 재정의 합니다. 예를 들어, 응용 프로그램에 고정 크기 문서를 뷰의 스크롤 제한 문서 크기를 기준으로 초기화 하려면이 함수를 사용할 수 있습니다. 사용 하 여 응용 프로그램에서 가변 크기의 문서를 지 원하는 경우 `OnUpdate` 스크롤 업데이트 제한 될 때마다 문서 변경 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::m_nWordWrap](#m_nwordwrap)합니다.

##  <a name="onpastenativeobject"></a>  CRichEditView::OnPasteNativeObject

이 함수를 사용 하 여 포함 된 항목에서 기본 데이터를 로드 합니다.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>매개 변수

*lpStg*<br/>
에 대 한 포인터를 [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않을 경우 0입니다.

### <a name="remarks"></a>설명

일반적으로 이렇게 만들어를 [COleStreamFile](../../mfc/reference/colestreamfile-class.md) 주위를 `IStorage`입니다. 합니다 `COleStreamFile` 보관 파일에 연결할 수 있습니다 하 고 [cobject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 데이터를 로드 하기 위해 호출 됩니다.

이 고급 재정의할 수 있습니다.

자세한 내용은 [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) Windows SDK에 있습니다.

##  <a name="onparaalign"></a>  CRichEditView::OnParaAlign

선택 된 단락에서 단락 맞춤을 변경 하려면이 함수를 호출 합니다.

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>매개 변수

*wAlign*<br/>
원하는 단락 맞춤입니다. 다음 값 중 하나입니다.

- PFA_LEFT 왼쪽된에 여백 두고 단락을 맞춥니다.

- PFA_RIGHT 오른쪽 여백이 있는 단락을 맞춥니다.

- PFA_CENTER 여백 사이의 단락 센터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

##  <a name="onprinterchanged"></a>  CRichEditView::OnPrinterChanged

프린터 변경 될 때이 서식 있는 편집 보기에 대 한 특성을 변경 하려면이 함수를 재정의 합니다.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>매개 변수

*dcPrinter*<br/>
A [CDC](../../mfc/reference/cdc-class.md) 새 프린터에 대 한 개체입니다.

### <a name="remarks"></a>설명

기본 구현에서는 실제 높이 및 너비 출력 장치 (프린터)에 대 한 용지 크기를 설정합니다. 장치 컨텍스트가 없는 연결 된 경우 *dcPrinter*, 용지 크기 11 8.5 인치를 설정 하는 기본 구현입니다.

##  <a name="onreplaceall"></a>  CRichEditView::OnReplaceAll

바꾸기 대화 상자에서 모두 바꾸기 명령을 처리할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
바꿀 텍스트입니다.

*lpszReplace*<br/>
대체 텍스트입니다.

*bCase*<br/>
검색은 대/소문자 구분 하는 경우를 나타냅니다.

*bWord*<br/>
검색 여부 전체 단어를 선택 해야 하는 경우를 나타냅니다.

### <a name="remarks"></a>설명

다른 문자열을 사용 하 여 지정 된 텍스트의 모든 항목을 바꾸려면이 함수를 호출 합니다. 이 보기에 대 한 검색 특성을 변경 하려면이 함수를 재정의 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::FindText](#findtext)합니다.

##  <a name="onreplacesel"></a>  CRichEditView::OnReplaceSel

바꾸기 대화 상자에서 Replace 명령을 처리할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
바꿀 텍스트입니다.

*bNext*<br/>
검색의 방향을 나타냅니다. TRUE가입니다. FALSE를 설정 합니다.

*bCase*<br/>
검색은 대/소문자 구분 하는 경우를 나타냅니다.

*bWord*<br/>
검색 여부 전체 단어를 선택 해야 하는 경우를 나타냅니다.

*lpszReplace*<br/>
대체 텍스트입니다.

### <a name="remarks"></a>설명

지정 된 텍스트를 한 번을 다른 문자열로 바꾸려면이 함수를 호출 합니다. 이 보기에 대 한 검색 특성을 변경 하려면이 함수를 재정의 합니다.

##  <a name="ontextnotfound"></a>  CRichEditView::OnTextNotFound

검색에 실패할 때마다 프레임 워크에서 호출 됩니다.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
텍스트를 찾을 수 없습니다.

### <a name="remarks"></a>설명

이 함수에서 출력 알림을 변경 하려면 재정의 [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep)합니다.

자세한 내용은 [MessageBeep](/windows/desktop/api/winuser/nf-winuser-messagebeep) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

##  <a name="onupdatechareffect"></a>  CRichEditView::OnUpdateCharEffect

프레임 워크가 문자 효과 명령에 대 한 명령 UI를 업데이트 하는이 함수를 호출 합니다.

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
에 대 한 포인터를 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체입니다.

*dwMask*<br/>
마스크 형식 지정 문자를 나타냅니다.

*dwEffect*<br/>
효과 서식 문자를 나타냅니다.

### <a name="remarks"></a>설명

마스크 *dwMask* 는 문자 검사할 서식 특성을 지정 합니다. 플래그 *dwEffect* 문자 서식을 설정/해제 하는 특성을 나열 합니다.

대 한 자세한 내용은 합니다 *dwMask* 및 *dwEffect* 매개 변수와 해당 잠재적인 값의 해당 데이터 멤버를 확인할 [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) Windows SDK의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

##  <a name="onupdateparaalign"></a>  CRichEditView::OnUpdateParaAlign

프레임 워크가 단락 효과 명령에 대 한 명령 UI를 업데이트 하는이 함수를 호출 합니다.

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
에 대 한 포인터를 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체입니다.

*wAlign*<br/>
검사할 단락 맞춤입니다. 다음 값 중 하나입니다.

- PFA_LEFT 왼쪽된에 여백 두고 단락을 맞춥니다.

- PFA_RIGHT 오른쪽 여백이 있는 단락을 맞춥니다.

- PFA_CENTER 여백 사이의 단락 센터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

##  <a name="printinsiderect"></a>  CRichEditView::PrintInsideRect

범위 내에 맞게 rich edit 컨트롤의 텍스트에 서식을 지정 하려면이 함수를 호출 *rectLayout* 로 지정 된 장치에 대 한 *pDC*합니다.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
출력 영역에 대 한 장치 컨텍스트에 대 한 포인터입니다.

*rectLayout*<br/>
[RECT](/windows/desktop/api/windef/ns-windef-tagrect) 나 [CRect](../../atl-mfc-shared/reference/crect-class.md) 출력 영역을 정의 하는 합니다.

*nIndexStart*<br/>
서식을 지정할 첫 번째 문자의 0부터 시작 인덱스입니다.

*nIndexStop*<br/>
서식이 지정 될 마지막 문자의 0부터 시작 인덱스입니다.

*bOutput*<br/>
텍스트를 렌더링할지 여부를 나타냅니다. FALSE 이면 텍스트 바로 측정 됩니다.

### <a name="return-value"></a>반환 값

1을 더하여 출력 영역에 맞는 마지막 문자의 인덱스입니다.

### <a name="remarks"></a>설명

일반적으로이 호출 뒤에 대 한 호출 [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) 출력을 생성 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::GetPaperSize](#getpapersize)합니다.

##  <a name="printpage"></a>  CRichEditView::PrintPage

범위 지정 된 출력 장치에 대 한 서식 있는 편집 컨트롤의 텍스트에 서식을 지정 하려면이 함수를 호출 *pDC*합니다.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
페이지 출력에 대 한 장치 컨텍스트에 대 한 포인터입니다.

*nIndexStart*<br/>
서식을 지정할 첫 번째 문자의 0부터 시작 인덱스입니다.

*nIndexStop*<br/>
서식이 지정 될 마지막 문자의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

1을 더한 페이지에 맞는 마지막 문자의 인덱스입니다.

### <a name="remarks"></a>설명

각 페이지의 레이아웃에 의해 제어 됩니다 [GetPageRect](#getpagerect) 하 고 [GetPrintRect](#getprintrect)합니다. 일반적으로이 호출 뒤에 대 한 호출 [CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband) 출력을 생성 합니다.

여백은 물리적 페이지에서 논리 페이지가 아닌를 기준으로 하는 참고 합니다. 따라서 0의 여백은 대부분의 프린터 페이지에서 인쇄할 수 없는 영역 없으므로 텍스트를 클립 경우가 많습니다. 호출 해야를 방지 하기 위해 텍스트를 맞추는 [SetMargins](#setmargins) 인쇄 하기 전에 적절 한 여백을 설정 합니다.

##  <a name="queryacceptdata"></a>  CRichEditView::QueryAcceptData

서식 있는 편집에 개체를 붙여 넣습니다. 프레임 워크에서 호출 됩니다.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>매개 변수

*lpdataobj*<br/>
에 대 한 포인터를 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject) 쿼리 합니다.

*lpcfFormat*<br/>
사용할 수 있는 데이터 형식에 대 한 포인터입니다.

*dwReco*<br/>
사용되지 않습니다.

*bReally*<br/>
붙여넣기 작업을 계속할지 여부를 나타냅니다.

*hMetaFile*<br/>
항목의 아이콘을 그리는 데 사용 하 여 메타 파일 핸들입니다.

### <a name="return-value"></a>반환 값

작업의 성공 여부를 보고 하는 HRESULT 값입니다.

### <a name="remarks"></a>설명

다른 조직에 문서 파생된 클래스의 COM 항목을 처리 하려면이 함수를 재정의 합니다. 이 고급 재정의할 수 있습니다.

HRESULT에 대 한 자세한 내용은 및 `IDataObject`를 참조 하세요 [COM 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) 및 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject)각각 Windows sdk에서입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

##  <a name="setcharformat"></a>  CRichEditView::SetCharFormat

이 새 텍스트 특성을 형식 지정 문자를 설정 하려면이 함수를 호출 `CRichEditView` 개체입니다.

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>매개 변수

*cf*<br/>
[CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) 새 기본 문자 서식 특성을 포함 하는 구조체입니다.

### <a name="remarks"></a>설명

지정 된 특성에만 합니다 `dwMask` 소속 *cf* 이 함수에 의해 변경 됩니다.

자세한 내용은 [EM_SETCHARFORMAT](/windows/desktop/Controls/em-setcharformat) 메시지 및 [CHARFORMAT2](/windows/desktop/api/richedit/ns-richedit-charformat2a) Windows SDK에는 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

##  <a name="setmargins"></a>  CRichEditView::SetMargins

이 서식 있는 편집 보기에 대 한 인쇄 여백을 설정 하려면이 함수를 호출 합니다.

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>매개 변수

*rectMargin*<br/>
인쇄를 위해 새 여백 값 MM_TWIPS 단위로 지정 합니다.

### <a name="remarks"></a>설명

경우 [m_nWordWrap](#m_nwordwrap) 됩니다 `WrapToTargetDevice`를 호출 해야 [WrapChanged](#wrapchanged) 이 함수를 사용 하 여 인쇄 특성을 조정 합니다.

여백을 사용 하는 참고 [PrintPage](#printpage) 논리 페이지가 아닌 실제 페이지를 기준으로 합니다. 따라서 0의 여백은 대부분의 프린터 페이지에서 인쇄할 수 없는 영역 없으므로 텍스트를 클립 경우가 많습니다. 텍스트를 맞추는 방지 하려면 사용 하 여 호출 해야 `SetMargins` 인쇄 하기 전에 적절 한 프린터 여백을 설정 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::GetPaperSize](#getpapersize)합니다.

##  <a name="setpapersize"></a>  CRichEditView::SetPaperSize

Rich edit 뷰를 인쇄 하는 것에 대 한 용지 크기를 설정 하려면이 함수를 호출 합니다.

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>매개 변수

*sizePaper*<br/>
인쇄를 위해 새 용지 크기 값 MM_TWIPS 단위로 지정 합니다.

### <a name="remarks"></a>설명

경우 [m_nWordWrap](#m_nwordwrap) 됩니다 `WrapToTargetDevice`를 호출 해야 [WrapChanged](#wrapchanged) 이 함수를 사용 하 여 인쇄 특성을 조정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

##  <a name="setparaformat"></a>  CRichEditView::SetParaFormat

단락 서식이 현재 선택 영역에 대 한 특성을 설정 하려면이 함수를 호출 `CRichEditView` 개체입니다.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>매개 변수

*pf*<br/>
[PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) 새 기본값을 포함 하는 구조 단락 서식 지정 특성입니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않을 경우 0입니다.

### <a name="remarks"></a>설명

지정 된 특성에만 합니다 `dwMask` 소속 *pf* 이 함수에 의해 변경 됩니다.

자세한 내용은 [EM_SETPARAFORMAT](/windows/desktop/Controls/em-setparaformat) 메시지 및 [PARAFORMAT2](/windows/desktop/api/richedit/ns-richedit-paraformat2) Windows SDK에는 구조입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

##  <a name="textnotfound"></a>  CRichEditView::TextNotFound

내부 검색 상태를 다시 설정 하려면이 함수를 호출 합니다 [CRichEditView](../../mfc/reference/cricheditview-class.md) 실패 한 호출 후 컨트롤 [FindText](#findtext)합니다.

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 없는 텍스트 문자열을 포함 합니다.

### <a name="remarks"></a>설명

실패 한 호출 바로 다음이 메서드를 호출 하는 것이 좋습니다 [FindText](#findtext) 컨트롤의 상태 내부 검색 올바르게 다시 설정 되도록 합니다.

합니다 *lpszFind* 매개 변수를 제공 하는 문자열와 동일한 콘텐츠를 포함 해야 [FindText](#findtext)합니다. 내부 검색 상태를 재설정 한 후이 메서드를 호출 합니다는 [OnTextNotFound](#ontextnotfound) 메서드에 제공 된 검색 문자열입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CRichEditView::FindText](#findtext)합니다.

##  <a name="wrapchanged"></a>  CRichEditView::WrapChanged

이 함수를 호출 하 여 인쇄 특성 변경 된 경우 ( [SetMargins](#setmargins) 하거나 [SetPaperSize](#setpapersize)).

```
virtual void WrapChanged();
```

### <a name="remarks"></a>설명

변경 내용에 응답 하는 다양 한 보기를 편집 하는 방법을 수정 하려면이 함수를 재정의 [m_nWordWrap](#m_nwordwrap) 또는 인쇄 특성 ( [OnPrinterChanged](#onprinterchanged)).

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 워드 패드](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc 클래스](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditCntrItem 클래스](../../mfc/reference/cricheditcntritem-class.md)
