---
title: CPrintInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 96b6204fe46cb624d22506b2d3e5c1d7621b1865
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772217"
---
# <a name="cprintinfo-structure"></a>CPrintInfo 구조체

인쇄 또는 인쇄 미리 보기 작업에 대 한 정보를 저장합니다.

## <a name="syntax"></a>구문

```
struct CPrintInfo
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPrintInfo::GetFromPage](#getfrompage)|인쇄할 첫 페이지의 수를 반환 합니다.|
|[CPrintInfo::GetMaxPage](#getmaxpage)|문서의 마지막 페이지의 수를 반환합니다.|
|[CPrintInfo::GetMinPage](#getminpage)|문서의 첫 번째 페이지의 수를 반환합니다.|
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|결합 된 DocObject 인쇄 작업의 인쇄 DocObject 항목의 첫 번째 페이지 앞 페이지 수를 반환 합니다.|
|[CPrintInfo::GetToPage](#gettopage)|인쇄할 마지막 페이지의 수를 반환 합니다.|
|[CPrintInfo::SetMaxPage](#setmaxpage)|문서의 마지막 페이지 번호를 설정합니다.|
|[CPrintInfo::SetMinPage](#setminpage)|문서의 첫 번째 페이지의 번호를 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|프레임 워크가 인쇄 루프를 계속 해야 하는지 여부를 나타내는 플래그를 포함 합니다.|
|[CPrintInfo::m_bDirect](#m_bdirect)|직접 (표시 하지 않고 인쇄 대화 상자) 문서를 인쇄 하는지 여부를 나타내는 플래그를 포함 합니다.|
|[CPrintInfo::m_bDocObject](#m_bdocobject)|인쇄 중인 문서 DocObject 인지 여부를 나타내는 플래그를 포함 합니다.|
|[CPrintInfo::m_bPreview](#m_bpreview)|문서를 미리 보고 되 고 있는지 여부를 나타내는 플래그를 포함 합니다.|
|[CPrintInfo::m_dwFlags](#m_dwflags)|DocObject의 인쇄 작업을 지정합니다.|
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|사용자가 만든 구조에 대 한 포인터를 포함합니다.|
|[CPrintInfo::m_nCurPage](#m_ncurpage)|현재 인쇄 중인 페이지의 번호를 식별 합니다.|
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|현재 인쇄 작업에 대 한 운영 체제에서 할당 된 작업 번호를 지정 합니다.|
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|미리 보기 창에 표시 되는 페이지 번호를 식별 1 또는 2입니다.|
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|결합 된 DocObject 인쇄 작업에서 특정 DocObject의 첫 페이지의 오프셋을 지정합니다.|
|[CPrintInfo::m_pPD](#m_ppd)|에 대 한 포인터를 포함 합니다 `CPrintDialog` 인쇄 대화 상자에 사용 되는 개체입니다.|
|[CPrintInfo::m_rectDraw](#m_rectdraw)|현재 사용 가능한 페이지 영역을 정의 하는 사각형을 지정 합니다.|
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|페이지 번호 표시에 대 한 형식 문자열을 포함합니다.|

## <a name="remarks"></a>설명

`CPrintInfo` 구조 이며 기본 클래스를 포함 하지 않습니다.

프레임 워크의 개체를 만듭니다 `CPrintInfo` 될 때마다 인쇄 또는 인쇄 미리 보기 명령을 선택 되 고 명령이 완료 되 면 제거 합니다.

`CPrintInfo` 현재 인쇄 중인 페이지와 같은 인쇄 작업의 현재 상태와 인쇄할 페이지 범위와 같은 전체 인쇄 작업에 대 한 정보를 포함 합니다. 일부 정보가 저장 됩니다 관련 [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체;이 개체는 인쇄 대화 상자에서 사용자가 입력 한 값을 포함 합니다.

`CPrintInfo` 개체 인쇄 중 프레임 워크와 뷰 클래스 간에 전달 되 고 둘 사이의 정보를 교환 하는 데 사용 됩니다. 예를 들어, 프레임 워크에 알립니다 뷰 클래스 값을 할당 하 여 인쇄 문서 페이지의 `m_nCurPage` 소속 `CPrintInfo`, 보기 클래스 값을 검색 하 고 지정된 된 페이지의 실제 인쇄를 수행 합니다.

또 다른 예로는 문서의 길이가 알려지지 않은 인쇄할 때까지 경우입니다. 이 이런 경우 뷰 클래스 페이지 인쇄 될 때마다 문서 끝 테스트 합니다. 뷰 클래스를 설정 하는 끝에 도달 하면 합니다 `m_bContinuePrinting` 소속 `CPrintInfo` 을 FALSE로 인쇄 루프를 중지 하기 위해 프레임 워크에 알립니다.

`CPrintInfo` 멤버 함수를 사용해 `CView` 나열 아래에 있는 "참고 하십시오." Microsoft Foundation Class 라이브러리에서 제공 하는 인쇄 아키텍처에 대 한 자세한 내용은 참조 하세요. [프레임 Windows](../../mfc/frame-windows.md) 하 고 [문서/뷰 아키텍처](../../mfc/document-view-architecture.md) 문서 [ 인쇄](../../mfc/printing.md) 고 [인쇄 합니다. 다중 페이지 문서](../../mfc/multipage-documents.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CPrintInfo`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage

인쇄할 첫 페이지의 수를 검색 하려면이 함수를 호출 합니다.

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>반환 값

인쇄할 첫 페이지의 수입니다.

### <a name="remarks"></a>설명

인쇄 대화 상자에서 사용자가 지정 된 값 이며에 저장 되는 `CPrintDialog` 참조 하는 개체를 `m_pPD` 멤버입니다. 사용자가 값을 지정 하지 않으면 기본 문서의 첫 번째 페이지입니다.

##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage

문서의 마지막 페이지 번호를 검색 하려면이 함수를 호출 합니다.

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>반환 값

문서의 마지막 페이지의 수입니다.

### <a name="remarks"></a>설명

이 값은 `CPrintDialog` 개체에서 참조 하는 `m_pPD` 멤버입니다.

##  <a name="getminpage"></a>  CPrintInfo::GetMinPage

문서의 첫 번째 페이지의 번호를 검색 하려면이 함수를 호출 합니다.

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>반환 값

문서의 첫 번째 페이지의 수입니다.

### <a name="remarks"></a>설명

이 값은 `CPrintDialog` 개체에서 참조 하는 `m_pPD` 멤버입니다.

##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage

DocObject 클라이언트에서 여러 DocObject 항목을 인쇄할 때 오프셋을 검색 하려면이 함수를 호출 합니다.

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>반환 값

결합 된 DocObject의 인쇄 DocObject 항목의 첫 번째 페이지 앞 페이지 수가 인쇄 작업입니다.

### <a name="remarks"></a>설명

이 값에서 참조 되는 `m_nOffsetPage` 멤버입니다. 문서의 첫 번째 페이지에는 번호가 `m_nOffsetPage` 값 + 1 다른 활성 문서를 사용 하 여 DocObject를 인쇄 합니다. 합니다 `m_nOffsetPage` 멤버는 사용할 경우에만 `m_bDocObject` 값은 TRUE입니다.

##  <a name="gettopage"></a>  CPrintInfo::GetToPage

인쇄할 마지막 페이지 번호를 검색 하려면이 함수를 호출 합니다.

```
UINT GetToPage() const;
```

### <a name="return-value"></a>반환 값

인쇄할 마지막 페이지의 수입니다.

### <a name="remarks"></a>설명

인쇄 대화 상자에서 사용자가 지정 된 값 이며에 저장 되는 `CPrintDialog` 참조 하는 개체를 `m_pPD` 멤버입니다. 사용자가 값을 지정 하지 않으면 기본값은 문서의 마지막 페이지입니다.

##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting

프레임 워크가 인쇄 루프를 계속 해야 하는지 여부를 나타내는 플래그를 포함 합니다.

### <a name="remarks"></a>설명

인쇄 때 페이지 번호 매기기를 수행 하는 경우의 재정의에서 FALSE로이 멤버를 설정할 수 있습니다 `CView::OnPrepareDC` 문서의 끝에 도달 합니다. 사용 하 여 인쇄 작업의 시작 부분에서 문서 길이 지정한 경우이 변수를 수정할 필요가 없습니다를 `SetMaxPage` 멤버 함수입니다. `m_bContinuePrinting` 멤버는 BOOL 형식의 공용 변수입니다.

##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect

프레임 워크를 직접 인쇄;에 대 한 인쇄 대화 상자를 무시할 수는 경우이 멤버를 TRUE로 설정 FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

셸 또는 인쇄 완료 되 면에서 인쇄할 때 인쇄 대화 상자는 일반적으로 무시 됩니다 ID ID_FILE_PRINT_DIRECT 명령을 사용 합니다.

일반적으로이 멤버를 변경 하지 경우이 변경 하기 전에 호출 되지만 [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) 의 재정의 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)합니다.

##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject

인쇄 중인 문서 DocObject 인지 여부를 나타내는 플래그를 포함 합니다.

### <a name="remarks"></a>설명

데이터 멤버 `m_dwFlags` 고 `m_nOffsetPage` 유효 하지 않으면이 플래그는 TRUE입니다.

##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview

문서를 미리 보고 되 고 있는지 여부를 나타내는 플래그를 포함 합니다.

### <a name="remarks"></a>설명

이 명령은 사용자에 따라 실행 프레임 워크에 의해 설정 됩니다. 인쇄 미리 보기 작업에 대 한 인쇄 대화 상자를 표시 되지 않습니다. `m_bPreview` 멤버는 BOOL 형식의 공용 변수입니다.

##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags

DocObject의 인쇄 작업을 지정 하는 플래그의 조합을 포함 합니다.

### <a name="remarks"></a>설명

유효한 경우에만 데이터 멤버 `m_bDocObject` 은 TRUE입니다.

다음 값 중 하나 이상의 플래그를 수 있습니다.

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData

사용자가 만든 구조에 대 한 포인터를 포함합니다.

### <a name="remarks"></a>설명

뷰 클래스에 저장 하지 않으려는 경우는 인쇄 관련 데이터를 저장 하려면이 사용할 수 있습니다. `m_lpUserData` 멤버인 LPVOID 형식의 공용 변수입니다.

##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage

현재 페이지의 수를 포함합니다.

### <a name="remarks"></a>설명

프레임 워크 호출 `CView::OnPrepareDC` 하 고 `CView::OnPrint` 번 때마다;이 멤버에 대해 다른 값을 지정 하는 문서의 각 페이지에 대 한 해당 값의 범위에서 반환한 값에서 `GetFromPage` 에서 반환 되는 `GetToPage`합니다. 이 멤버의 재정의에서 사용 하 여 `CView::OnPrepareDC` 및 `CView::OnPrint` 문서의 지정 된 페이지를 인쇄할 수 있습니다.

미리 보기 모드를 처음 호출 하면 프레임 워크 문서 페이지는 처음에 미리 볼 수는 확인 하려면이 멤버의 값을 읽습니다. 재정의에서이 멤버의 값을 설정할 수 있습니다 `CView::OnPreparePrinting` 미리 보기 모드로 들어갈 때 문서에 사용자의 현재 위치를 유지 관리 합니다. `m_nCurPage` 멤버인 UINT 형식의 공용 변수입니다.

##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber

현재 인쇄 작업에 대 한 운영 체제에서 할당 된 작업 수를 나타냅니다.

### <a name="remarks"></a>설명

작업이 인쇄 아직 하지 않은 경우이 값이 SP_ERROR을 수 있습니다 (즉는 `CPrintInfo` 개체 새로 생성 및 인쇄를 아직 사용 되지 않은), 아니면 시작 작업에서 오류가 발생 했습니다.

##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages

미리 보기 모드에서 표시 되는 페이지 수를 포함 합니다. 1 또는 2 수 있습니다.

### <a name="remarks"></a>설명

`m_nNumPreviewPages` 멤버인 UINT 형식의 공용 변수입니다.

##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage

특정 DocObject의 첫 번째 페이지를 전체 DocObject 인쇄 작업을 이전 하는 페이지 수를 포함 합니다.

##  <a name="m_ppd"></a>  CPrintInfo::m_pPD

에 대 한 포인터를 포함 합니다 `CPrintDialog` 인쇄 작업에 대 한 인쇄 대화 상자를 표시 하는 데 사용 되는 개체입니다.

### <a name="remarks"></a>설명

합니다 `m_pPD` 멤버에 대 한 포인터로 선언 된 공용 변수는 `CPrintDialog`합니다.

##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw

논리적 좌표에서 페이지의 사용 가능한 그리기 영역을 지정합니다.

### <a name="remarks"></a>설명

재정의에서 참조 하는 것이 좋습니다 `CView::OnPrint`합니다. 머리글과 바닥글 등 인쇄 한 후 영역을 계속 사용할 수 추적를이 멤버를 사용할 수 있습니다. 합니다 `m_rectDraw` 멤버는 형식의 공용 변수 `CRect`합니다.

##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc

인쇄 미리 보기에는 동안 페이지 번호를 표시 하는 데 사용 되는 형식 문자열을 포함 이 문자열 두 부분 문자열을 단일 페이지 표시에 대 한 '\n' 문자로 각각 이중 페이지 표시에 대 한 구성 됩니다.

### <a name="remarks"></a>설명

프레임 워크는 기본값으로 "페이지 %u\nPages%u-%u\n"를 사용합니다. 페이지 번호에 대 한 다른 형식으로 하려는 경우 형식 문자열의 재정의 지정 `CView::OnPreparePrinting`합니다. 합니다 `m_strPageDesc` 멤버는 형식의 공용 변수 `CString`합니다.

##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage

문서의 마지막 페이지의 수를 지정 하려면이 함수를 호출 합니다.

```
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>매개 변수

*nMaxPage*<br/>
문서의 마지막 페이지 번호입니다.

### <a name="remarks"></a>설명

이 값은 `CPrintDialog` 개체에서 참조 하는 `m_pPD` 멤버입니다. 문서의 길이 인쇄 하기 전에 알 수 있으면의 재정의에서이 함수를 호출 `CView::OnPreparePrinting`합니다. 문서 인쇄 대화 상자에서 사용자가 지정한 설정에 따라 달라 집니다, 하는 경우의 재정의에서이 함수를 호출할 `CView::OnBeginPrinting`합니다. 문서의 길이 알 수 없는 인쇄 될 때까지 사용 하 여는 `m_bContinuePrinting` 인쇄 루프를 제어 하는 멤버입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)합니다.

##  <a name="setminpage"></a>  CPrintInfo::SetMinPage

문서의 첫 번째 페이지의 수를 지정 하려면이 함수를 호출 합니다.

```
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>매개 변수

*nMinPage*<br/>
문서의 첫 번째 페이지 번호입니다.

### <a name="remarks"></a>설명

일반적으로 페이지 번호는 1부터 시작 합니다. 이 값은 `CPrintDialog` 개체에서 참조 하는 `m_pPD` 멤버입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView::OnPrint](../../mfc/reference/cview-class.md#onprint)
