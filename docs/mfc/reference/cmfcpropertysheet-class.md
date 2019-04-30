---
title: CMFCPropertySheet 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::CMFCPropertySheet
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPage
- AFXPROPERTYSHEET/CMFCPropertySheet::AddPageToTree
- AFXPROPERTYSHEET/CMFCPropertySheet::AddTreeCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::EnablePageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::GetHeaderHeight
- AFXPROPERTYSHEET/CMFCPropertySheet::GetLook
- AFXPROPERTYSHEET/CMFCPropertySheet::GetNavBarWidth
- AFXPROPERTYSHEET/CMFCPropertySheet::GetTab
- AFXPROPERTYSHEET/CMFCPropertySheet::InitNavigationControl
- AFXPROPERTYSHEET/CMFCPropertySheet::OnActivatePage
- AFXPROPERTYSHEET/CMFCPropertySheet::OnDrawPageHeader
- AFXPROPERTYSHEET/CMFCPropertySheet::OnRemoveTreePage
- AFXPROPERTYSHEET/CMFCPropertySheet::RemoveCategory
- AFXPROPERTYSHEET/CMFCPropertySheet::RemovePage
- AFXPROPERTYSHEET/CMFCPropertySheet::SetIconsList
- AFXPROPERTYSHEET/CMFCPropertySheet::SetLook
helpviewer_keywords:
- CMFCPropertySheet [MFC], CMFCPropertySheet
- CMFCPropertySheet [MFC], AddPage
- CMFCPropertySheet [MFC], AddPageToTree
- CMFCPropertySheet [MFC], AddTreeCategory
- CMFCPropertySheet [MFC], EnablePageHeader
- CMFCPropertySheet [MFC], GetHeaderHeight
- CMFCPropertySheet [MFC], GetLook
- CMFCPropertySheet [MFC], GetNavBarWidth
- CMFCPropertySheet [MFC], GetTab
- CMFCPropertySheet [MFC], InitNavigationControl
- CMFCPropertySheet [MFC], OnActivatePage
- CMFCPropertySheet [MFC], OnDrawPageHeader
- CMFCPropertySheet [MFC], OnRemoveTreePage
- CMFCPropertySheet [MFC], RemoveCategory
- CMFCPropertySheet [MFC], RemovePage
- CMFCPropertySheet [MFC], SetIconsList
- CMFCPropertySheet [MFC], SetLook
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
ms.openlocfilehash: 7e5b553e6a10bee0e5b05bb32b9af3069269ca91
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344223"
---
# <a name="cmfcpropertysheet-class"></a>CMFCPropertySheet 클래스

`CMFCPropertySheet` 클래스는 각 속성 페이지가 페이지 탭, 도구 모음 단추, 트리 컨트롤 노드 또는 목록 항목으로 표시되는 속성 시트를 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertySheet : public CPropertySheet
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|`CMFCPropertySheet` 개체를 생성합니다.|
|`CMFCPropertySheet::~CMFCPropertySheet`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCPropertySheet::AddPage](#addpage)|속성 시트에 페이지를 추가합니다.|
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|트리 컨트롤에 새 속성 페이지를 추가합니다.|
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|트리 컨트롤에 새 노드를 추가합니다.|
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.|
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|현재 머리글의 높이를 검색합니다.|
|[CMFCPropertySheet::GetLook](#getlook)|현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.|
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|탐색 모음의 너비(픽셀)를 검색합니다.|
|[CMFCPropertySheet::GetTab](#gettab)|현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.|
|`CMFCPropertySheet::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|현재 속성 시트 컨트롤의 모양을 초기화합니다.|
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.|
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|사용자 지정 속성 페이지 머리글을 그리기 위해 프레임워크에서 호출됩니다.|
|`CMFCPropertySheet::OnInitDialog`|처리를 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) 메시지입니다. (재정의 [cpropertysheet:: Oninitdialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.|
|`CMFCPropertySheet::PreTranslateMessage`|디스패치 되기 전에 창 메시지를 변환 합니다 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 함수입니다. ( `CPropertySheet::PreTranslateMessage`을 재정의합니다.)|
|[CMFCPropertySheet::RemoveCategory](#removecategory)|트리 컨트롤에서 노드를 제거합니다.|
|[CMFCPropertySheet::RemovePage](#removepage)|속성 시트에서 속성 페이지를 제거합니다.|
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.|
|[CMFCPropertySheet::SetLook](#setlook)|속성 시트의 모양을 지정합니다.|

## <a name="remarks"></a>설명

`CMFCPropertySheet` 클래스는 속성 시트(탭 대화 상자라고도 함)를 나타냅니다. `CMFCPropertySheet` 클래스는 다양한 방식으로 속성 페이지를 표시할 수 있습니다.

응용 프로그램에서 `CMFCPropertySheet` 클래스를 사용하려면 다음 단계를 수행합니다.

1. `CMFCPropertySheet` 클래스에서 클래스를 파생시키고 클래스 이름(예: CMyPropertySheet)을 지정합니다.

1. 생성 된 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) 각 속성 페이지에 대 한 개체입니다.

1. 호출 된 [cmfcpropertysheet:: Setlook](#setlook) CMyPropertySheet 생성자에서 메서드. 이 메서드의 매개 변수는 속성 페이지가 속성 시트의 위쪽이나 왼쪽에 있는 탭, Microsoft OneNote 속성 시트 스타일의 탭, Microsoft Outlook 도구 모음 컨트롤의 단추, 트리 컨트롤의 노드 또는 속성 시트의 왼쪽에 있는 항목 목록으로 표시되도록 지정합니다.

1. 속성 시트 스타일의 Microsoft Outlook 도구 모음을 만든 경우 호출 된 [CMFCPropertySheet::SetIconsList](#seticonslist) 속성 페이지와 함께 이미지 목록을 연결 하는 방법입니다.

1. 호출 된 [cmfcpropertysheet:: Addpage](#addpage) 메서드가 각 속성 페이지에 대 한 합니다.

1. `CMFCPropertySheet` 컨트롤을 만들고 해당 `DoModal` 메서드를 호출합니다.

## <a name="illustrations"></a>그림

다음 그림에서는 포함된 Microsoft Outlook 도구 모음 스타일의 속성 시트를 보여 줍니다. Outlook 도구 모음은 속성 시트의 왼쪽에 나타납니다.

![CMFCPropertySheet 색 컨트롤](../../mfc/reference/media/cmfcpropertysheet_color.png "CMFCPropertySheet 색 컨트롤")

다음 그림에서는 포함 된 속성 시트를 보여 줍니다.는 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체입니다. 해당 개체는 표준 공용 컨트롤 속성 시트 스타일의 속성 시트입니다.

![CMFCPropertySheet 목록 및 속성 컨트롤](../../mfc/reference/media/cmfcpropertysheet_list.png "CMFCPropertySheet 목록 및 속성 컨트롤")

다음 그림에서는 트리 컨트롤 스타일의 속성 시트를 보여 줍니다.

![속성 트리](../../mfc/reference/media/proptree.png "속성 트리")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertysheet.h

##  <a name="addpage"></a>  CMFCPropertySheet::AddPage

속성 시트에 페이지를 추가합니다.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
[in] Page 개체에 대 한 포인터입니다. 이 매개 변수는 NULL 일 수 없습니다.

### <a name="remarks"></a>설명

이 메서드는 속성 시트의 오른쪽에 있는 탭으로 지정 된 속성 페이지를 추가합니다. 따라서 왼쪽에서 오른쪽 순서로 페이지를 추가 하려면이 메서드를 사용 합니다.

속성 시트 스타일 Microsoft Outlook의 경우 프레임 워크 속성 시트의 왼쪽에 있는 탐색 단추 목록을 표시 합니다. 이 메서드는 속성 페이지를 추가 하면 해당 단추가 목록에 추가 됩니다. 속성 페이지를 표시 하려면 해당 단추를 클릭 합니다. 속성 시트의 스타일에 대 한 자세한 내용은 참조 [cmfcpropertysheet:: Setlook](#setlook)합니다.

##  <a name="addpagetotree"></a>  CMFCPropertySheet::AddPageToTree

트리 컨트롤에 새 속성 페이지를 추가합니다.

```
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,
    CMFCPropertyPage* pPage,
    int nIconNum=-1,
    int nSelIconNum=-1);
```

### <a name="parameters"></a>매개 변수

*pCategory*<br/>
[in] 부모 트리 노드 또는 최상위 노드를 사용 하 여 지정된 된 페이지를 연결 하는 NULL 포인터입니다. 호출 된 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 이 포인터를 가져오는 방법입니다.

*pPage*<br/>
[in] 속성 페이지 개체에 대 한 포인터입니다.

*nIconNum*<br/>
[in] 아이콘 또는 없음 아이콘을 사용 하는 경우-1의 0부터 시작 인덱스입니다. 페이지 선택 하지 않은 경우 트리 컨트롤 속성 페이지 옆에 있는 아이콘을 표시 됩니다. 기본값은 -1입니다.

*nSelIconNum*<br/>
[in] 아이콘 또는 없음 아이콘을 사용 하는 경우-1의 0부터 시작 인덱스입니다. 페이지 선택 하면 아이콘 트리 컨트롤 속성 페이지 옆에 표시 됩니다. 기본값은 -1입니다.

### <a name="remarks"></a>설명

이 메서드는 트리 컨트롤의 리프로 속성 페이지를 추가합니다. 속성 페이지를 추가 하려면 만듭니다를 `CMFCPropertySheet` 개체를 호출 합니다 [cmfcpropertysheet:: Setlook](#setlook) 메서드를 *확인* 매개 변수 설정 `CMFCPropertySheet::PropSheetLook_Tree`, 다음이 메서드를 사용 하 여 속성 페이지를 추가 하려면 .

##  <a name="addtreecategory"></a>  CMFCPropertySheet::AddTreeCategory

트리 컨트롤에 새 노드를 추가합니다.

```
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,
    int nIconNum=-1,
    int nSelectedIconNum=-1,
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
[in] 노드의 이름입니다.

*nIconNum*<br/>
[in] 아이콘 또는 없음 아이콘을 사용 하는 경우-1의 0부터 시작 인덱스입니다. 페이지 선택 하지 않은 경우 트리 컨트롤 속성 페이지 옆에 있는 아이콘을 표시 됩니다. 기본값은 -1입니다.

*nSelectedIconNum*<br/>
[in] 아이콘 또는 없음 아이콘을 사용 하는 경우-1의 0부터 시작 인덱스입니다. 페이지 선택 하면 아이콘 트리 컨트롤 속성 페이지 옆에 표시 됩니다. 기본값은 -1입니다.

*pParentCategory*<br/>
[in] 부모 트리 노드 또는 최상위 노드를 사용 하 여 지정된 된 페이지를 연결 하는 NULL 포인터입니다. 이 매개 변수를 설정 합니다 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 메서드.

### <a name="return-value"></a>반환 값

트리 컨트롤의 새 노드에 대 한 포인터입니다.

### <a name="remarks"></a>설명

트리 컨트롤에는 라고도 범주에는 새 노드를 추가 하려면이 메서드를 사용 합니다. 노드를 추가 하려면 만듭니다는 `CMFCPropertySheet` 개체를 호출 합니다 [cmfcpropertysheet:: Setlook](#setlook) 메서드를 *확인* 매개 변수 설정 `CMFCPropertySheet::PropSheetLook_Tree`, 다음 노드를 추가 하려면이 메서드를 사용 하 여.

이 메서드의 반환 값에 대 한 후속 호출에서 사용 하 여 [CMFCPropertySheet::AddPageToTree](#addpagetotree) 하 고 [CMFCPropertySheet::AddTreeCategory](#addtreecategory)합니다.

##  <a name="cmfcpropertysheet"></a>  CMFCPropertySheet::CMFCPropertySheet

`CMFCPropertySheet` 개체를 생성합니다.

```
CMFCPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd=NULL,
    UINT iSelectPage=0);
```

### <a name="parameters"></a>매개 변수

*pszCaption*<br/>
[in] 속성 시트 캡션을 포함 하는 문자열입니다. NULL일 수 없습니다.

*nIDCaption*<br/>
[in] 속성 시트 캡션을 포함 하는 리소스 ID입니다.

*pParentWnd*<br/>
[in] 속성 시트의 부모 창은 응용 프로그램의 주 창 하는 경우에 NULL 부모 창에 대 한 포인터입니다. 기본값은 NULL입니다.

*iSelectPage*<br/>
[in] Top 속성 페이지의 0부터 시작 하는 인덱스입니다. 기본값은 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 참조에 대 한 매개 변수를 [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) 생성자입니다.

##  <a name="enablepageheader"></a>  CMFCPropertySheet::EnablePageHeader

각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.

```
void EnablePageHeader(int nHeaderHeight);
```

### <a name="parameters"></a>매개 변수

*nHeaderHeight*<br/>
[in] 픽셀에서 머리글의 높이입니다.

### <a name="remarks"></a>설명

값을 사용 하는 *nHeaderHeight* 사용자 지정 헤더를 그릴 매개 변수를 재정의 합니다 [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) 메서드.

##  <a name="getheaderheight"></a>  CMFCPropertySheet::GetHeaderHeight

현재 머리글의 높이를 검색합니다.

```
int GetHeaderHeight() const;
```

### <a name="return-value"></a>반환 값

픽셀에서 머리글의 높이입니다.

### <a name="remarks"></a>설명

호출 된 [CMFCPropertySheet::EnablePageHeader](#enablepageheader) 이 메서드를 호출 하기 전에 합니다.

##  <a name="getlook"></a>  CMFCPropertySheet::GetLook

현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.

```
PropSheetLook GetLook() const;
```

### <a name="return-value"></a>반환 값

속성 시트의 모양을 지정 하는 열거형 값 중 하나입니다. 가능한 값 목록을 열거형에 대 한 표의의 설명 섹션을 참조 하세요. [cmfcpropertysheet:: Setlook](#setlook)합니다.

##  <a name="getnavbarwidth"></a>  CMFCPropertySheet::GetNavBarWidth

탐색 모음의 너비를 가져옵니다.

```
int GetNavBarWidth() const;
```

### <a name="return-value"></a>반환 값

탐색 모음의 너비(픽셀)입니다.

##  <a name="gettab"></a>  CMFCPropertySheet::GetTab

현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.

```
CMFCTabCtrl& GetTab() const;
```

### <a name="return-value"></a>반환 값

내부 탭 컨트롤 개체입니다.

### <a name="remarks"></a>설명

속성 시트 탐색 단추 또는 탭된 페이지 집합 목록을 트리 컨트롤과 같은 다른 스타일의 표시 되도록 설정할 수 있습니다.

이 메서드를 호출 하기 전에 호출 된 [cmfcpropertysheet:: Setlook](#setlook) 속성 시트 컨트롤의 모양을 설정 하는 방법입니다. 그런 다음 호출을 [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) 내부 탭 컨트롤 개체를 초기화 하는 방법입니다. 탭 컨트롤 개체를 검색 한 다음 속성 시트의 탭을 사용 하는 개체를 사용 하려면이 메서드를 사용 합니다.

Microsoft onenote 스타일의 표시 속성 시트 컨트롤을 설정 하지 않으면이 메서드는 디버그 모드에서 어설션 합니다.

##  <a name="initnavigationcontrol"></a>  CMFCPropertySheet::InitNavigationControl

현재 속성 시트 컨트롤의 모양을 초기화합니다.

```
virtual CWnd* InitNavigationControl();
```

### <a name="return-value"></a>반환 값

속성 시트 컨트롤의 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

속성 시트 컨트롤 탭된 페이지, 트리 컨트롤 또는 탐색 단추의 목록을 집합과 같은 여러 가지 다양 한 형태로 나타날 수 있습니다. 사용 된 [cmfcpropertysheet:: Setlook](#setlook) 속성 시트 컨트롤의 모양을 지정 하는 방법입니다.

##  <a name="onactivatepage"></a>  CMFCPropertySheet::OnActivatePage

속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.

```
virtual void OnActivatePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
[in] Enabled 속성 페이지를 나타내는 속성 페이지 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본적으로이 메서드는 enabled 속성 페이지 스크롤될 확인 합니다. 현재 속성 시트 스타일의 Microsoft Outlook 창에 있으면이 메서드는 해당 Outlook 단추 선택된 상태를 설정 합니다.

##  <a name="ondrawpageheader"></a>  CMFCPropertySheet::OnDrawPageHeader

사용자 지정 속성 페이지에 대 한 헤더를 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDrawPageHeader(
    CDC* pDC,
    int nPage,
    CRect rectHeader);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*nPage*<br/>
[in] 0부터 시작 속성 페이지 번호입니다.

*rectHeader*<br/>
[in] 헤더를 그릴 위치를 지정 하는 경계 사각형입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 아무것도 수행하지 않습니다. 이 메서드를 재정의 하는 경우 호출 된 [CMFCPropertySheet::EnablePageHeader](#enablepageheader) 프레임 워크는이 메서드를 호출 하기 전에 합니다.

##  <a name="onremovetreepage"></a>  CMFCPropertySheet::OnRemoveTreePage

트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.

```
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
[in] 제거할 속성 페이지를 나타내는 속성 페이지 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="removecategory"></a>  CMFCPropertySheet::RemoveCategory

트리 컨트롤에서 노드를 제거합니다.

```
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```

### <a name="parameters"></a>매개 변수

*pCategory*<br/>
[in] 제거할 범주 (노드)에 대 한 포인터입니다.

### <a name="remarks"></a>설명

또한 라고 범주를 트리 컨트롤에서 노드를 제거 하려면이 메서드를 사용 합니다. 사용 된 [CMFCPropertySheet::AddTreeCategory](#addtreecategory) 트리 컨트롤 노드를 추가 하는 방법입니다.

##  <a name="removepage"></a>  CMFCPropertySheet::RemovePage

속성 시트에서 속성 페이지를 제거합니다.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
[in] 제거할 속성 페이지를 나타내는 속성 페이지 개체에 대 한 포인터입니다. NULL일 수 없습니다.

*nPage*<br/>
[in] 제거할 페이지의 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 지정 된 속성 페이지를 제거 하 고 연결된 된 창을 제거 합니다. 속성 페이지 개체를 *물리 페이지* 매개 변수 지정 될 때까지 제거 되지 않습니다를 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) 창이 닫힙니다.

##  <a name="seticonslist"></a>  CMFCPropertySheet::SetIconsList

Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.

```
BOOL SetIconsList(
    UINT uiImageListResID,
    int cx,
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```

### <a name="parameters"></a>매개 변수

*uiImageListResID*<br/>
[in] 리소스의 ID는 이미지 목록입니다.

*cx*<br/>
[in] 이미지 목록에 있는 아이콘의 픽셀에서 너비입니다.

*clrTransparent*<br/>
[in] 투명 이미지 색입니다. 이 색 되어 있는 이미지의 파트를 투명 하 게 됩니다. 기본값은 색 자홍, RGB(255,0,255) 합니다.

*hIcons*<br/>
[in] 기존 이미지 목록에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

첫 번째 방법은 오버 로드 구문을 true 이면이 메서드는 성공 하는 경우 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

속성 시트 스타일 Microsoft Outlook의 경우 프레임 워크는 속성 시트의 왼쪽에 있는 Outlook 창 컨트롤 이라는 탐색 단추의 목록을 표시 합니다. 이 메서드를 사용 하 여 Outlook 창 컨트롤에서 사용할 이미지 목록을 설정 합니다.

이 메서드를 지 원하는 방법에 대 한 자세한 내용은 참조 하세요. [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) 하 고 [CImageList::Add](../../mfc/reference/cimagelist-class.md#add)합니다. 속성 시트의 스타일을 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [cmfcpropertysheet:: Setlook](#setlook)합니다.

##  <a name="setlook"></a>  CMFCPropertySheet::SetLook

속성 시트의 모양을 지정합니다.

```
void SetLook(
    PropSheetLook look,
    int nNavControlWidth=100);
```

### <a name="parameters"></a>매개 변수

*look*<br/>
[in] 속성 시트의 모양을 지정 하는 열거형 값 중 하나입니다. 속성 시트에 대 한 기본 스타일은 `CMFCPropertySheet::PropSheetLook_Tabs`합니다. 자세한 내용은이 항목의 설명 섹션의 표를 참조 하세요.

*nNavControlWidth*<br/>
[in] 픽셀에서 탐색 컨트롤의 너비입니다. 기본값은 100입니다.

### <a name="remarks"></a>설명

기본값이 아닌 스타일의 속성 시트를 표시 하려면 속성 시트 창을 만들기 전에이 메서드를 호출 합니다.

다음 표에서 지정할 수 있습니다 하는 열거형 값을 *찾습니다* 매개 변수입니다.

|값|설명|
|-----------|-----------------|
|`CMFCPropertySheet::PropSheetLook_Tabs`|(기본값) 각 속성 페이지에 대 한 탭을 표시 합니다. 탭 속성 시트의 위쪽에 표시 되 고 단일 행에 들어가는 것 보다 더 많은 탭에 있는 경우 누적 됩니다.|
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Microsoft Outlook 도구 모음의 왼쪽에 있는 속성 시트의 스타일 탐색 단추의 목록을 표시합니다. 목록의 각 단추 속성 페이지에 해당합니다. 프레임 워크 목록의 표시 영역에 들어가는 것 보다 더 많은 단추 경우 스크롤 화살표를 표시 합니다.|
|`CMFCPropertySheet::PropSheetLook_Tree`|속성 시트의 왼쪽에 있는 트리 컨트롤을 표시합니다. 각 부모 또는 자식 노드 트리 컨트롤의 속성 페이지에 해당합니다. 프레임 워크는 트리 컨트롤의 표시 영역에 들어가는 것 보다 더 많은 노드가 있는 경우 스크롤 화살표를 표시 합니다.|
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Microsoft OneNote의 각 속성 페이지의 스타일에서, 탭을 표시합니다. 프레임 워크 속성 시트의 맨 위에 있는 탭이 표시 됩니다 및 단일 행에 맞는 보다 더 많은 탭에 있는 경우 스크롤 화살표입니다.|
|`CMFCPropertySheet::PropSheetLook_List`|속성 시트의 왼쪽에 있는 목록을 표시합니다. 각 목록 항목 속성 페이지에 해당합니다. 프레임 워크 목록의 표시 영역에 들어가는 것 보다 자세한 목록 항목이 있는 경우 스크롤 화살표를 표시 합니다.|

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyPage 클래스](../../mfc/reference/cmfcpropertypage-class.md)<br/>
[CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)
