---
title: Run 멤버 함수
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: 8271a10ad7439d2795dcc45d667b23b0932a0486
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308552"
---
# <a name="run-member-function"></a>Run 멤버 함수

프레임워크 응용 프로그램은 대부분의 시간을 [CWinApp](../mfc/reference/cwinapp-class.md) 클래스의 [Run](../mfc/reference/cwinapp-class.md#run) 멤버 함수에서 소비합니다. 초기화된 다음 `WinMain`은 `Run`을 호출하여 메시지 루프를 처리합니다.

`Run`은 사용할 수 있는 메시지가 있는지 메시지 큐를 확인하여 메시지 루프를 순환합니다. 메시지가 사용 가능한 경우 `Run`은 작업에 디스패치합니다. 사용 가능한 메시지가 없는 경우 `Run`은 `OnIdle`을 호출하여 사용자나 프레임워크에서 수행할 수 있는 유휴 시간 처리를 수행합니다. 메시지가 없고 유휴 처리를 수행하지 않는다면 응용 프로그램은 어떤 일이 발생될 때까지 대기합니다. 응용 프로그램이 종료되면 `Run`은 `ExitInstance`를 호출합니다. [OnIdle 멤버 함수](../mfc/onidle-member-function.md)의 그림은 메시지 루프의 작업 절차를 보여줍니다.

메시지 디스패치는 메시지의 종류에 따라 달라집니다. 자세한 내용은 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)을 참조합니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
