---
title: CEditView 클래스
ms.date: 11/04/2016
f1_keywords:
- CEditView
- AFXEXT/CEditView
- AFXEXT/CEditView::CEditView
- AFXEXT/CEditView::FindText
- AFXEXT/CEditView::GetBufferLength
- AFXEXT/CEditView::GetEditCtrl
- AFXEXT/CEditView::GetPrinterFont
- AFXEXT/CEditView::GetSelectedText
- AFXEXT/CEditView::LockBuffer
- AFXEXT/CEditView::PrintInsideRect
- AFXEXT/CEditView::SerializeRaw
- AFXEXT/CEditView::SetPrinterFont
- AFXEXT/CEditView::SetTabStops
- AFXEXT/CEditView::UnlockBuffer
- AFXEXT/CEditView::OnFindNext
- AFXEXT/CEditView::OnReplaceAll
- AFXEXT/CEditView::OnReplaceSel
- AFXEXT/CEditView::OnTextNotFound
- AFXEXT/CEditView::dwStyleDefault
helpviewer_keywords:
- CEditView [MFC], CEditView
- CEditView [MFC], FindText
- CEditView [MFC], GetBufferLength
- CEditView [MFC], GetEditCtrl
- CEditView [MFC], GetPrinterFont
- CEditView [MFC], GetSelectedText
- CEditView [MFC], LockBuffer
- CEditView [MFC], PrintInsideRect
- CEditView [MFC], SerializeRaw
- CEditView [MFC], SetPrinterFont
- CEditView [MFC], SetTabStops
- CEditView [MFC], UnlockBuffer
- CEditView [MFC], OnFindNext
- CEditView [MFC], OnReplaceAll
- CEditView [MFC], OnReplaceSel
- CEditView [MFC], OnTextNotFound
- CEditView [MFC], dwStyleDefault
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
ms.openlocfilehash: 3ab276e83e8642aa5de2fd96305cb6d7b648fc40
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781239"
---
# <a name="ceditview-class"></a>CEditView 클래스

Windows 편집 컨트롤의 기능을 제공하고 간단한 텍스트 편집기 기능을 구현하는 데 사용할 수 있는 뷰 클래스의 유형입니다.

## <a name="syntax"></a>구문

```
class CEditView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CEditView::CEditView](#ceditview)|`CEditView` 형식의 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CEditView::FindText](#findtext)|텍스트 내에서 문자열을 검색 합니다.|
|[CEditView::GetBufferLength](#getbufferlength)|문자 버퍼의 길이 가져옵니다.|
|[CEditView::GetEditCtrl](#geteditctrl)|에 대 한 액세스를 제공 합니다 `CEdit` 부분을 `CEditView` 개체 (된 Windows 컨트롤을 편집 하는 데 사용).|
|[CEditView::GetPrinterFont](#getprinterfont)|현재 프린터 글꼴을 검색합니다.|
|[CEditView::GetSelectedText](#getselectedtext)|현재 선택한 텍스트를 검색합니다.|
|[CEditView::LockBuffer](#lockbuffer)|버퍼를 잠급니다.|
|[CEditView::PrintInsideRect](#printinsiderect)|지정 된 사각형 안의 텍스트를 렌더링합니다.|
|[CEditView::SerializeRaw](#serializeraw)|Serialize 된 `CEditView` 원시 텍스트로 디스크에는 개체입니다.|
|[CEditView::SetPrinterFont](#setprinterfont)|새 프린터 글꼴을 설정합니다.|
|[CEditView::SetTabStops](#settabstops)|탭 화면 표시와 인쇄 정지를 설정 합니다.|
|[CEditView::UnlockBuffer](#unlockbuffer)|버퍼를 잠금 해제합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CEditView::OnFindNext](#onfindnext)|텍스트 문자열의 다음 항목을 찾습니다.|
|[CEditView::OnReplaceAll](#onreplaceall)|지정된 된 문자열의 모든 항목을 새 문자열로 바꿉니다.|
|[CEditView::OnReplaceSel](#onreplacesel)|현재 선택 영역을 대체합니다.|
|[CEditView::OnTextNotFound](#ontextnotfound)|찾기 작업이 실패 하는 추가 텍스트와 일치 하도록 하는 경우 호출 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CEditView::dwStyleDefault](#dwstyledefault)|기본 형식의 개체에 대 한 스타일 `CEditView`합니다.|

## <a name="remarks"></a>설명

`CEditView` 클래스는 다음과 같은 추가 기능을 제공 합니다.

- 인쇄 합니다.

- 찾기 및 바꾸기.

때문에 클래스 `CEditView` 클래스의 파생 항목 `CView`, 클래스의 개체 `CEditView` 문서 및 문서 템플릿을 사용할 수 있습니다.

각 `CEditView` 컨트롤의 텍스트는 고유한 전역 메모리 개체에서 유지 됩니다. 응용 프로그램에 개수에 관계 없이 있습니다 `CEditView` 개체입니다.

형식의 개체를 만들 `CEditView` 편집 창 위에 나열 된 추가 기능을 사용 하려는 경우 또는 간단한 텍스트 편집기 기능을 사용 하려는 경우. `CEditView` 개체 창에 전체 클라이언트 영역을 차지할 수 있습니다. 고유한 클래스를 파생할 `CEditView` 를 추가 하 여 기본 기능을 수정 하거나 문서 템플릿에 추가할 수 있는 클래스를 선언 합니다.

클래스의 기본 구현은 `CEditView` 다음 명령을 처리 합니다. ID_EDIT_SELECT_ALL, ID_EDIT_FIND, ID_EDIT_REPLACE, ID_EDIT_REPEAT, 및 ID_FILE_PRINT 합니다.

기본 문자 제한은 `CEditView` 은 (1024 \* 1024-1 = 1048575). 내부 편집 컨트롤의 EM_LIMITTEXT 함수를 호출 하 여 변경할 수 있습니다. 그러나 제한 운영 체제에 따라 서로 다르고 형식의 편집 컨트롤 (단일 또는 여러 줄). 이러한 제한에 대 한 자세한 내용은 참조 하세요. [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext)합니다.

컨트롤에서이 한도 변경 하려면 재정의 `OnCreate()` 에 대 한 함수에 `CEditView` 클래스 및 코드의 다음 줄을 삽입 합니다.

[!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/cpp/ceditview-class_1.cpp)]

형식의 개체 `CEditView` (또는에서 파생 된 유형의 `CEditView`)은 다음과 같이 제한:

- `CEditView` true는 구현 하지 않는 표시는 WYSIWYG ()을 편집 합니다. 화면의 가독성 및 일치 하는 인쇄 된 출력 간에 선택할 있는 `CEditView` 화면 가독성을 높이기 위해 옵트아웃 합니다.

- `CEditView` 단일 글꼴로 텍스트를 표시할 수 있습니다. 서식이 없는 특수 문자 지원 됩니다. 클래스를 참조 하세요 [CRichEditView](../../mfc/reference/cricheditview-class.md) 큰 기능에 대 한 합니다.

- 텍스트의 크기는 `CEditView` 포함 될 수 있습니다 제한 됩니다. 제한은 동일 하 게 된 `CEdit` 제어 합니다.

에 대 한 자세한 `CEditView`를 참조 하세요 [파생 된 뷰 클래스에서에서 사용할 수 있는 MFC](../../mfc/derived-view-classes-available-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="ceditview"></a>  CEditView::CEditView

`CEditView` 형식의 개체를 생성합니다.

```
CEditView();
```

### <a name="remarks"></a>설명

개체를 생성 한 후 호출 해야 합니다 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 편집 컨트롤을 사용 하기 전에 함수입니다. 클래스를 파생 하는 경우 `CEditView` 사용 하 여 템플릿을 추가할 `CWinApp::AddDocTemplate`를 모두이 생성자를 호출 하는 프레임 워크 및 `Create` 함수.

##  <a name="dwstyledefault"></a>  CEditView::dwStyleDefault

기본 스타일을 포함 하는 `CEditView` 개체입니다.

```
static const DWORD dwStyleDefault;
```

### <a name="remarks"></a>설명

이 정적 멤버를 전달 합니다 *dwStyle* 의 매개 변수를 `Create` 함수에 대 한 기본 스타일을 가져오려고는 `CEditView` 개체입니다.

##  <a name="findtext"></a>  CEditView::FindText

호출 된 `FindText` 검색할 함수는 `CEditView` 개체의 텍스트 버퍼입니다.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bNext = TRUE,
    BOOL bCase = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*bNext*<br/>
검색 방향을 지정합니다. TRUE 이면 검색 방향을 버퍼의 끝에 다가가입니다. FALSE 이면 검색 방향을 버퍼의 시작 부분입니다.

*bCase*<br/>
검색은 대/소문자 구분 여부를 지정 합니다. True 이면 검색은 대/소문자 구분 합니다. FALSE 이면 검색은 대/소문자 구분이 아님.

### <a name="return-value"></a>반환 값

검색 텍스트가 발견 되는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수에서 지정 된 텍스트에 대 한 버퍼에서 텍스트를 검색 *lpszFind*지정 하는 방향에서 현재 선택 영역에서 시작 *다음*, 이며 로지정된대/소문자구분*bCase*합니다. 텍스트가 있으면 선택 찾은 텍스트를 설정 하 고 0이 아닌 값을 반환 합니다. 텍스트가 없으면 함수가 0을 반환 합니다.

일반적으로 필요가 없습니다를 호출 하는 `FindText` 함수를 재정의 하지 않으면 `OnFindNext`를 호출 하는 `FindText`합니다.

##  <a name="getbufferlength"></a>  CEditView::GetBufferLength

편집 컨트롤의 버퍼를 null 종결자를 포함 하지 않습니다의 현재 문자 번호를 가져오려면이 함수를 호출 합니다.

```
UINT GetBufferLength() const;
```

### <a name="return-value"></a>반환 값

버퍼에 있는 문자열의 길이입니다.

##  <a name="geteditctrl"></a>  CEditView::GetEditCtrl

호출 `GetEditCtrl` 편집 보기에서 사용 하는 편집 컨트롤에 대 한 참조를 가져오려고 합니다.

```
CEdit& GetEditCtrl() const;
```

### <a name="return-value"></a>반환 값

`CEdit` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 컨트롤은 형식의 [CEdit](../../mfc/reference/cedit-class.md)이므로 사용 하 여 직접 Windows 편집 컨트롤을 조작할 수는 `CEdit` 멤버 함수입니다.

> [!CAUTION]
>  사용 하는 `CEdit` 개체 기본 Windows의 상태 변경 컨트롤을 편집할 수 있습니다. 예를 들어, 사용 하는 탭 설정 하지 변경 해야 합니다 [CEdit::SetTabStops](../../mfc/reference/cedit-class.md#settabstops) 때문에 함수 `CEditView` 인쇄 및 편집 컨트롤에서 모두 사용에 대 한 이러한 설정은 캐시 합니다. 대신 [CEditView::SetTabStops](#settabstops)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#66](../../mfc/codesnippet/cpp/ceditview-class_2.cpp)]

##  <a name="getprinterfont"></a>  CEditView::GetPrinterFont

호출 `GetPrinterFont` 에 대 한 포인터를 가져오려면를 [CFont](../../mfc/reference/cfont-class.md) 현재 프린터 글꼴을 설명 하는 개체입니다.

```
CFont* GetPrinterFont() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CFont` ; 현재 프린터 글꼴을 지정 하는 개체 프린터 글꼴을 설정 하지 않은 경우 NULL입니다. 해당 포인터는 임시적이며, 나중에 사용하려고 저장하면 안됩니다.

### <a name="remarks"></a>설명

경우 프린터 글꼴에 설정 되어 있지 기본 동작의 인쇄를 `CEditView` 클래스 표시에 사용 되는 동일한 글꼴로 인쇄 하는 것입니다.

현재 프린터 글꼴을 확인 하려면이 함수를 사용 합니다. 사용 하 여 원하는 프린터 글꼴 없으면 [CEditView::SetPrinterFont](#setprinterfont) 를 변경 합니다.

##  <a name="getselectedtext"></a>  CEditView::GetSelectedText

호출 `GetSelectedText` 선택한 텍스트를 복사 하는 `CString` 선택 또는 선택 영역에 있는 첫 번째 캐리지 리턴 문자 앞에 있는 문자 끝까지 개체입니다.

```
void GetSelectedText(CString& strResult) const;
```

### <a name="parameters"></a>매개 변수

*strResult*<br/>
에 대 한 참조를 `CString` 선택한 텍스트를 수신 하는 개체입니다.

##  <a name="lockbuffer"></a>  CEditView::LockBuffer

버퍼에 대 한 포인터를 가져오려면이 함수를 호출 합니다. 버퍼는 수정할 수 없습니다.

```
LPCTSTR LockBuffer() const;
```

### <a name="return-value"></a>반환 값

편집 컨트롤의 버퍼에 대 한 포인터입니다.

##  <a name="onfindnext"></a>  CEditView::OnFindNext

지정 하는 텍스트에 대 한 버퍼에서 텍스트를 검색 *lpszFind*를 지정 하는 방향에 *다음*를 지정 된 대/소문자를 사용 하 여 *bCase*합니다.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*bNext*<br/>
검색 방향을 지정합니다. TRUE 이면 검색 방향을 버퍼의 끝에 다가가입니다. FALSE 이면 검색 방향을 버퍼의 시작 부분입니다.

*bCase*<br/>
검색은 대/소문자 구분 여부를 지정 합니다. True 이면 검색은 대/소문자 구분 합니다. FALSE 이면 검색은 대/소문자 구분이 아님.

### <a name="remarks"></a>설명

검색이 현재 선택 영역의 시작 부분에서 시작 하 고 호출을 통해 이루어집니다 [FindText](#findtext)합니다. 기본 구현에서는 `OnFindNext` 호출 [OnTextNotFound](#ontextnotfound) 텍스트가 없는 경우.

재정의 `OnFindNext` 방식을 변경할 수는 `CEditView`-파생된 개체가 텍스트를 검색 합니다. `CEditView` 호출 `OnFindNext` 사용자 표준 찾기 대화 상자에서 다음 찾기 단추를 선택 하는 경우.

##  <a name="onreplaceall"></a>  CEditView::OnReplaceAll

`CEditView` 호출 `OnReplaceAll` 사용자 표준 바꾸기 대화 상자에서 모두 바꾸기 단추를 선택 하는 경우.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*lpszReplace*<br/>
검색 텍스트를 바꿀 텍스트입니다.

*bCase*<br/>
검색은 대/소문자 구분 여부를 지정 합니다. True 이면 검색은 대/소문자 구분 합니다. FALSE 이면 검색은 대/소문자 구분이 아님.

### <a name="remarks"></a>설명

`OnReplaceAll` 지정 하는 텍스트에 대 한 버퍼에서 텍스트를 검색 *lpszFind*에 의해 지정 된 대/소문자를 사용 하 여 *bCase*합니다. 현재 선택 영역의 시작 부분에서 검색이 시작 됩니다. 각 시간 검색 텍스트가 발견 될,이 함수는 지정 하는 텍스트를 사용 하 여 텍스트의 해당 항목을 바꿉니다 *lpszReplace*합니다. 검색에 대 한 호출을 통해 이루어집니다 [FindText](#findtext)합니다. 기본 구현에서는 [OnTextNotFound](#ontextnotfound) 텍스트가 없는 경우 호출 됩니다.

현재 선택 영역이 일치 하지 않는 경우 *lpszFind*를 선택 하 여 지정 된 텍스트의 처음으로 업데이트 됩니다 *lpszFind* 및 대체 수행 되지 않습니다. 이 수 있도록 선택 바꿀 텍스트 일치 하지 않는 경우 수행 하려는 작업이 무엇 인지 확인 합니다.

재정의 `OnReplaceAll` 방식을 변경할 수는 `CEditView`-파생된 개체가 텍스트를 바꿉니다.

##  <a name="onreplacesel"></a>  CEditView::OnReplaceSel

`CEditView` 호출 `OnReplaceSel` 사용자 표준 바꾸기 대화 상자에서 [바꾸기] 단추를 선택 하는 경우.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

*bNext*<br/>
검색 방향을 지정합니다. TRUE 이면 검색 방향을 버퍼의 끝에 다가가입니다. FALSE 이면 검색 방향을 버퍼의 시작 부분입니다.

*bCase*<br/>
검색은 대/소문자 구분 여부를 지정 합니다. True 이면 검색은 대/소문자 구분 합니다. FALSE 이면 검색은 대/소문자 구분이 아님.

*lpszReplace*<br/>
찾은 텍스트를 바꿀 텍스트입니다.

### <a name="remarks"></a>설명

선택 영역을 바꾼 후이 함수에서 지정 된 텍스트의 다음 항목에 대 한 버퍼에서 텍스트를 검색 *lpszFind*, 지정 된 방향의 *다음*, 대/소문자 구분을 사용 하 여 지정 된 *bCase*합니다. 검색에 대 한 호출을 통해 이루어집니다 [FindText](#findtext)합니다. 텍스트가 없으면 [OnTextNotFound](#ontextnotfound) 라고 합니다.

재정의 `OnReplaceSel` 방식을 변경할 수는 `CEditView`-파생된 개체가 선택한 텍스트를 바꿉니다.

##  <a name="ontextnotfound"></a>  CEditView::OnTextNotFound

Windows 함수를 호출 하는 기본 구현에서 변경 하려면이 함수를 재정의 `MessageBeep`합니다.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 텍스트입니다.

##  <a name="printinsiderect"></a>  CEditView::PrintInsideRect

호출 `PrintInsideRect` 하 여 지정 된 사각형에서 텍스트를 인쇄 하 *rectLayout*합니다.

```
UINT PrintInsideRect(
    CDC *pDC,
    RECT& rectLayout,
    UINT nIndexStart,
    UINT nIndexStop);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 장치 컨텍스트 포인터입니다.

*rectLayout*<br/>
에 대 한 참조를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조체](/windows/desktop/api/windef/ns-windef-tagrect) 텍스트를 렌더링할의 사각형을 지정 합니다.

*nIndexStart*<br/>
렌더링할 첫 번째 문자의 버퍼 내의 인덱스입니다.

*nIndexStop*<br/>
렌더링할의 마지막 문자 다음 문자의 버퍼 내의 인덱스입니다.

### <a name="return-value"></a>반환 값

인쇄할 다음 문자의 인덱스 (즉, 렌더링의 마지막 문자 다음 문자).

### <a name="remarks"></a>설명

경우는 `CEditView` 렌더링 사각형 내에서 텍스트가 줄 바꿈되지, 컨트롤 스타일 ES_AUTOHSCROLL 없습니다. 컨트롤 스타일 ES_AUTOHSCROLL 않은, 경우에 텍스트 사각형의 오른쪽 가장자리에 잘립니다.

합니다 `rect.bottom` 의 요소를 *rectLayout* 개체 텍스트를 차지 하 고 있는 원래의 사각형의 일부를 정의 하는 사각형의 차원이 변경 됩니다.

##  <a name="serializeraw"></a>  CEditView::SerializeRaw

호출 `SerializeRaw` 할를 `CArchive` 읽기 개체 또는 텍스트를 작성 합니다 `CEditView` 개체를 텍스트 파일입니다.

```
void SerializeRaw(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
에 대 한 참조를 `CArchive` 직렬화 된 텍스트를 저장 하는 개체입니다.

### <a name="remarks"></a>설명

`SerializeRaw` 다른 `CEditView`의 내부 구현의 `Serialize` 는 읽고 개체 설명 데이터를 이전 하지 않고만 텍스트를 씁니다.

##  <a name="setprinterfont"></a>  CEditView::SetPrinterFont

호출 `SetPrinterFont` 프린터 글꼴을 지정 된 글꼴을 설정 하려면 *pFont*합니다.

```
void SetPrinterFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
형식의 개체에 대 한 포인터 `CFont`합니다. NULL 인 경우 인쇄에 사용 된 글꼴의 글꼴을 기반으로 합니다.

### <a name="remarks"></a>설명

항상 인쇄에 대 한 특정 글꼴을 사용 하 여 보기를 하려는 경우에 대 한 호출이 `SetPrinterFont` 클래스의 `OnPreparePrinting` 함수입니다. 보기의 내용을 인쇄 전에 수행 하는 글꼴 변경 되므로이 가상 함수는 인쇄 발생 하기 전에 호출 됩니다.

##  <a name="settabstops"></a>  CEditView::SetTabStops

표시 및 인쇄에 사용 되는 탭 정지를 설정 하려면이 함수를 호출 합니다.

```
void SetTabStops(int nTabStops);
```

### <a name="parameters"></a>매개 변수

*nTabStops*<br/>
대화 상자 단위에서 각 탭 정지의 너비입니다.

### <a name="remarks"></a>설명

단일 탭 정지 너비만 지원 됩니다. ( `CEdit` 개체는 여러 탭 너비를 지원 합니다.) 같은 인쇄 하거나 표시 시점에 사용 된 글꼴의 평균 문자 너비 (대문자 및 소문자 알파벳 문자만 기반)이 1-4는 대화 상자 단위에서 너비는 됩니다. 사용 하지 않아야 `CEdit::SetTabStops` 있으므로 `CEditView` 탭 정지 값을 캐시 해야 합니다.

이 함수를 호출 하는 개체의 탭만 수정 합니다. 탭을 변경 하려면 각각에 대 한 중지 `CEditView` 응용 프로그램에서 개체를 각 개체의 호출 `SetTabStops` 함수입니다.

### <a name="example"></a>예제

이 코드 조각은 컨트롤에서 사용 되는 글꼴을 신중 하 게 측정 하 여 모든 네 번째 문자를 컨트롤의 탭 정지를 설정 합니다.

[!code-cpp[NVC_MFCDocView#67](../../mfc/codesnippet/cpp/ceditview-class_3.cpp)]

##  <a name="unlockbuffer"></a>  CEditView::UnlockBuffer

버퍼를 잠금 해제 하려면이 멤버 함수를 호출 합니다.

```
void UnlockBuffer() const;
```

### <a name="remarks"></a>설명

호출 `UnlockBuffer` 반환한 포인터를 사용 하 여 완료 한 후 [LockBuffer](#lockbuffer)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 SUPERPAD](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)
