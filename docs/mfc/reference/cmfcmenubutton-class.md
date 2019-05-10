---
title: CMFCMenuButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
ms.openlocfilehash: cbdf4005ee1a0249e7ed2b5f1d50621fb951f64f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388425"
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton 클래스

사용자가 선택한 메뉴에 팝업 메뉴와 보고서를 표시하는 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCMenuButton : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|`CMFCMenuButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|디스패치 되기 전에 창 메시지를 변환 하기 위해 프레임 워크에서 호출 됩니다. ( `CMFCButton::PreTranslateMessage`을 재정의합니다.)|
|[CMFCMenuButton::SizeToContent](#sizetocontent)|텍스트 및 이미지 크기에 따라 단추 크기를 변경합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|기본 시스템 팝업 메뉴에 표시 되거나 사용 여부를 지정 [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)합니다.|
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|팝업 메뉴 아래쪽 또는 오른쪽 단추에 나타날지 여부를 지정 합니다.|
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|단추를 놓으면 후 메뉴 단추 상태가 변경 되는지 여부를 지정 합니다.|
|[CMFCMenuButton::m_hMenu](#m_hmenu)|연결 된 Windows 메뉴에 대 한 핸들입니다.|
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|어떤 항목을 나타내는 식별자 사용자가 팝업 메뉴에서 선택 합니다.|

## <a name="remarks"></a>설명

`CMFCMenuButton` 에서 파생 된 클래스를 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md) 를 차례로에서 파생 된를 [CButton 클래스](../../mfc/reference/cbutton-class.md)합니다. 따라서 사용할 수 있습니다 `CMFCMenuButton` 사용 하 여 동일한 방식으로 코드에서 `CButton`합니다.

만들 때는 `CMFCMenuButton`, 연결 된 팝업 메뉴에 대 한 핸들을 전달 해야 합니다. 그런 다음 함수를 호출 `CMFCMenuButton::SizeToContent`합니다. `CMFCMenuButton::SizeToContent` 단추 크기가 있는 팝업 창이 표시 됩니다.-즉, 아래 또는 오른쪽 단추 위치를 가리키는 화살표를 포함 하는 데 충분 한지 확인 합니다.

## <a name="example"></a>예제

다음 예제에서는 단추에 연결 된 메뉴의 핸들을 설정 하 고 해당 텍스트와 이미지 크기에 따라 단추 크기를 조정 프레임 워크에 의해 표시 되는 팝업 메뉴를 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인 합니다 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxmenubutton.h

##  <a name="cmfcmenubutton"></a>  CMFCMenuButton::CMFCMenuButton

새 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) 개체입니다.

```
CMFCMenuButton();
```

##  <a name="m_bosmenu"></a>  CMFCMenuButton::m_bOSMenu

부울 멤버 변수는 팝업 메뉴를 표시 하는 프레임 워크를 표시 합니다.

```
BOOL m_bOSMenu;
```

### <a name="remarks"></a>설명

하는 경우 `m_bOSMenu` 가 TRUE 인 프레임 워크는 상속 된 호출 `TrackPopupMenu` 이 개체에 대 한 메서드. 프레임 워크에서 호출이 고, 그렇지 [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)합니다.

##  <a name="m_brightarrow"></a>  CMFCMenuButton::m_bRightArrow

팝업 메뉴의 위치를 나타내는 부울 멤버 변수입니다.

```
BOOL m_bRightArrow;
```

### <a name="remarks"></a>설명

메뉴 단추를 누를 때 응용 프로그램에 팝업 메뉴를 보여 줍니다. 프레임 워크에는 팝업 메뉴 단추를 클릭 또는 단추 오른쪽에 표시 됩니다. 단추에 팝업 메뉴 표시 되는 위치를 지정 하는 작은 화살표가 있습니다. 경우 `m_bRightArrow` 가 TRUE 인 프레임 워크 단추 오른쪽에 팝업 메뉴를 표시 합니다. 그렇지 않은 경우 단추를 클릭 하 고 팝업 메뉴를 표시합니다.

##  <a name="m_bstaypressed"></a>  CMFCMenuButton::m_bStayPressed

사용자가 팝업 메뉴에서 항목을 선택 하는 동안 메뉴 단추를 표시할지 여부를 나타내는 부울 멤버 변수를 눌렀습니다.

```
BOOL m_bStayPressed;
```

### <a name="remarks"></a>설명

경우는 `m_bStayPressed` 멤버 FALSE 이면 메뉴 단추 않습니다 될 누르지 않은 경우 사용 단추를 클릭 합니다. 이 경우 프레임 워크만 팝업 메뉴를 표시합니다.

경우는 `m_bStayPressed` 멤버가 TRUE 이면 사용자 단추를 클릭할 때 메뉴 단추를 누르면 됩니다. 사용자가 팝업 메뉴를 선택 하거나 취소 하 여 닫힌 후까지 누름 유지 합니다.

##  <a name="m_hmenu"></a>  CMFCMenuButton::m_hMenu

연결 된 메뉴에 대 한 핸들입니다.

```
HMENU m_hMenu;
```

### <a name="remarks"></a>설명

프레임 워크 메뉴 단추를 클릭할 때이 멤버 변수로 표시 된 메뉴를 표시 합니다.

##  <a name="m_nmenuresult"></a>  CMFCMenuButton::m_nMenuResult

어떤 항목을 나타내는 정수를 팝업 메뉴에서 선택 합니다.

```
int m_nMenuResult;
```

### <a name="remarks"></a>설명

사용자 메뉴를 선택 하지 않고 취소 하는 경우 나 오류가 발생 한 경우이 멤버 변수의 값이 0으로 지정 합니다.

##  <a name="pretranslatemessage"></a>  CMFCMenuButton::PreTranslateMessage

디스패치 되기 전에 창 메시지를 변환 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
[in] 가리키는 [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) 처리할 메시지를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

0이 아닌 메시지를 변환 및 발송 되어야 합니다. 메시지 변환 되지 되었습니다 및 디스패치해야 하는 경우 0입니다.

### <a name="remarks"></a>설명

##  <a name="sizetocontent"></a>  CMFCMenuButton::SizeToContent

텍스트 크기와 이미지 크기에 따라 단추 크기를 변경합니다.

```
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```

### <a name="parameters"></a>매개 변수

*bCalcOnly*<br/>
[in] 이 메서드가 단추의 크기를 조정 하는지 여부를 나타내는 부울 매개 변수입니다.

### <a name="return-value"></a>반환 값

A [CSize](../../atl-mfc-shared/reference/csize-class.md) 단추에 대 한 새 크기를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이 함수를 호출 하는 경우 및 *bCalcOnly* 가 TRUE 인 `SizeToContent` 새 단추 크기를 계산 합니다.

버튼의 새 크기 단추 텍스트, 이미지 및 화살표에 맞게 계산 됩니다. 프레임 워크는 또한 가로 지 10 픽셀 및 세로 가장자리에 대 한 5 픽셀의 미리 정의 된 여백에 추가합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md)
