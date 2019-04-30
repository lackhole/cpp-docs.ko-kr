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

Framework 응용 프로그램을 대부분의 시간을 소비 합니다 [실행할](../mfc/reference/cwinapp-class.md#run) 클래스의 멤버 함수 [CWinApp](../mfc/reference/cwinapp-class.md)합니다. 초기화 한 다음 `WinMain` 호출 `Run` 메시지 루프를 처리 합니다.

`Run` 메시지 루프를 사용할 수 있는 메시지에 대 한 메시지 큐를 검사 돌아가면서 선택 합니다. 메시지가 사용 가능한 경우 `Run` 작업에 디스패치합니다. 메시지가 사용 가능한 경우는 경우가 물론 `Run` 호출 `OnIdle` 수행 유휴 시간 처리 프레임 워크에서 필요할 수 있는 작업을 수행할 합니다. 가 없는 메시지 및 유휴 프로세스가 작업을 수행 하는 경우 응용 프로그램 일이 발생 될 때까지 대기 합니다. 응용 프로그램이 종료 되 면 `Run` 호출 `ExitInstance`합니다. 에 있는 그림과 [OnIdle 멤버 함수](../mfc/onidle-member-function.md) 메시지 루프의 작업 순서를 보여 줍니다.

메시지 디스패치 메시지의 종류에 따라 달라 집니다. 자세한 내용은 [프레임 워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)입니다.

## <a name="see-also"></a>참고자료

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)
