---
title: 바로 가기 키 설정
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: 7b49f24039b130f74693e7567f5287476126f225
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511211"
---
# <a name="setting-a-hot-key"></a>바로 가기 키 설정

응용 프로그램은 다음 두 가지 방법 중 하나로 핫 키 ([Chotkeyctrl](../mfc/reference/chotkeyctrl-class.md)) 컨트롤에서 제공 하는 정보를 사용할 수 있습니다.

- 활성화할 창에 [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) 메시지를 전송 하 여 비 자식 창을 활성화 하는 전역 핫 키를 설정 합니다.

- Windows 함수 [Registerhotkey](/windows/win32/api/winuser/nf-winuser-registerhotkey)를 호출 하 여 스레드 관련 바로 가기 키를 설정 합니다.

## <a name="see-also"></a>참고자료

[CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
