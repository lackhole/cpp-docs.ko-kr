---
title: CMFCWindowsManagerDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 5089decc7a118cd867aa14df51f5d7e269221108
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767407"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog 클래스

`CMFCWindowsManagerDialog` 개체를 사용 하면 사용자가 MDI 응용 프로그램에서 MDI 자식 창을 관리할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|`CMFCWindowsManagerDialog` 개체를 생성합니다.|

## <a name="remarks"></a>설명

`CMFCWindowsManagerDialog` 응용 프로그램에서 현재 열려 있는 MDI 자식 창의 목록을 포함 합니다. 사용자가 대화 상자를 사용 하 여 MDI 자식 창의 상태를 수동으로 제어할 수 있습니다.

`CMFCWindowsManagerDialog` 내에 포함 된 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)합니다. `CMFCWindowsManagerDialog` 수동으로 만들어야 하는 클래스가 아닙니다. 함수를 호출 하는 대신 [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)에서 생성 및 표시를 `CMFCWindowsManagerDialog` 개체입니다.

## <a name="example"></a>예제

다음 예제에서는 생성 하는 방법에 설명 된 `CMFCWindowsManagerDialog` 개체를 호출 하 여 `CMDIFrameWndEx::ShowWindowsDialog`입니다. 이 코드 조각은의 일부인 합니다 [Visual Studio 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxWindowsManagerDialog.h

##  <a name="cmfcwindowsmanagerdialog"></a>  CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

생성 된 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 개체입니다.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>매개 변수

*pMDIFrame*<br/>
[in] 부모 또는 소유자 창에 대 한 포인터입니다.

*bHelpButton*<br/>
[in] 프레임 워크를 표시 하는지 여부를 지정 하는 부울 매개 변수를 **도움말** 단추입니다.

### <a name="remarks"></a>설명

비주얼 관리자에 대 한 자세한 내용은 참조 하세요. [시각화 관리자](../../mfc/visualization-manager.md)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)
