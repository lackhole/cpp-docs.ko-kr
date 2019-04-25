---
title: CDialogEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
ms.openlocfilehash: f92058d1aa0dabccf6623d20a248fed8eb99ab26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168052"
---
# <a name="cdialogex-class"></a>CDialogEx 클래스

`CDialogEx` 클래스는 대화 상자의 배경 색과 배경 이미지를 지정합니다.

## <a name="syntax"></a>구문

```
class CDialogEx : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|`CDialogEx` 개체를 생성합니다.|
|`CDialogEx::~CDialogEx`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|대화 상자의 배경 색을 설정합니다.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|대화 상자의 배경 이미지를 설정합니다.|

## <a name="remarks"></a>설명

`CDialogEx` 클래스를 사용하려면 `CDialogEx` 클래스 대신 `CDialog` 클래스에서 대화 상자 클래스를 파생합니다.

대화 상자 이미지는 리소스 파일에 저장됩니다. 프레임워크는 리소스 파일에서 로드되는 모든 이미지를 자동으로 삭제합니다. 현재 배경 이미지를 프로그래밍 방식으로 삭제 하려면 다음을 호출 합니다 [CDialogEx::SetBackgroundImage](#setbackgroundimage) 메서드 또는 구현은 `OnDestroy` 이벤트 처리기입니다. 호출 하는 경우는 [CDialogEx::SetBackgroundImage](#setbackgroundimage) 메서드를는 `HBITMAP` 매개 변수를 이미지 핸들로 합니다. `CDialogEx` 개체가 이미지의 소유권을 갖게 되며 `m_bAutoDestroyBmp` 플래그가 `TRUE`이면 삭제합니다.

A `CDialogEx` 개체의 부모가 될 수는 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 개체입니다. [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 호출 개체를 `CDialogEx::SetActiveMenu` 메서드 때 합니다 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 열립니다 개체. 나중에 `CDialogEx` 될 때까지 모든 메뉴 이벤트를 처리 하는 개체를 [CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md) 개체가 닫혀 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdialogex.h

##  <a name="cdialogex"></a>  CDialogEx::CDialogEx

`CDialogEx` 개체를 생성합니다.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
[in] 대화 상자 템플릿의 리소스 ID입니다.

*lpszTemplateName*<br/>
[in] 대화 상자 템플릿의 리소스 이름입니다.

*pParent*<br/>
[in] 부모 창에 대 한 포인터입니다. 기본값은 NULL입니다.

*pParentWnd*<br/>
[in] 부모 창에 대 한 포인터입니다. 기본값은 NULL입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="setbackgroundcolor"></a>  CDialogEx::SetBackgroundColor

대화 상자의 배경 색을 설정합니다.

```
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>매개 변수

*color*<br/>
[in] RGB 색 값입니다.

*bRepaint*<br/>
[in] 화면을 즉시 업데이트 하려면 TRUE 그렇지 않으면 FALSE입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

##  <a name="setbackgroundimage"></a>  CDialogEx::SetBackgroundImage

대화 상자의 배경 이미지를 설정합니다.

```
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
[in] 배경 이미지에 대 한 핸들입니다.

*uiBmpResId*<br/>
[in] 배경 이미지의 리소스 ID입니다.

*location*<br/>
[in] 중 하나는 `CDialogEx::BackgroundLocation` 이미지의 위치를 지정 하는 값입니다. 유효한 값 BACKGR_TILE "," BACKGR_TOPLEFT "," BACKGR_TOPRIGHT "," BACKGR_BOTTOMLEFT, "및" BACKGR_BOTTOMRIGHT 같습니다. 기본값은 BACKGR_TILE 합니다.

*bAutoDestroy*<br/>
[in] 배경 이미지를 자동으로 삭제. 그렇지 않으면 FALSE입니다.

*bRepaint*<br/>
[in] 대화 상자를 즉시 다시 그리도록 하려면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

두 번째 방법은 오버 로드 구문을 TRUE 메서드가 성공할 경우 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

대화 상자의 클라이언트 영역에 맞게 지정 하는 이미지를 채우도록 확장 되지 않습니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPopupMenu 클래스](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[CContextMenuManager 클래스](../../mfc/reference/ccontextmenumanager-class.md)
