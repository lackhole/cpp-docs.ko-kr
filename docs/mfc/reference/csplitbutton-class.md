---
title: CSplitButton 클래스
ms.date: 11/19/2018
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
ms.openlocfilehash: 70bba379f33be2d4df05f6b96eac14bf248cf356
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346269"
---
# <a name="csplitbutton-class"></a>CSplitButton 클래스

`CSplitButton` 클래스는 분할 단추 컨트롤을 나타냅니다. 분할 단추 컨트롤은 사용자가 단추의 주요 부분을 클릭할 때 기본 동작을 수행하고 사용자가 단추의 드롭다운 화살표를 클릭하면 드롭다운 메뉴를 표시합니다.

## <a name="syntax"></a>구문

```
class CSplitButton : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSplitButton::CSplitButton](#csplitbutton)|`CSplitButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSplitButton::Create](#create)|지정 된 스타일을 사용 하 여 분할 단추 컨트롤을 만들고 현재 연결 `CSplitButton` 개체입니다.|
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 드롭다운 메뉴를 설정 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CSplitButton::OnDropDown](#ondropdown)|현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 시스템에서 보내는 BCN_DROPDOWN 알림을 처리 합니다.|

## <a name="remarks"></a>설명

합니다 `CSplitButton` 에서 파생 된 클래스를 [CButton](../../mfc/reference/cbutton-class.md) 클래스입니다. 분할 단추 컨트롤은 BS_SPLITBUTTON 스타일 단추 컨트롤입니다. 드롭다운 화살표를 클릭할 때 사용자 지정 메뉴를 표시 합니다. 자세한 내용은 BS_DEFSPLITBUTTON 및 BS_SPLITBUTTON 스타일을 참조 하세요 [단추 스타일](/windows/desktop/Controls/button-styles)합니다.

다음 그림에서는 pager 컨트롤 및 (1) 분할 단추 컨트롤을 포함 하는 대화 상자를 보여 줍니다. (2)에서 드롭다운 화살표를 클릭 했는지 이미 및 (3) 하위 메뉴가 표시 됩니다.

![Splitbutton 및 pager 컨트롤이 있는 대화 상자. ](../../mfc/reference/media/splitbutton_pager.png "Splitbutton 및 pager 컨트롤이 있는 대화 상자.")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

이 클래스는 Windows Vista 이상 사용할 수 있습니다.

이 클래스에 대 한 추가 요구 사항에 설명 되어 [빌드 요구 사항에 대 한 Windows Vista 공용 컨트롤](../../mfc/build-requirements-for-windows-vista-common-controls.md)합니다.

##  <a name="create"></a>  CSplitButton::Create

지정 된 스타일을 사용 하 여 분할 단추 컨트롤을 만들고 현재 연결 `CSplitButton` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwStyle*|[in] 컨트롤에 적용 될 스타일의 비트 조합 (OR)입니다. 자세한 내용은 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)합니다.|
|*rect*|[in] 에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 컨트롤의 크기와 위치를 포함 하는 구조입니다.|
|*pParentWnd*|[in] 에 대 한 null이 아닌 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다.|
|*nID*|[in] 컨트롤의 ID입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton

`CSplitButton` 개체를 생성합니다. 생성자의 매개 변수는 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 하위 메뉴를 지정 합니다.

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*nMenuId*|[in] 메뉴 모음의 리소스 ID입니다.|
|*nSubMenuId*|[in] 하위 리소스 ID입니다.|
|*pMenu*|[in] 에 대 한 포인터를 [CMenu](../../mfc/reference/cmenu-class.md) 하위 메뉴를 지정 하는 개체입니다. `CSplitButton` 삭제 개체를 `CMenu` 개체와 연결 된 해당 HMENU 때는 `CSplitButton` 범위를 벗어나면 합니다.|

### <a name="remarks"></a>설명

사용 된 [CSplitButton::Create](#create) 분할 단추 컨트롤을 만들고 연결 하는 메서드를 `CSplitButton` 개체입니다.

##  <a name="ondropdown"></a>  CSplitButton::OnDropDown

현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 시스템에서 보내는 BCN_DROPDOWN 알림을 처리 합니다.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pNMHDR*|[in] 에 대 한 포인터를 [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) 구조에 대 한 정보를 포함 하는 [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown) 알림.|
|*pResult*|[out] (사용 되지 않습니다; 아무 값도 반환)입니다. 값을 반환 합니다 [BCN_DROPDOWN](/windows/desktop/Controls/bcn-dropdown) 알림.|

### <a name="remarks"></a>설명

시스템 보냅니다 BCN_DROPDOWN 알림 사용자가 분할 단추 컨트롤에 있는 드롭다운 화살표를 클릭 하는 메시지를 `OnDropDown` 메서드 핸들입니다. 그러나는 `CSplitButton` 개체 BCN_DROPDOWN 알림 분할 단추 컨트롤을 포함 하는 컨트롤을 전달 하지 않습니다. 따라서 포함 하는 컨트롤 알림에 대 한 응답으로 사용자 지정 작업을 지원할 수 없습니다.

포함 하는 컨트롤을 지 원하는 사용자 지정 작업을 구현 하려면 사용을 [CButton](../../mfc/reference/cbutton-class.md) 대신 BS_SPLITBUTTON 스타일을 사용 하 여 개체를 `CSplitButton` 개체입니다. 그런 다음에 BCN_DROPDOWN 알림 처리기를 구현 합니다 `CButton` 개체입니다. 자세한 내용은 [단추 스타일](../../mfc/reference/styles-used-by-mfc.md#button-styles)합니다.

분할 단추 컨트롤 자체에서 지 원하는 사용자 지정 작업을 구현 하려면 사용 [리플렉션 메시지](../../mfc/tn062-message-reflection-for-windows-controls.md)합니다. 고유한 클래스를 파생 합니다 `CSplitButton` 클래스 하 고 예를 들어 CMySplitButton 이름을 합니다. 그런 다음 다음과 같은 메시지 맵을 BCN_DROPDOWN 알림 메시지를 처리 하도록 응용 프로그램 추가.

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu

현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시 되는 드롭다운 메뉴를 설정 합니다.

```
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*nMenuId*|[in] 메뉴 모음의 리소스 ID입니다.|
|*nSubMenuId*|[in] 하위 리소스 ID입니다.|
|*pMenu*|[in] 에 대 한 포인터를 [CMenu](../../mfc/reference/cmenu-class.md) 하위 메뉴를 지정 하는 개체입니다. `CSplitButton` 삭제 개체를 `CMenu` 개체와 연결 된 해당 HMENU 때는 `CSplitButton` 범위를 벗어나면 합니다.|

### <a name="remarks"></a>설명

합니다 *nMenuId* 매개 변수는 메뉴 모음, 메뉴 모음 항목의 가로 목록인를 식별 합니다. 합니다 *nSubMenuId* 매개 변수는 각 메뉴 모음 항목을 사용 하 여 연결 된 메뉴 항목의 드롭다운 목록에는 하위 메뉴를 식별 하는 0부터 시작 인덱스 번호입니다. 예를 들어 일반적인 응용 프로그램에 포함 하는 메뉴가 메뉴 모음 항목을 "File", "편집" 및 "Help"입니다. "파일" 메뉴 모음 항목에 메뉴 항목이 들어 있는 하위 메뉴가 "열," "닫기" 및 "Exit"입니다. 분할 단추 컨트롤의 드롭다운 화살표를 클릭 하면 지정 된 하위 메뉴, 메뉴 모음 하지 컨트롤에 표시 됩니다.

다음 그림에서는 pager 컨트롤 및 (1) 분할 단추 컨트롤을 포함 하는 대화 상자를 보여 줍니다. (2)에서 드롭다운 화살표를 클릭 했는지 이미 및 (3) 하위 메뉴가 표시 됩니다.

![Splitbutton 및 pager 컨트롤이 있는 대화 상자. ](../../mfc/reference/media/splitbutton_pager.png "Splitbutton 및 pager 컨트롤이 있는 대화 상자.")

### <a name="example"></a>예제

다음 코드 예제에서 첫 번째 문과 합니다 [CSplitButton::SetDropDownMenu](#setdropdownmenu) 메서드. 메뉴 모음 ID IDR_MENU1 이름이 자동으로 지정 하는 편집기에서 메뉴는 Visual Studio 리소스를 사용 하 여 만든. 합니다 *nSubMenuId* 매개 변수인 0만 하위 메뉴의 메뉴 모음을 가리킵니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>참고자료

[CSplitButton 클래스](../../mfc/reference/csplitbutton-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)
