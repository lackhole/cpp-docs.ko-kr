---
title: TOOLTIPTEXT 구조체
ms.date: 11/04/2016
f1_keywords:
- TOOLTIPTEXT
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
ms.openlocfilehash: 7d77ca7dc55273e6084e919323ed71e55fa68a2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181849"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT 구조체

작성에서에 [도구 설명 알림 처리기](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)를 사용 해야 합니다 **TOOLTIPTEXT** 구조입니다. 멤버는 **TOOLTIPTEXT** 구조는:

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
텍스트는 도구를 식별 합니다. 해야 할 수 있습니다이 구조체의 유일한 구성원은 컨트롤의 명령 id입니다. 컨트롤의 명령 ID는 이어야 합니다 *idFrom* 의 멤버를 **NMHDR** 구조를 구문을 사용 하 여 액세스할 `hdr.idFrom`. 참조 [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) 에 대 한 멤버의 설명은 합니다 **NMHDR** 구조입니다.

*lpszText*<br/>
도구에 대 한 텍스트를 수신 하는 문자열의 주소입니다.

*szText*<br/>
도구 설명 텍스트를 받는 버퍼입니다. 응용 프로그램 문자열 주소를 지정 하는 대신이 버퍼에 텍스트를 복사할 수 있습니다.

*hinst*<br/>
도구 설명 텍스트로 사용할 문자열을 포함 하는 인스턴스 핸들입니다. 하는 경우 *lpszText* 주소인 도구 설명 텍스트의이 멤버는 NULL입니다.

처리 하는 경우는 `TTN_NEEDTEXT` 알림 메시지를 다음 방법 중 하나에 표시할 문자열을 지정 합니다.

- 지정 된 버퍼에 텍스트를 복사 합니다 *szText* 멤버입니다.

- 텍스트를 포함 하는 버퍼의 주소를 복사 합니다 *lpszText* 멤버입니다.

- 에 문자열 리소스의 식별자를 복사 합니다 *lpszText* 멤버 및 리소스를 포함 하는 인스턴스 핸들을 복사 합니다 *hinst* 멤버.

## <a name="see-also"></a>참고자료

[CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
