---
title: CDialogBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
ms.openlocfilehash: af84c5239a9cb3cbddb1ab4f0230e5b1a3373573
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768304"
---
# <a name="cdialogbar-class"></a>CDialogBar 클래스

컨트롤 막대에 Windows 모덜리스 대화 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CDialogBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDialogBar::CDialogBar](#cdialogbar)|`CDialogBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDialogBar::Create](#create)|Windows 대화 상자 모음을 만들고에 연결 된 `CDialogBar` 개체입니다.|

## <a name="remarks"></a>설명

대화 상자 모음와 사용자 간의 탭 수는 표준 Windows 컨트롤을 포함 하는 대화 상자가 유사 합니다. 다른 유사성은 대화 상자 막대를 나타내는 대화 상자 템플릿을 만들어야 합니다.

만들고 사용 하 여 만들고 대화 상자 막대를 사용 하 여 비슷합니다는 `CFormView` 개체입니다. 먼저 사용 하 여는 [대화 상자 편집기](../../windows/dialog-editor.md) WS_CHILD 스타일으로 대화 상자 템플릿 및 다른 스타일이 없습니다 정의할 수 있습니다. 템플릿 스타일 WS_VISIBLE 없어야 합니다. 응용 프로그램 코드에서 생성 하는 생성자를 호출 합니다 `CDialogBar` 개체를 만든 다음 호출 `Create` 대화 상자 모음 창을 만들에 연결 하는 `CDialogBar` 개체입니다.

에 대 한 자세한 `CDialogBar`, 문서를 참조 하세요 [대화 상자 모음](../../mfc/dialog-bars.md) 하 고 [Technical Note 31](../../mfc/tn031-control-bars.md), 컨트롤 막대입니다.

> [!NOTE]
>  현재 릴리스에서 `CDialogBar` 개체는 Windows Forms 컨트롤을 호스팅할 수 없습니다. 시각적 개체에 Windows Forms 컨트롤에 대 한 자세한 내용은 C++를 참조 하세요 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CDialogBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar

`CDialogBar` 개체를 생성합니다.

```
CDialogBar();
```

##  <a name="create"></a>  CDialogBar::Create

지정 된 대화 상자 리소스 템플릿을 로드 `lpszTemplateName` 또는 `nIDTemplate`, 대화 상자 모음 창을 만듭니다. 해당 스타일을 설정 및 연결 된 `CDialogBar` 개체입니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

virtual BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
부모에 대 한 포인터 `CWnd` 개체입니다.

*lpszTemplateName*<br/>
이름에 대 한 포인터를 `CDialogBar` 개체의 대화 상자 리소스 템플릿.

*nStyle*<br/>
도구 모음 스타일입니다. 지원 되는 추가 도구 모음 스타일은

- CBRS_TOP 컨트롤 막대 프레임 창의 위쪽에 있는 경우

- CBRS_BOTTOM 컨트롤 막대 프레임 창의 맨 아래에 있는 경우

- CBRS_NOALIGN 컨트롤 막대 부모 크기를 조정할 때 관계를 변경할 수 없습니다.

- CBRS_TOOLTIPS 컨트롤 막대에는 도구 설명을 표시합니다.

- CBRS_SIZE_DYNAMIC 컨트롤 막대는 동적입니다.

- CBRS_SIZE_FIXED 컨트롤 막대 고정 되어 있습니다.

- CBRS_FLOATING 컨트롤 막대는 부동입니다.

- CBRS_FLYBY 상태 표시줄 단추에 대 한 정보를 표시합니다.

- CBRS_HIDE_INPLACE 컨트롤 막대를 사용자에 게 표시 되지 않습니다.

*nID*<br/>
컨트롤의 ID는 대화 상자 막대입니다.

*nIDTemplate*<br/>
리소스 ID는 `CDialogBar` 개체의 대화 상자 템플릿.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

대화 상자 막대의 너비를 사용 하면 프레임 창의, 높이 사용 하 여 지정 된 리소스의는 CBRS_TOP 또는 CBRS_BOTTOM 맞춤 스타일을 지정한 경우 *nIDTemplate*합니다. 대화 상자 막대의 높이 사용 하면 프레임 창의, 지정 하는 리소스의 너비가 CBRS_LEFT 또는 CBRS_RIGHT 맞춤 스타일을 지정한 경우 *nIDTemplate*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFormView 클래스](../../mfc/reference/cformview-class.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)
