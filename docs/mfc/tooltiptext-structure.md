---
title: TOOLTIPTEXT 구조체
ms.date: 11/04/2016
f1_keywords:
- TOOLTIPTEXT
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
ms.openlocfilehash: 2eb899e66acbadbe45aae2c8adbb356bf4730191
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915243"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT 구조체

[도구 설명 알림 처리기](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)를 작성할 때 **TOOLTIPTEXT** 구조를 사용 해야 합니다. **TOOLTIPTEXT** 구조체의 멤버는 다음과 같습니다.

```cpp
typedef struct {
    NMHDR     hdr;        // required for all WM_NOTIFY messages
    LPTSTR    lpszText;   // see below
    TCHAR     szText[80]; // buffer for tool tip text
    HINSTANCE hinst;      // see below
    UINT      uflags;     // flag indicating how to interpret the
                          // idFrom member of the NMHDR structure
                          // that is included in the structure
} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;
```

*hdr*<br/>
텍스트를 필요로 하는 도구를 식별 합니다. 이 구조체의 유일한 멤버는 컨트롤의 명령 ID입니다. 컨트롤의 명령 ID는 구문을 `hdr.idFrom`사용 하 여 액세스 되는 **NMHDR** 구조의 *idfrom* 멤버에 있습니다. **NMHDR** 구조체의 멤버에 대 한 자세한 내용은 [NMHDR](/windows/desktop/api/richedit/ns-richedit-nmhdr) 를 참조 하세요.

*lpszText*<br/>
도구의 텍스트를 받을 문자열의 주소입니다.

*szText*<br/>
도구 설명 텍스트를 수신 하는 버퍼입니다. 응용 프로그램은 문자열 주소를 지정 하는 대신이 버퍼에 텍스트를 복사할 수 있습니다.

*hinst*<br/>
도구 설명 텍스트로 사용할 문자열을 포함 하는 인스턴스의 핸들입니다. *LpszText* 가 도구 설명 텍스트의 주소인 경우이 멤버는 NULL입니다.

`TTN_NEEDTEXT` 알림 메시지를 처리할 때 다음 방법 중 하나로 표시할 문자열을 지정 합니다.

- *Sztext* 멤버로 지정 된 버퍼에 텍스트를 복사 합니다.

- 텍스트를 포함 하는 버퍼의 주소를 *lpszText* 멤버에 복사 합니다.

- 문자열 리소스의 식별자를 *lpszText* 멤버에 복사 하 고 리소스를 포함 하는 인스턴스의 핸들을 *hinst* 멤버에 복사 합니다.

## <a name="see-also"></a>참고자료

[CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
