---
title: 'TN061: ON_NOTIFY 및 WM_NOTIFY 메시지'
ms.date: 06/28/2018
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
ms.openlocfilehash: 74eb39a855da3ff3e6da7f14a76bf0804919826d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399579"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY 및 WM_NOTIFY 메시지

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트 새 WM_NOTIFY 메시지에 대 한 배경 정보를 제공 하 고는 권장 하 고 가장 일반적인 방법은 MFC 응용 프로그램에서 WM_NOTIFY 메시지를 처리를 설명 합니다.

**Windows에서 알림 메시지 3.x**

Windows의 부모에 대 한 메시지를 전송 하 여 콘텐츠 및 선택 컨트롤 배경에 그리기 3.x 변경 컨트롤의 마우스 클릭 같은 이벤트의 부모에 게 알립니다. 간단한 알림 (예: BN_CLICKED) 알림 코드를 사용 하 여 특수 WM_COMMAND 메시지로 전송 됩니다 및 ID에 압축을 제어할 *wParam* 하 고 있는 컨트롤의 핸들 *lParam*합니다. 이후 유의 *wParam* 및 *lParam* 는 추가 데이터를 전달할 방법이 전체-이러한 메시지는 간단한 알림만 될 수 있습니다. 예를 들어 BN_CLICKED 알림에서 방법이 있으면 단추를 클릭 했을 때 마우스 커서의 위치에 대 한 정보를 보내도록 합니다.

WM_CTLCOLOR, WM_VSCROLL, 하, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_ 메시지 특수 한 용도의 다양 한 컨트롤 3.x 해야 Windows에서 추가 데이터를 포함 하는 알림 메시지를 보내면 사용 CHARTOITEM, WM_VKEYTOITEM, 및 등입니다. 이러한 메시지는 다시 전송 하는 컨트롤에 반영 될 수 있습니다. 자세한 내용은 참조 하세요. [TN062: Windows 컨트롤에 대 한 리플렉션 메시지](../mfc/tn062-message-reflection-for-windows-controls.md)합니다.

**Win32에서 알림 메시지**

Windows 3.1에 존재 하는 컨트롤에 대 한 Win32 API에서는 대부분의 사용 된 알림 메시지를 Windows 3.x입니다. 그러나 Win32도 다양 한 정교 하 고 복잡 한 컨트롤에 추가 Windows에서 지원 되는 3.x입니다. 자주, 이러한 컨트롤의 알림 메시지를 사용 하 여 추가 데이터를 보내도록 해야 합니다. 새로 추가 하는 대신 **WM_** <strong>\*</strong> 에 하나의 메시지를 전달할 수는 WM_NOTIFY를 추가 하도록 선택한 각 새 알림이 추가 데이터를 Win32 API의 설계자는에 대 한 메시지 표준화 된 방식으로 추가 데이터의 양입니다.

WM_NOTIFY 메시지 메시지를 전송 하는 컨트롤의 ID를 포함 *wParam* 의 구조에 대 한 포인터 *lParam*합니다. 이 구조는 하나는 **NMHDR** 구조 또는 일부 큰 구조체는 **NMHDR** 첫 번째 멤버로 구조입니다. 이후에 합니다 **NMHDR** 멤버는 첫 번째,이 구조에 대 한 포인터에 대 한 포인터를 사용할 수는 **NMHDR** 또는 캐스팅 하는 방법에 따라 더 큰 구조에 대 한 포인터입니다.

대부분의 경우에서 더 큰 구조체 포인터를 가리킵니다 및 사용 하는 경우 캐스트 해야 합니다. 일반적인 알림과 같은 몇 가지 알림에 (시작 하는 이름의 **NM_**) 도구 컨트롤의 TTN_SHOW TTN_POP 알림과 팁은 및는 **NMHDR** 실제로 사용 되는 구조입니다.

합니다 **NMHDR** 구조 또는 초기 멤버 핸들 및 메시지와 알림 코드 (예: TTN_SHOW)를 전송 하는 컨트롤의 ID를 포함 합니다. 형식의 합니다 **NMHDR** 구조는 다음과 같습니다.

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

TTN_SHOW 메시지의 경우는 **코드** 멤버 TTN_SHOW로 설정 됩니다.

대부분의 알림을 포함 하는 큰 구조에 포인터를 전달 합니다는 **NMHDR** 첫 번째 멤버로 구조입니다. 예를 들어 구조를에서 목록 뷰 컨트롤에서 키를 누를 때 전송 되는 목록 뷰 컨트롤의 LVN_KEYDOWN 알림 메시지를 사용 하는 것이 좋습니다. 가리키는 포인터를 **LV_KEYDOWN** 구조는 아래와 같이 정의 됩니다.

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

이후 유의 합니다 **NMHDR** 멤버는이 구조에서 첫 번째, 알림 메시지에 전달 하는 포인터에 대 한 포인터로 캐스팅 될 수는 **NMHDR** 에 대 한 포인터 또는 **LV_KEYDOWN** .

**모든 새 Windows 컨트롤에 공통 된 알림**

일부 알림은 모든 새 Windows 컨트롤에 공통적으로 적용 합니다. 이러한 알림을 전달에 대 한 포인터를 **NMHDR** 구조입니다.

|알림 코드|보낸 때문입니다.|
|-----------------------|------------------|
|NM_CLICK|사용자는 컨트롤에서 마우스 왼쪽된 단추 클릭|
|NM_DBLCLK|컨트롤의 사용자 두 번 클릭된 마우스 왼쪽된 단추|
|NM_RCLICK|사용자는 컨트롤에서 마우스 오른쪽 단추 클릭|
|NM_RDBLCLK|사용자 컨트롤을 두 번 클릭된 마우스 오른쪽 단추로|
|NM_RETURN|사용자는 컨트롤에 입력 포커스가 있는 동안 ENTER 키를 누를|
|NM_SETFOCUS|컨트롤에 입력된 포커스가 지정|
|NM_KILLFOCUS|컨트롤에 입력된 포커스가 손실 되었습니다.|
|NM_OUTOFMEMORY|사용 가능한 메모리가 부족 하기 때문에 컨트롤이 작업을 완료할 수 없습니다.|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON_NOTIFY: MFC 응용 프로그램에서 WM_NOTIFY 메시지를 처리합니다.

함수 `CWnd::OnNotify` 알림 메시지를 처리 합니다. 기본 구현 호출 알림 처리기에 대 한 메시지 맵을 확인 합니다. 일반적으로 재정의 하지 `OnNotify`합니다. 대신, 처리기 함수를 제공 하 고 소유자 창의 클래스의 메시지 맵에 해당 처리기에 대 한 메시지 맵 항목을 추가 합니다.

ClassWizard 속성 시트를 통해 ClassWizard는 ON_NOTIFY 메시지 맵 항목을 만들고 기본 처리기 함수를 사용 하 여 제공 수 있습니다. 클래스 마법사를 사용 하 여 간편 하 게에 대 한 자세한 내용은 참조 하세요. [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.

ON_NOTIFY 메시지 맵 매크로는 다음 구문이 있습니다.

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

여기서 매개 변수는 다음과 같습니다.

*wNotifyCode*<br/>
알림 메시지는 LVN_KEYDOWN 같은 처리에 대 한 코드입니다.

*ID*<br/>
알림이 전송 되는 컨트롤의 자식 식별자입니다.

*memberFxn*<br/>
이 알림 메시지를 보낼 때 호출 되는 멤버 함수입니다.

멤버 함수는 다음과 같은 프로토타입을 사용 하 여 선언 해야 합니다.

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

여기서 매개 변수는 다음과 같습니다.

*pNotifyStruct*<br/>
위 섹션에 설명 된 대로 알림 구조에 대 한 포인터입니다.

*result*<br/>
결과 코드에 대 한 포인터를 반환 하기 전에 설정 합니다.

## <a name="example"></a>예제

멤버 함수를 지정 하려면 `OnKeydownList1` LVN_KEYDOWN 메시지를 처리 하는 `CListCtrl` ID가 갖는 `IDC_LIST1`, 클래스 마법사를 사용 하 여 메시지 맵에 다음을 추가 하는:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

위의 예에서 classwizard 함께 사용 하 여 제공 된 함수는:

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

ClassWizard 적절 한 형식의 포인터를 자동으로 제공 하는 참고 합니다. 알림 구조 중 하나를 통해 액세스할 수 있습니다 *pNMHDR* 하거나 *pLVKeyDow*합니다.

##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE

컨트롤의 집합에 대 한 동일한 WM_NOTIFY 메시지를 처리 해야 할 경우 ON_NOTIFY 대신 ON_NOTIFY_RANGE를 사용할 수 있습니다. 예를 들어 특정 알림 메시지에 대해 동일한 작업을 수행 하려는 단추 집합이 할 수 있습니다.

ON_NOTIFY_RANGE를 사용 하면 인접 한 범위의 시작을 지정 하 고 자식 식별자의 범위를 종료 하 여 알림 메시지를 처리 하는 자식 식별자 지정 합니다.

ClassWizard ON_NOTIFY_RANGE; 처리 하지 않습니다. 를 사용 하려면 메시지 지도 직접 편집 해야 합니다.

ON_NOTIFY_RANGE 함수 프로토타입을 확인 하 고 메시지 맵 항목은 다음과 같습니다.

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

여기서 매개 변수는 다음과 같습니다.

*wNotifyCode*<br/>
알림 메시지는 LVN_KEYDOWN 같은 처리에 대 한 코드입니다.

*ID*<br/>
식별자의 인접 한 범위에서 첫 번째 식별자입니다.

*idLast*<br/>
식별자의 인접 한 범위에서 마지막 식별자입니다.

*memberFxn*<br/>
이 알림 메시지를 보낼 때 호출 되는 멤버 함수입니다.

멤버 함수는 다음과 같은 프로토타입을 사용 하 여 선언 해야 합니다.

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

여기서 매개 변수는 다음과 같습니다.

*ID*<br/>
알림을 전송 하는 컨트롤의 자식 식별자입니다.

*pNotifyStruct*<br/>
위에서 설명한 것 처럼 알림 구조에 대 한 포인터입니다.

*result*<br/>
결과 코드에 대 한 포인터를 반환 하기 전에 설정 합니다.

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

알림 메시지를 처리 하도록 라우팅에 둘 이상의 개체를 원한다 면 ON_NOTIFY (또는 ON_NOTIFY_RANGE) 대신 ON_NOTIFY_EX (또는 ON_NOTIFY_EX_RANGE)을 사용할 수 있습니다. 간의 유일한 차이점을 **EX** 버전과 정식 버전에 대 한 멤버 함수가 호출 하는 **EX** 버전을 반환 합니다를 **BOOL** 나타내는 여부 메시지 처리를 계속 합니다. 반환 **FALSE** 이 함수에서 둘 이상의 개체에서 같은 메시지를 처리할 수 있습니다.

ON_NOTIFY_EX 또는 ON_NOTIFY_EX_RANGE; ClassWizard 처리 하지 않습니다. 둘 중 하나를 사용 하려는 경우에 메시지 지도 직접 편집 해야 합니다.

메시지 맵 항목 및 ON_NOTIFY_EX 및 ON_NOTIFY_EX_RANGE 함수 프로토타입에 다음과 같습니다. 매개 변수의 의미는 동일 이외**EX** 버전입니다.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

위의 두 항목 모두에 대 한 프로토타입을 동일합니다.

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

두 경우 모두 *id* 알림을 전송 하는 컨트롤의 자식 식별자를 포함 합니다.

함수 반환 해야 합니다 **TRUE** 알림 메시지를 완전히 처리 된 경우 또는 **FALSE** 명령 라우팅의 다른 개체에 메시지를 처리 하는 경우 있어야 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
