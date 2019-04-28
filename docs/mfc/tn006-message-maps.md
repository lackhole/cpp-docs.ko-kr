---
title: 'TN006: 메시지 맵'
ms.date: 06/25/2018
f1_keywords:
- vc.messages.maps
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
ms.openlocfilehash: 3536cb215da04fb7114853d3fa5d764585cbb58e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306150"
---
# <a name="tn006-message-maps"></a>TN006: 메시지 맵

이 이는 MFC 메시지 맵에 기능을 설명합니다.

## <a name="the-problem"></a>문제

Microsoft Windows의 메시징 기능을 사용 하는 창 클래스의 가상 함수를 구현 합니다. 관련 된 메시지의 수가 많아서 각 Windows 메시지에 대 한 별도 가상 함수를 제공 하는 크지 vtable를 생성 합니다.

Windows 시스템에 정의 된 메시지 수가 시간이 지남에 따라 변경 하 고 응용 프로그램에서 자체 Windows 메시지를 정의할 수 있으므로 메시지 맵 때문에 인터페이스 변경 내용이 기존 코드를 수정 하지 못하도록 하는 간접 참조 수준을 제공 합니다.

## <a name="overview"></a>개요

MFC는 창에 전송 된 메시지를 처리 하도록 기존 Windows 기반 프로그램에 사용 된 switch 문 대신을 제공 합니다. 메시지 창에 의해 수신 되 면 적절 한 메서드는 자동으로 되도록 메시지에서 매핑된 메서드를 정의할 수 있습니다. 이 메시지 맵 기능 가상 함수를 유사 하 게 설계 되어 있지만 추가 이점이 불가능 C++ 가상 함수입니다.

## <a name="defining-a-message-map"></a>메시지 맵 정의

합니다 [DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) 매크로 클래스에 대 한 세 가지 멤버를 선언 합니다.

- AFX_MSGMAP_ENTRY 항목의 private 배열을 호출 *_messageEntries*합니다.

- 보호 된 AFX_MSGMAP 구조 호출 *messageMap* 가리키는 합니다 *_messageEntries* 배열입니다.

- 보호 된 가상 함수 호출 `GetMessageMap` 의 주소를 반환 하는 *messageMap*합니다.

이 매크로 메시지 맵을 사용 하 여 클래스의 선언에 배치 해야 합니다. 규칙으로 클래스 선언의 끝입니다. 예를 들어:

```cpp
class CMyWnd : public CMyParentWndClass
{
    // my stuff...

protected:
    //{{AFX_MSG(CMyWnd)
    afx_msg void OnPaint();
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};
```

새 클래스를 만들 때 AppWizard 및 classwizard 함께 사용 하 여 생성 된 형식입니다. / / {{및 / /}} 대괄호 클래스 마법사에 대 한 필요 합니다.

메시지 맵에서 테이블 메시지 맵 항목을 확장 하는 매크로 집합을 사용 하 여 정의 됩니다. 테이블 시작을 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 이 메시지 맵에 의해 처리 되는 클래스와 처리 되지 않은 메시지 전달 되는 부모 클래스를 정의 하는 매크로 호출 합니다. 테이블 사용 하 여 종료 합니다 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) 매크로 호출 합니다.

이러한 두 매크로 호출 간에이 메시지 맵을 통해 처리할 각 메시지에 대 한 항목이입니다. 모든 표준 Windows 메시지에 ON_WM_ 형식의 매크로*MESSAGE_NAME* 해당 메시지에 대 한 진입점을 생성 하는 합니다.

각 Windows 메시지의 매개 변수를 압축 하 고 형식 안전성을 제공 하는 표준 함수 서명 정의 되었습니다. 이러한 시그니처 파일 Afxwin.h 선언에서 찾을 수 있습니다의 [CWnd](../mfc/reference/cwnd-class.md)합니다. 각 키워드와 함께 표시 됩니다 **afx_msg** 에 쉽게 식별할 수 있도록 합니다.

> [!NOTE]
> Classwizard 함께 사용 해야 합니다 **afx_msg** 메시지 맵 처리기 선언에서 키워드입니다.

이러한 함수 시그니처는 간단한 규칙을 사용 하 여 파생 되었습니다. 함수의 이름을 항상 시작 `"On`"입니다. 이 배열을 제거 "WM_"를 사용 하 여 Windows 메시지의 이름과 대문자로 시작 하는 각 단어의 첫 글자 나옵니다. 매개 변수의 순서가 *wParam* 뒤 `LOWORD`(*lParam*) 한 다음 `HIWORD`(*lParam*). 사용 되지 않는 매개 변수 전달 되지 않습니다. MFC 클래스에 의해 래핑된 모든 핸들은 적절 한 MFC 개체에 대 한 포인터를 변환 됩니다. WM_PAINT 메시지를 처리 하는 방법을 보여 주는 다음 예제는 `CMyWnd::OnPaint` 호출할 함수입니다.

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

메시지 맵 테이블은 모든 함수 또는 클래스 정의의 범위를 벗어나는 정의 되어야 합니다. Extern "C" 블록에 추가 되지 않아야 합니다.

> [!NOTE]
> ClassWizard 간에 발생 하는 메시지 맵 항목을 수정 합니다는 / / {{및 / /}을 (를) 주석 대괄호입니다.

## <a name="user-defined-windows-messages"></a>사용자 정의 Windows 메시지

사용자 정의 메시지를 사용 하 여 메시지 구조에 포함 될 수 있습니다 합니다 [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) 매크로입니다. 이 매크로 메시지 수와 형식의 메서드를 허용합니다.

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

이 예제에서는 사용자 정의 메시지에 대 한 표준 WM_USER 기본에서 파생 된 Windows 메시지 ID가 있는 사용자 지정 메시지 처리기를 설정 합니다. 다음 예제에서는이 처리기를 호출 하는 방법을 보여 줍니다.

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

이 방법을 사용 하는 사용자 정의 메시지의 범위는 0x7fff WM_USER 범위에 있어야 합니다.

> [!NOTE]
> 클래스 마법사 클래스 마법사 사용자 인터페이스에서 입력 ON_MESSAGE 처리기 루틴을 지원 하지 않습니다. 시각적 개체에서 수동으로 입력 해야 합니다 C++ 편집기입니다. 클래스 마법사는 이러한 항목을 구문 분석를 다른 메시지 맵 항목 처럼을 탐색할 수 있도록 합니다.

## <a name="registered-windows-messages"></a>등록 된 Windows 메시지

합니다 [RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) 함수를 사용 하는 시스템 전체에서 고유 하 게 보장 되는 새 창 메시지를 정의 합니다. ON_REGISTERED_MESSAGE 매크로 이러한 메시지 처리에 사용 됩니다. 이 매크로의 이름을 허용 된 *UINT 거의* 등록 된 windows 메시지 ID를 포함 하는 변수 예

```cpp
class CMyWnd : public CMyParentWndClass
{
public:
    CMyWnd();

    //{{AFX_MSG(CMyWnd)
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};

static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

등록 된 Windows 메시지 ID 변수 (이 예제의 WM_FIND) 이어야 합니다는 *NEAR* 방식으로 인해 변수 ON_REGISTERED_MESSAGE 구현 됩니다.

이 방법을 사용 하는 사용자 정의 메시지의 범위 0xC000에서 0xFFFF 범위의 됩니다.

> [!NOTE]
> 클래스 마법사 클래스 마법사 사용자 인터페이스에서 입력 ON_REGISTERED_MESSAGE 처리기 루틴을 지원 하지 않습니다. 텍스트 편집기에서 수동으로 입력 해야 합니다. 클래스 마법사는 이러한 항목을 구문 분석를 다른 메시지 맵 항목 처럼을 탐색할 수 있도록 합니다.

## <a name="command-messages"></a>명령 메시지

메뉴 및 액셀러레이터에서 명령 메시지 ON_COMMAND 매크로 사용 하 여 메시지 맵에서 처리 됩니다. 이 매크로 메서드 및 명령 ID를 허용합니다. 있는 특정 WM_COMMAND 메시지만 *wParam* 같은 지정된 된 명령 ID는 메시지 맵 항목에 지정 된 메서드에서 처리 됩니다. 명령 처리기 멤버 함수는 매개 변수가 없습니다 및 반환 **void**합니다. 매크로는 다음 폼에 있습니다.

```cpp
ON_COMMAND(id, memberFxn)
```

명령 업데이트 메시지 동일한 메커니즘을 통해 라우팅됩니다 있지만 ON_UPDATE_COMMAND_UI 매크로 대신 사용 합니다. 명령 업데이트 처리기 멤버 함수는 단일 매개 변수를에 대 한 포인터를 [CCmdUI](../mfc/reference/ccmdui-class.md) 개체를 반환 **void**합니다. 형식은 매크로

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

고급 사용자는 확장 된 형태의 명령 메시지 처리기는 ON_COMMAND_EX 매크로 사용할 수 있습니다. 매크로는 ON_COMMAND 기능의 상위 집합을 제공합니다. 확장된 명령 처리기 멤버 함수는 단일 매개 변수를 **UINT** 명령 ID를 포함 하 고 반환 된 **BOOL**합니다. 반환 값 이어야 **TRUE** 명령 처리 된 것을 나타냅니다. 그렇지 않으면 라우팅 다른 명령 대상 개체에 계속 됩니다.

이러한 형식의 예:

- Resource.h 내부 (일반적으로 시각적 개체에서 생성 된 C++)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- 클래스 선언 내에서

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- 메시지 맵 정의 내에서

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- 구현 파일에서

    ```cpp
    void CMyClass::OnMyCommand()
    {
        // handle the command
    }

    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)
    {
        // set the UI state with pCmdUI
    }

    BOOL CMyClass::OnComplexCommand(UINT nID)
    {
        // handle the command
        return TRUE;
    }
    ```

고급 사용자는 단일 명령 처리기를 사용 하 여 다양 한 명령 처리할 수 있습니다. [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) 또는 ON_COMMAND_RANGE_EX 합니다. 이러한 매크로 대 한 자세한 내용은 제품 설명서를 참조 하세요.

> [!NOTE]
> 클래스 마법사 만들기 ON_COMMAND 및 ON_UPDATE_COMMAND_UI 처리기를 지원 하지만 만들기 ON_COMMAND_EX 또는 ON_COMMAND_RANGE 처리기를 지원 하지 않습니다. 그러나 클래스 마법사 구문 분석 하 고 4 개의 명령 처리기 변형이 모두를 탐색할 수 있도록 합니다.

## <a name="control-notification-messages"></a>컨트롤 알림 메시지

창에 자식 컨트롤의 추가 비트 정보 메시지에 전송 되는 메시지 맵 항목: 컨트롤의 id입니다. 메시지 맵 항목에 지정 된 메시지 처리기는 다음 조건이 true 인 경우에 호출 됩니다.

- 컨트롤 알림 코드 (변수의 상위 단언 *lParam*), BN_CLICKED, 예: 메시지 맵 항목에 지정 된 알림 코드와 일치 합니다.

- 컨트롤 ID (*wParam*) 메시지 맵 항목에 지정 된 컨트롤 ID와 일치 합니다.

사용자 지정 컨트롤 알림 메시지를 사용할 수는 [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) 매크로를 사용자 지정 알림 코드를 사용 하 여 메시지 맵 항목을 정의 합니다. 형식은이 매크로

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

고급 사용에 대 한 [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) 동일한 처리기를 사용 하 여 컨트롤의 범위에서 특정 컨트롤 알림 처리를 사용할 수 있습니다.

> [!NOTE]
> 클래스 마법사 사용자 인터페이스에서 ON_CONTROL 또는 ON_CONTROL_RANGE 처리기 만들기를 지원 하지 않습니다. 텍스트 편집기를 사용 하 여 수동으로 입력 해야 합니다. 클래스 마법사는 이러한 항목을 구문 분석를 다른 메시지 맵 항목 처럼을 탐색할 수 있도록 합니다.

Windows 공용 컨트롤 사용 더욱 강력해 진 [WM_NOTIFY](/windows/desktop/controls/wm-notify) 복잡 한 컨트롤 알림에 대 한 합니다. 이 버전의 MFC는 ON_NOTIFY 및 ON_NOTIFY_RANGE 매크로 사용 하 여 새 메시지에 대 한 직접 지원 합니다. 이러한 매크로 대 한 자세한 내용은 제품 설명서를 참조 하세요.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
