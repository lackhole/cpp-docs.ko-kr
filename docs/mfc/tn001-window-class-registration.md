---
title: 'TN001: 창 클래스 등록'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: 68c851ae6a6b1b8578df90e2618f257122797aa5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306273"
---
# <a name="tn001-window-class-registration"></a>TN001: 창 클래스 등록

이 참고는 특별 한 등록 하는 MFC 루틴에 설명 합니다 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa)es Microsoft Windows에서 필요 합니다. 특정 `WNDCLASS` MFC 및 Windows에서 사용 하는 특성은 설명 합니다.

## <a name="the-problem"></a>문제

특성을 [CWnd](../mfc/reference/cwnd-class.md) 개체와 같이 `HWND` Windows 처리, 두 위치에 저장 됩니다: 창 개체 및 `WNDCLASS`합니다. 이름을 합니다 `WNDCLASS` 와 같이 일반 창 만들기 함수에 전달 되 [CWnd::Create](../mfc/reference/cwnd-class.md#create) 및 [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) 에 *lpszClassName* 매개 변수.

이 `WNDCLASS` 네 가지 의미 중 하나를 통해 등록 되어야 합니다.

- 암시적으로 제공 하는 MFC를 사용 하 여 `WNDCLASS`입니다.

- Windows 컨트롤 (또는 일부 다른 컨트롤)를 서브클래싱 암시적으로 합니다.

- 명시적으로 MFC를 호출한 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 하거나 [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass)합니다.

- Windows 루틴을 호출 하 여 명시적으로 [RegisterClass](/windows/desktop/api/winuser/nf-winuser-registerclassa)합니다.

## <a name="wndclass-fields"></a>WNDCLASS 필드

`WNDCLASS` 구조 창 클래스를 설명 하는 다양 한 필드로 구성 됩니다. 다음 표에서 필드가 표시 하 고 MFC 응용 프로그램에서 사용 되는 방법을 지정 합니다.

|필드|설명|
|-----------|-----------------|
|*lpfnWndProc*|창 프로시저 여야는 `AfxWndProc`|
|*cbClsExtra*|사용 되지 않습니다 (0 이어야 함)|
|*cbWndExtra*|사용 되지 않습니다 (0 이어야 함)|
|*hInstance*|자동으로 채워진 [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|
|*hIcon*|프레임 창에 대 한 아이콘 아래를 참조 하세요|
|*hCursor*|아래 때 마우스가 창에 대 한 커서를 참조 하세요.|
|*hbrBackground*|배경색 아래를 참조 하세요.|
|*lpszMenuName*|사용 되지 않습니다 (NULL 이어야 함)|
|*lpszClassName*|클래스 이름, 아래 참조|

## <a name="provided-wndclasses"></a>WNDCLASSes를 제공합니다.

이전 버전의 MFC (MFC 4.0의 경우) 하기 전에 몇 가지 미리 정의 된 창 클래스를 제공 합니다. 이러한 창 클래스는 더 이상 기본적으로 제공 됩니다. 응용 프로그램을 사용할지 `AfxRegisterWndClass` 적절 한 매개 변수를 사용 합니다.

지정 된 리소스 ID (예를 들어 AFX_IDI_STD_FRAME)를 사용 하 여 리소스를 제공 하는 응용 프로그램을 MFC는 해당 리소스를 사용 합니다. 그렇지 않은 경우 기본 리소스가 사용 됩니다. 아이콘에 대 한 표준 응용 프로그램 아이콘은 사용 하 고 커서에 대 한 표준 화살표 커서를 사용 됩니다.

두 아이콘 단일 문서 형식 사용 하 여 MDI 응용 프로그램을 지원 합니다: 주 응용 프로그램에 대 한 하나의 아이콘을 다른 아이콘 문서/MDIChild windows 아이콘입니다. 다른 아이콘을 사용 하 여 여러 문서 형식에 대 한 추가 등록 해야 합니다 `WNDCLASS`es 또는 사용 합니다 [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 함수입니다.

`CFrameWnd::LoadFrame` 등록을 `WNDCLASS` 첫 번째 매개 변수 및 다음 표준 특성으로 지정 하는 아이콘 ID를 사용 하 여:

- 클래스 스타일: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- icon AFX_IDI_STD_FRAME

- 화살표 커서

- COLOR_WINDOW 배경색

배경색 및 커서에 대 한 값을 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 클라이언트 영역의 이후 사용 되지 않습니다는 `CMDIFrameWnd` 에 의해 완전히 가려져 합니다 **MDICLIENT** 창. Microsoft 서브클래싱 것을 권장 하지 않습니다 합니다 **MDICLIENT** 창 표준 색 및 가능한 경우 커서 유형을 사용 합니다.

## <a name="subclassing-and-superclassing-controls"></a>하위 클래스 지정 및 슈퍼 클 래 싱 컨트롤

서브 클래스를 만들 또는 슈퍼 클래스는 Windows 제어 하는 경우 (예를 들어 [CButton](../mfc/reference/cbutton-class.md)) 클래스에 자동으로 가져옵니다. 그런 다음는 `WNDCLASS` 해당 컨트롤의 Windows 구현에서 제공 하는 특성입니다.

## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass 함수

MFC 창 클래스 등록에 대 한 도우미 함수를 제공 합니다. 지정 된 특성 (예: 창 클래스 스타일, 커서, 배경 브러시 및 아이콘) 집합, 가상 이름을 생성 되 고 결과 창 클래스를 등록 합니다. 예를 들면 다음과 같습니다.

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

이 함수는 임시 생성 된 등록 된 창 클래스 이름 문자열을 반환합니다. 이 함수에 대 한 자세한 내용은 참조 하세요. [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)합니다.

반환된 된 문자열에는 정적 문자열 버퍼에 임시 포인터입니다. 다음 호출 될 때까지 유효 `AfxRegisterWndClass`합니다. 이 문자열을 유지 하려는 경우에 저장 된 [CString](../atl-mfc-shared/using-cstring.md) 이 예제와 같이 변수:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass` throw를 [CResourceException](../mfc/reference/cresourceexception-class.md) 경우 창 클래스 등록 하지 못했습니다 (인해 잘못 된 매개 변수 또는 Windows 메모리 부족).

## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass 및 AfxRegisterClass 함수

수행 하려는 경우 아무 것도 더 복잡 한 것 `AfxRegisterWndClass` 에서는 Windows API를 호출할 수 있습니다 `RegisterClass` 또는 MFC 함수 `AfxRegisterClass`합니다. `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) 하 고 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` 함수를 *lpszClassName* 첫 번째 매개 변수로 창 클래스에 대 한 문자열 이름입니다. 등록에 사용 되는 방법에 관계 없이 등록 된 창 클래스 이름, 사용할 수 있습니다.

사용 하는 것이 반드시 `AfxRegisterClass` (또는 `AfxRegisterWndClass`)에서 Win32 DLL에 있습니다. Win32는 자동으로 등록을 취소할 DLL 종료 될 때 클래스를 등록 취소 명시적으로 해야 하므로 DLL을 등록 하는 클래스입니다. 사용 하 여 `AfxRegisterClass` 대신 `RegisterClass` 이를 자동으로 처리 됩니다. `AfxRegisterClass` 고유 클래스 목록을 DLL에서 등록 하 고는 자동으로 등록을 취소 하는 DLL 종료 될 때 유지 관리 합니다. 사용 하는 경우 `RegisterClass` DLL을 확인 해야 합니다 DLL 종료 될 때 모두 클래스 등록이 취소 됩니다 (에서 하 [DllMain](/windows/desktop/Dlls/dllmain) 함수). 이렇게 하지 않으면 발생할 수 있습니다 `RegisterClass` 다른 클라이언트 응용 프로그램 DLL을 사용 하려고 할 때 예기치 않게 실패할 수 있습니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
