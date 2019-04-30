---
title: CMiniFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: 70f090e2d9830ccfdd98640b54ff07440064d542
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337819"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd 클래스

일반적으로 부동 도구 모음에 있는 절반 높이의 프레임 창을 나타냅니다.

## <a name="syntax"></a>구문

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|`CMiniFrameWnd` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMiniFrameWnd::Create](#create)|만듭니다는 `CMiniFrameWnd` 생성 후 개체입니다.|
|[CMiniFrameWnd::CreateEx](#createex)|만듭니다는 `CMiniFrameWnd` 생성 후 개체 (사용 하 여 추가 옵션).|

## <a name="remarks"></a>설명

이러한 미니 프레임 창을 최소화/최대화 단추를 갖지 않습니다 또는 메뉴 하 수만 번을 클릭 하 고 해제 하려면 시스템 메뉴에서 한다는 점을 제외 하면 일반 프레임 창 처럼 동작 합니다.

사용 하는 `CMiniFrameWnd` 개체, 먼저 개체를 정의 합니다. 그런 다음 호출을 [만들기](#create) 미니 프레임 창을 표시 하려면 멤버 함수입니다.

사용 하는 방법에 대 한 자세한 내용은 `CMiniFrameWnd` 문서를 참조 하는 개체를 [도킹 및 부동 도구 모음](../../mfc/docking-and-floating-toolbars.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd

생성 된 `CMiniFrameWnd` 개체 하지만 창을 만들지는 않습니다.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>설명

창, 호출 [CMiniFrameWnd::Create](#create)합니다.

##  <a name="create"></a>  CMiniFrameWnd::Create

Windows 미니 프레임 창을 만들고에 연결 된 `CMiniFrameWnd` 개체입니다.

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>매개 변수

*lpClassName*<br/>
Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다. 전역으로 등록 된 모든 이름 클래스 이름일 수 있습니다 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 함수입니다. NULL 인 경우 창 클래스를 프레임 워크에 의해 등록 됩니다. MFC는 다음과 같은 스타일 및 특성이 기본 클래스를 제공합니다.

- 집합 스타일 비트가 CS_DBLCLKS를 보내고 마우스를 두 번 클릭할 때 창 프로시저에 메시지를 두 번 클릭 합니다.

- 창 크기가 변경 될 때 다시 그려져 야 클라이언트 영역의 내용을 직접 CS_HREDRAW 및 CS_VREDRAW, 스타일 비트를 설정 합니다.

- Windows 표준 IDC_ARROW에 클래스 커서를 설정 합니다.

- 창 배경을 지우지 됩니다 있도록 클래스 배경 브러시를 NULL로 설정 합니다.

- 표준, 손 흔드는 플래그 Windows 로고 아이콘 클래스 아이콘을 설정 합니다.

- Windows에 표시 된 대로 창의 기본 크기 및 위치를 설정 합니다.

*lpWindowName*<br/>
창 이름이 포함 된 null로 끝나는 문자열을 가리킵니다.

*dwStyle*<br/>
창 스타일 특성을 지정합니다. 표준 창 스타일 및 하나 이상의 다음 특수 스타일을 포함할 수 있습니다.

- MFS_MOVEFRAME 미니 프레임 창을 캡션 뿐 아니라 창의 가장자리를 클릭 하 여 이동할 수 있습니다.

- 미니 프레임 창의 크기 조정 MFS_4THICKFRAME 사용 하지 않도록 설정 합니다.

- MFS_SYNCACTIVE 동기화 미니 프레임 창의 부모 창의 정품 인증을 활성화 합니다.

- 미니 프레임 창의 클라이언트 영역의 내용으로 작은 크기를 조정할 수 허용 MFS_THICKFRAME 수 있습니다.

- 시스템 메뉴 및 컨트롤 메뉴에 액세스할 MFS_BLOCKSYSMENU 사용 하지 않도록 설정 (제목 표시줄) 캡션 부분과 관련 하 여 변환 합니다.

참조 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 가능한 창 스타일 값에 대 한 합니다. 미니 프레임 창에 사용 되는 일반적인 조합이 WS_POPUP입니다&#124;WS_CAPTION&#124;WS_SYSMENU 합니다.

*rect*<br/>
`RECT` 구조 창의 원하는 크기를 지정 합니다.

*pParentWnd*<br/>
부모 창을 가리킵니다. 최상위 창에 대해 NULL을 사용 합니다.

*nID*<br/>
미니 프레임 창의 자식 창으로 만들어진 경우이 자식 컨트롤의 식별자 그렇지 않으면 0입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Create` 창의 클래스 이름 및 창 이름을 초기화 하 고 해당 스타일 및 부모에 대 한 기본값을 등록 합니다.

##  <a name="createex"></a>  CMiniFrameWnd::CreateEx

`CMiniFrameWnd` 개체를 만듭니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
확장된 스타일을 지정 합니다 `CMiniFrameWnd` 만들어지는 합니다. 적용 된 [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) 창에 있습니다.

*lpClassName*<br/>
Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리키는 (한 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) 구조). 전역으로 등록 된 모든 이름 클래스 이름일 수 있습니다 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 함수 또는 미리 정의 된 컨트롤 클래스 이름입니다. NULL이 아니어야 합니다.

*lpWindowName*<br/>
창 이름이 포함 된 null로 끝나는 문자열을 가리킵니다.

*dwStyle*<br/>
창 스타일 특성을 지정합니다. 참조 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 하 고 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 가능한 값에 대 한 합니다.

*rect*<br/>
크기와의 클라이언트 좌표에서 창의 위치 *pParentWnd*합니다.

*pParentWnd*<br/>
부모 창 개체를 가리킵니다.

*nID*<br/>
자식 창의 식별자입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`CreateEx` WNDCLASS, 창 스타일 및 (선택 사항) 초기 위치 및 창 크기 매개 변수를 지정 합니다. `CreateEx` 또한 창의 부모 (있는 경우) 및 ID를 지정

때 `CreateEx` 보냅니다 Windows를 실행 합니다 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)를 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) 창에 메시지입니다.

기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CMiniFrameWnd`메시지 맵에서 새로운 클래스를 추가 하 고 위의 메시지에 대 한 멤버 함수를 제공 합니다. 재정의 `OnCreate`, 예를 들어, 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.

추가로 재정의 `On` *메시지* 메시지 파생된 클래스에 기능을 추가 하는 처리기.

WS_VISIBLE 스타일을 지정 하는 경우 Windows는 활성화 하 고 창을 표시 하는 데 필요한 모든 메시지 창에 게 보냅니다. 창 스타일 제목 표시줄을 지정 하는 경우 창 제목은 가리키는 합니다 *lpszWindowName* 매개 변수는 제목 표시줄에 표시 됩니다.

합니다 *dwStyle* 매개 변수 조합 될 수 있습니다 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.

이전 스타일 팔레트 도구 상자 창은 더 이상 지원 합니다. MFC 응용 프로그램을 이전 버전의 Windows 실행 하는 경우 "X" 닫기 단추를 하지 않은, 하는 이전 스타일 지원 된 시각적 개체에 더 이상 지원 되지 않지만 C++.NET입니다. 새 WS_EX_TOOLWINDOW 스타일만 이제 지원 됩니다. 이 스타일의 설명을 참조 하세요 [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)합니다.

## <a name="see-also"></a>참고자료

[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)
