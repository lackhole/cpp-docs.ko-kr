---
title: 클립보드
ms.date: 11/04/2016
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
ms.openlocfilehash: 5814b2fdfc7fbcaca00037cc64dd71aa27d65cc3
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504620"
---
# <a name="clipboard"></a>클립보드

이 문서에서는 MFC 응용 프로그램에서 Windows 클립보드에 대 한 지원을 구현 하는 방법을 설명 합니다. Windows 클립보드는 두 가지 방법으로 사용 됩니다.

- 잘라내기, 복사 및 붙여넣기 등의 표준 편집 메뉴 명령을 구현 합니다.

- 놓기 (OLE) 및 끌어서 전송 균일 한 데이터를 구현 합니다.

클립보드는 원본과 대상 간의 데이터 전송의 표준 Windows 메서드입니다. 또한 OLE 작업에 매우 유용할 수 있습니다. OLE의 되면서 메커니즘은 두 가지 클립보드 Windows에서. 표준 Windows 클립보드 API는 여전히 사용할 수 있지만 OLE 데이터 전송 메커니즘을 사용 하 여 개의 보완 되었습니다. OLE 단일형 데이터 전송 (UDT) 잘라내기, 복사 및 붙여넣기 클립보드를 사용 하 여 원하는 끌어서 놓습니다.

클립보드는 전체 Windows 세션에서 공유 하는 핸들 또는 클래스 자체에 없기 때문에 시스템 서비스입니다. 클래스의 멤버 함수를 통해 클립보드를 관리할 [CWnd](../mfc/reference/cwnd-class.md)합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [각 클립보드 메커니즘을 사용 하는 경우](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [기존 Windows 클립보드 API를 사용 하 여](../mfc/clipboard-using-the-windows-clipboard.md)

- [OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md)

- [기타 서식 추가](../mfc/clipboard-adding-other-formats.md)

- [Windows 클립보드](/windows/desktop/dataxchg/clipboard)

- [끌어서 놓기 (OLE)를 구현합니다.](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
