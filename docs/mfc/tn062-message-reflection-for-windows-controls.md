---
title: 'TN062: Windows 컨트롤에 대 한 메시지 리플렉션'
ms.date: 06/28/2018
f1_keywords:
- vc.controls.messages
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
ms.openlocfilehash: aa189eec430d72bef753fef7ebbe9ad929d76c87
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351849"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>TN062: Windows 컨트롤에 대 한 메시지 리플렉션

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트에서는 메시지 리플렉션, MFC 4.0의 새로운 기능을 설명합니다. 또한 메시지 리플렉션을 사용 하는 간단한 재사용 가능한 컨트롤 만들기에 대 한 지침을 포함 합니다.

이 기술 노트는 ActiveX 컨트롤 (이전의 OLE 컨트롤)에 적용 될 때 메시지 리플렉션을 설명 하지 않습니다. 문서를 참조 하십시오 [ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)합니다.

**메시지 리플렉션 란**

Windows 컨트롤 자주 해당 부모 창에 알림 메시지를 보냅니다. 예를 들어 많은 컨트롤이 부모 컨트롤의 배경을 그리는 브러시를 제공할 수 있도록 해당 부모 (WM_CTLCOLOR 또는 해당 변형 중 하나) 컨트롤 색 알림 메시지를 보냅니다.

Windows 및 MFC 버전 4.0에서 부모 창 자주 대화 상자는 이러한 메시지를 처리 하는 일을 담당 합니다. 이 메시지를 처리 하기 위한 코드 부모 창의 클래스에 있어야 하며 해당 메시지를 처리 해야 하는 모든 클래스에 중복 수 있음을 의미 합니다. 위의 경우 사용자 지정 배경 사용 하 여 컨트롤 지정 하려는 모든 대화 상자 컨트롤 색 알림 메시지를 처리 해야 합니다. 손쉽게 자체 배경색을 처리 하는 컨트롤 클래스를 작성할 수 있습니다 하는 경우에 코드를 재사용할 수 것입니다.

MFC 4.0에서 이전 메커니즘은 계속 작동-부모 windows 알림 메시지를 처리할 수 있습니다. 그러나 또한 MFC 4.0을 용이 하 게 다시 사용 "메시지 리플렉션" 이라는 기능을 제공 하 여 이러한 알림 메시지를 자식 컨트롤 창 또는 부모 창에서 또는 둘 다에서 처리할 수 있도록 합니다. 리플 렉 트 WM_CTLCOLOR 메시지를 처리 하 여 자체 배경색을 설정 하는 컨트롤 클래스를 작성해 수 예에서 컨트롤 배경 색-부모에 의존 하지 않고 있습니다. (메시지 리플렉션 MFC에서 구현 된 이후 없습니다, Windows에서 부모 창 클래스 해야 수에서 파생 된 `CWnd` 메시지 리플렉션 작업에 대 한 합니다.)

이전 버전의 MFC (WM_DRAWITEM, 및 등)의 소유자가 그린 목록 상자에 대 한 메시지와 같은 몇 가지 메시지에 대 한 가상 함수를 제공 하 여 메시지 리플렉션 비슷한 않았습니다. 새 메시지 리플렉션 메커니즘 일반화 되어 일치 합니다.

메시지 리플렉션은 4.0 이전 버전의 MFC 용으로 작성 된 코드와 역방향 호환이 가능 합니다.

특정 메시지에 대 한 처리기를 제공한 또는 부모 창의 클래스에서 메시지의 범위에 대 한 재정의 하는 경우 고유한 처리기의 기본 클래스 처리기 함수를 호출 하지 않으면 제공 된 동일한 메시지에 대 한 메시지 처리기를 반영 합니다. 예를 들어 대화 상자 클래스에서 WM_CTLCOLOR를 처리 하는 경우에 처리 리플 렉 트 된 메시지 처리기를 재정의 합니다.

리플 렉 트 된 메시지 처리기를 통해 해당 메시지를 전송 하는 자식 컨트롤에 없는 경우에 처리기를 호출할 수의 부모 창 클래스에 특정 WM_NOTIFY 메시지 또는 범위의 WM_NOTIFY 메시지에 대 한 처리기를 제공 하는 경우 `ON_NOTIFY_REFLECT()`합니다. 사용 하는 경우 `ON_NOTIFY_REFLECT_EX()` 메시지 구조의 메시지 처리기 수 또는 부모 창에 메시지를 처리를 사용할 수 없습니다. 처리기를 반환 하는 경우 **FALSE**를 반환 하는 호출 하는 동안 부모도 메시지를 처리할 수 됩니다 **TRUE** 을 처리 하는 부모를 허용 하지 않습니다. 리플 렉 트 된 메시지 전에 알림 메시지 처리는 참고 합니다.

WM_NOTIFY 메시지를 보낼 때 컨트롤을 처리 하는 첫 번째 기회를 제공 됩니다. 다른 리플 렉 트 된 메시지를 보낼 경우 부모 창에는 첫 번째 예외를 처리 하 고 컨트롤 리플 렉 트 된 메시지를 수신 합니다. 이렇게 하려면 처리기 함수 및 적절 한 컨트롤의 클래스 메시지 맵 항목 해야 합니다.

리플 렉 트 된 메시지에 대 한 메시지 맵 매크로 일반 알림에 대 한 보다 약간 다릅니다: 있기 *_REFLECT* 일반적인 이름에 추가 됩니다. 예를 들어 부모에서 WM_NOTIFY 메시지를 처리 하려면 부모 메시지 구조의 ON_NOTIFY 매크로 사용할 수 있습니다. 자식 컨트롤에 리플 렉 트 된 메시지를 처리 하려면 자식 컨트롤의 메시지 구조의 ON_NOTIFY_REFLECT 매크로 사용 합니다. 경우에 따라 매개 변수를 다른 사례도 있습니다. 참고 클래스 마법사 수 일반적으로 메시지 맵 항목을 추가 하 고 올바른 매개 변수를 사용 하 여 스 켈 레 톤 함수 구현을 제공 합니다.

참조 [TN061: ON_NOTIFY 및 WM_NOTIFY 메시지](../mfc/tn061-on-notify-and-wm-notify-messages.md) 새 WM_NOTIFY 메시지에 대 한 정보에 대 한 합니다.

**리플 렉 트 된 메시지 처리기 함수 프로토타입 및 메시지 맵 항목**

리플 렉 트 된 컨트롤 알림 메시지를 처리 하려면 아래 표에 나열 된 함수 프로토타입을 확인 하 고 메시지 맵 매크로 사용 합니다.

일반적으로 클래스 마법사를 이러한 메시지 맵 항목을 추가 하 고 스 켈 레 톤 함수 구현을 제공할 수 있습니다. 참조 [반영 메시지의 메시지 처리기 정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) 리플 렉 트 된 메시지에 대 한 처리기를 정의 하는 방법에 대 한 정보에 대 한 합니다.

메시지 이름이 반영된 매크로 이름으로 변환할 앞 *ON_* 및 추가 *_REFLECT*합니다. 예를 들어 WM_CTLCOLOR ON_WM_CTLCOLOR_REFLECT 됩니다. (반영 될 수 있는 메시지를 보려면 수행할 아래 표에 있는 매크로 항목 변환 합니다.)

위의 규칙에 세 가지 예외는 다음과 같습니다.

- WM_COMMAND 알림에 매크로 ON_CONTROL_REFLECT입니다.

- WM_NOTIFY 반사의 매크로 ON_NOTIFY_REFLECT입니다.

- ON_UPDATE_COMMAND_UI 반사의 매크로 ON_UPDATE_COMMAND_UI_REFLECT입니다.

위의 경우 각각의 처리기 멤버 함수 이름을 지정 해야 합니다. 다른 경우에서 처리기 함수에 대 한 표준 이름을 사용 해야 합니다.

매개 변수의 의미 및 함수의 반환 값에서 함수 이름 또는 함수 이름 앞에 나와 *에서* 앞에 추가 합니다. 예를 들어 `CtlColor` 에 설명 되어 있습니다 `OnCtlColor`합니다. 리플 렉 트 된 메시지 처리기를 여러 부모 창에서 유사한 처리기 보다 더 적은 매개 변수가 필요합니다. 설명서의 정식 매개 변수 이름 사용 하 여 아래 테이블의 이름과 일치만.

|맵 항목|함수 프로토타입|
|---------------|------------------------|
|**ON_CONTROL_REFLECT(** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **( );**|
|**ON_NOTIFY_REFLECT(** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg void** `memberFxn` **( NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT**<strong>\*</strong> *result* **);**|
|**ON_UPDATE_COMMAND_UI_REFLECT(** `memberFxn` **)**|**afx_msg void** `memberFxn` **( CCmdUI**<strong>\*</strong> `pCmdUI` **);**|
|**ON_WM_CTLCOLOR_REFLECT( )**|**afx_msg HBRUSH CtlColor ( CDC**<strong>\*</strong> `pDC` **, UINT** `nCtlColor` **);**|
|**ON_WM_DRAWITEM_REFLECT( )**|**afx_msg void DrawItem ( LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|
|**ON_WM_MEASUREITEM_REFLECT( )**|**afx_msg MeasureItem void (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|
|**ON_WM_DELETEITEM_REFLECT( )**|**afx_msg void DeleteItem ( LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|
|**ON_WM_COMPAREITEM_REFLECT( )**|**afx_msg int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|
|**ON_WM_CHARTOITEM_REFLECT( )**|**afx_msg int CharToItem (UINT** `nKey` **, UINT** `nIndex` **);**|
|**ON_WM_VKEYTOITEM_REFLECT( )**|**afx_msg int VKeyToItem ( UINT** `nKey` **, UINT** `nIndex` **);**|
|**ON_WM_HSCROLL_REFLECT( )**|**afx_msg void HScroll ( UINT** `nSBCode` **, UINT** `nPos` **);**|
|**ON_WM_VSCROLL_REFLECT( )**|**afx_msg VScroll void (UINT** `nSBCode` **, UINT** `nPos` **);**|
|**ON_WM_PARENTNOTIFY_REFLECT( )**|**afx_msg void ParentNotify ( UINT** `message` **, LPARAM** `lParam` **);**|

ON_NOTIFY_REFLECT 및 ON_CONTROL_REFLECT 매크로 변형이 지정된 된 메시지를 처리 하려면 둘 이상의 개체 (예: 컨트롤 및 해당 부모)를 허용 하는 경우

|맵 항목|함수 프로토타입|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX(** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **( NMHDR** <strong>\*</strong> `pNotifyStruct` **, LRESULT**<strong>\*</strong> *result* **);**|
|**ON_CONTROL_REFLECT_EX(** `wNotifyCode` **,** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **( );**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>리플렉션된 메시지 처리 합니다. 재사용 가능한 컨트롤의 예

이라는 재사용 가능한 컨트롤을 만드는 간단한 예제 `CYellowEdit`합니다. 노란색 배경 기반 검은색 텍스트를 표시 한다는 컨트롤이 일반 편집 컨트롤을 동일 하 게 작동 합니다. 쉽게 허용 하는 멤버 함수를 추가할 수는 `CYellowEdit` 컨트롤을 다른 색으로 표시 합니다.

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>재사용 가능한 컨트롤을 만드는 예제를 실행 하려면

1. 기존 응용 프로그램에서 새 대화 상자를 만듭니다. 자세한 내용은 참조는 [대화 상자 편집기](../windows/dialog-editor.md) 항목입니다.

   재사용 가능한 컨트롤을 개발 하는 응용 프로그램이 있어야 합니다. 사용 하 여 기존 응용 프로그램에 없는 경우 응용 프로그램 마법사를 사용 하 여 대화 상자 기반 응용 프로그램을 만듭니다.

2. 프로젝트를 사용 하 여 시각적 개체로 로드 C++를 클래스 마법사를 사용 하 여 라는 새 클래스를 만듭니다 `CYellowEdit` 기반 `CEdit`합니다.

3. 세 가지 멤버 변수를 추가 하 여 `CYellowEdit` 클래스입니다. 처음 두 됩니다 *COLORREF* 텍스트 색과 배경색을 보유할 변수입니다. 세 번째는 `CBrush` 배경을 그리는 브러시를 포함 하는 개체입니다. 합니다 `CBrush` 개체를 사용 하면 한 번, 단순히 그 참조 하는 브러시를 만들고 브러시를 자동으로 제거 하는 `CYellowEdit` 컨트롤이 소멸 될 합니다.

4. 다음과 같이 생성자를 작성 하 여 멤버 변수를 초기화 합니다.

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. 리플 렉 트 된 WM_CTLCOLOR 메시지에 대 한 처리기를 추가 클래스 마법사를 사용 하 여 `CYellowEdit` 클래스입니다. 메시지를 처리할 수 있습니다 목록의 메시지 이름 앞에 등호 메시지 반영 됩니다 나타내는 note 합니다. 에 설명 되어 [반영 메시지의 메시지 처리기 정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)합니다.

   다음 메시지 맵 매크로 및 스 켈 레 톤 함수를 추가 하는 클래스 마법사:

    ```cpp
    ON_WM_CTLCOLOR_REFLECT()
    // Note: other code will be in between....

    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)
    {
        // TODO: Change any attributes of the DC here
        // TODO: Return a non-NULL brush if the
        //       parent's handler should not be called
        return NULL;
    }
    ```

6. 다음 코드를 사용 하 여 함수의 본문을 대체 합니다. 코드는 텍스트 색, 텍스트 배경색 및 컨트롤의 나머지 부분에 대 한 배경색을 지정합니다.

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. 편집 컨트롤을 대화 상자, 작성 한 다음 편집 컨트롤에 컨트롤 키를 누른 채 두 번 클릭 하 여 멤버 변수에 연결 합니다. 멤버 변수 추가 대화 상자에서 변수 이름을 완료 하 고 "CYellowEdit" 변수 형식에 대 한 범주에 대 한 "컨트롤"을 선택 합니다. 대화 상자에서 탭 순서를 설정 하려면 두는 것을 잊지 마세요. 또한에 대 한 헤더 파일을 포함 해야 합니다 `CYellowEdit` 대화 상자의 헤더 파일에는 컨트롤입니다.

8. 애플리케이션을 빌드하고 실행합니다. 편집 컨트롤에는 노란색 배경이 됩니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
