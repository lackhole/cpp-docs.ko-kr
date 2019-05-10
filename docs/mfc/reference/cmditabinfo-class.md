---
title: CMDITabInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
helpviewer_keywords:
- CMDITabInfo [MFC], Serialize
- CMDITabInfo [MFC], m_bAutoColor
- CMDITabInfo [MFC], m_bDocumentMenu
- CMDITabInfo [MFC], m_bEnableTabSwap
- CMDITabInfo [MFC], m_bFlatFrame
- CMDITabInfo [MFC], m_bTabCloseButton
- CMDITabInfo [MFC], m_bTabCustomTooltips
- CMDITabInfo [MFC], m_bTabIcons
- CMDITabInfo [MFC], m_nTabBorderSize
- CMDITabInfo [MFC], m_style
- CMDITabInfo [MFC], m_tabLocation
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
ms.openlocfilehash: a42128d097c9d63d82243090e2e215a250ff432b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341687"
---
# <a name="cmditabinfo-class"></a>CMDITabInfo 클래스

합니다 `CMDITabInfo` 클래스는 매개 변수를 전달 하는 데 사용 됩니다 [cmdiframewndex:: Enablemditabbedgroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups) 메서드. MDI 탭 그룹의 동작을 제어하려면 이 클래스의 멤버를 설정합니다.

## <a name="syntax"></a>구문

```
class CMDITabInfo
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMDITabInfo::CMDITabInfo`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMDITabInfo::Serialize](#serialize)|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMDITabInfo::m_bActiveTabCloseButton;](#m_bactivetabclosebutton_)|지정 여부는 **닫기** 단추가 활성 탭의 레이블에 표시 됩니다.|
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|MDI 탭 색을 지정 합니다.|
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|탭 그룹에 열린된 문서의 목록을 표시 하거나 스크롤 단추를 표시 하는 팝업 메뉴를 표시 하는지 여부를 지정 합니다.|
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|사용자 탭의 위치를 끌어서 교체할 수 있는지 여부를 지정 합니다.|
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|탭 플랫 프레임을 여부를 지정 합니다.|
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|각 탭 레이블에 표시 되는지 여부를 지정 된 **닫기** 단추입니다.|
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|사용자 지정 도구 설명이 사용 되는지 여부를 지정 합니다.|
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|MDI 탭에 아이콘을 표시할지 여부를 지정 합니다.|
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|각 탭 창의 테두리 크기를 지정합니다.|
|[CMDITabInfo::m_style](#m_style)|탭 레이블 스타일을 지정합니다.|
|[CMDITabInfo::m_tabLocation](#m_tablocation)|탭 레이블을 위쪽 또는 페이지의 맨 아래에 있는지 여부를 지정 합니다.|

## <a name="remarks"></a>설명

이 클래스는 프레임 워크에서 만든 MDI 탭 그룹의 매개 변수를 지정 합니다.

## <a name="example"></a>예제

다음 예제에서는 다양 한 멤버 변수 값을 설정 하는 방법에 설명 `CMDITabInfo` 클래스입니다.

[!code-cpp[NVC_MFC_MDITab#1](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxmdiclientareawnd.h

##  <a name="m_bactivetabclosebutton_"></a>  CMDITabInfo::m_bActiveTabCloseButton;

지정 여부는 **닫기** 단추가 활성 탭의 레이블에 표시 됩니다.

```
BOOL m_bActiveTabCloseButton;
```

### <a name="remarks"></a>설명

True 이면 활성 탭의 레이블에 표시 됩니다는 **닫기** 단추입니다. 합니다 **닫기** 단추 탭 영역의 오른쪽 위 모서리에서 제거 됩니다. 그렇지 않으면 활성 탭의 레이블에 표시 되지 것입니다는 **닫기** 단추입니다. 합니다 **닫기** 단추 탭 영역의 오른쪽 위 모서리에 표시 됩니다.

##  <a name="m_bautocolor"></a>  CMDITabInfo::m_bAutoColor

각 MDI 탭 색 자체에 있는지 여부를 지정 합니다.

```
BOOL m_bAutoColor;
```

### <a name="remarks"></a>설명

True 이면 각 탭은 고유한 색을 해야 합니다. 색 집합 MFC 라이브러리에 의해 관리 됩니다. 그렇지 않으면 탭 흰색으로 표시 됩니다. 기본값은 FALSE입니다.

##  <a name="m_bdocumentmenu"></a>  CMDITabInfo::m_bDocumentMenu

각 탭 탭 영역의 오른쪽 가장자리에 열린 문서의 목록을 보여 주는 팝업 메뉴를 표시 하는지 여부를 지정 합니다.

```
BOOL m_bDocumentMenu;
```

### <a name="remarks"></a>설명

True 이면 각 탭 창 탭 영역의 오른쪽 가장자리에 열린 문서의 목록을 보여 주는 팝업 메뉴를 표시 하는 그렇지 않으면 탭 창 탭 영역의 오른쪽 가장자리에 스크롤 단추를 표시합니다. 기본값은 FALSE입니다.

##  <a name="m_benabletabswap"></a>  CMDITabInfo::m_bEnableTabSwap

사용자 탭의 위치를 끌어서 교체할 수 있는지 여부를 지정 합니다.

```
BOOL m_bEnableTabSwap;
```

### <a name="remarks"></a>설명

TRUE 인 경우 사용자는 탭을 끌어 탭 위치를 변경할 수 있습니다. 그렇지 않으면 사용자 탭 위치를 변경할 수 없습니다. 기본값은 TRUE입니다.

##  <a name="m_bflatframe"></a>  CMDITabInfo::m_bFlatFrame

각 탭 창 플랫 프레임에 있는지 여부를 지정 합니다.

```
BOOL m_bFlatFrame;
```

##  <a name="m_btabclosebutton"></a>  CMDITabInfo::m_bTabCloseButton

각 탭 창에 표시 되는지 여부를 지정 된 **닫기** 단추입니다.

```
BOOL m_bTabCloseButton;
```

### <a name="remarks"></a>설명

TRUE 인 경우 각 탭 창에 표시 합니다 **닫기** 탭의 오른쪽 가장자리에는 단추입니다. 그렇지 않으면 합니다 **닫기** 단추가 표시 되지 않습니다. 기본값은 TRUE입니다.

##  <a name="m_btabcustomtooltips"></a>  CMDITabInfo::m_bTabCustomTooltips

탭에 도구 설명을 표시할지 여부를 지정 합니다.

```
BOOL m_bTabCustomTooltips;
```

### <a name="remarks"></a>설명

True 이면 응용 프로그램 주 프레임에는 AFX_WM_ON_GET_TAB_TOOLTIP 메시지를 보냅니다. ON_REGISTERED_MESSAGE 매크로 사용 하 여이 메시지를 처리할 수 있습니다.

##  <a name="m_btabicons"></a>  CMDITabInfo::m_bTabIcons

MDI 탭에 아이콘을 표시할지 여부를 지정 합니다.

```
BOOL m_bTabIcons;
```

### <a name="remarks"></a>설명

TRUE 이면 각 MDI 탭에 아이콘이 표시 됩니다. 그렇지 않으면 아이콘 탭에 표시 되지 않습니다. 기본값은 FALSE입니다.

##  <a name="m_ntabbordersize"></a>  CMDITabInfo::m_nTabBorderSize

각 탭 창의 픽셀 테두리 크기를 지정합니다.

```
int m_nTabBorderSize;
```

### <a name="remarks"></a>설명

[CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize) 기본값을 반환 합니다.

##  <a name="m_style"></a>  CMDITabInfo::m_style

탭 레이블 스타일을 지정합니다.

```
CMFCTabCtrl::Style m_style
```

### <a name="remarks"></a>설명

탭 레이블에 대 한 다음과 같은 스타일 중 하나를 지정 합니다.

|||
|-|-|
|STYLE_3D|3D 스타일입니다.  |
|STYLE_3D_ONENOTE|Microsoft OneNote 스타일입니다.  |
|STYLE_3D_VS2005|Microsoft Visual Studio 2005 style.  |
|STYLE_3D_SCROLLED|사각형 탭 레이블로 3D 스타일입니다.  |
|STYLE_FLAT_SHARED_HORZ_SCROLL|공유 가로 스크롤 막대를 사용 하 여 플랫 스타일입니다.  |
|STYLE_3D_ROUNDED_SCROLL|Round 탭 레이블로 3D 스타일입니다.  |

##  <a name="m_tablocation"></a>  CMDITabInfo::m_tabLocation

탭 레이블을 위쪽 또는 페이지의 맨 아래에 있는지 여부를 지정 합니다.

```
CMFCTabCtrl::Location m_tabLocation;
```

### <a name="remarks"></a>설명

다음 위치 플래그의 탭 하나에 적용 됩니다.

- LOCATION_BOTTOM: 탭 레이블을 페이지의 맨 아래에 나와 있습니다.

- LOCATION_TOP: 탭 레이블을 페이지의 위쪽에 나와 있습니다.

##  <a name="serialize"></a>  CMDITabInfo::Serialize

읽거나 보관 또는 보관에서이 개체를 씁니다.

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
[in] A [CArchive 클래스](../../mfc/reference/carchive-class.md) serialize 할 개체입니다.

## <a name="see-also"></a>참고자료

[CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)<br/>
[MDI 탭 그룹](../../mfc/mdi-tabbed-groups.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
