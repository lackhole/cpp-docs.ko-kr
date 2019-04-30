---
title: 표준 명령 라우팅 재정의
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
ms.openlocfilehash: 5383c1053894d44e23baf51b19ac3df4e60158e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410163"
---
# <a name="overriding-the-standard-command-routing"></a>표준 명령 라우팅 재정의

드문 경우에서 라우팅 표준 프레임 워크의 일부 변형을 구현 해야 하는 경우 재정의할 수 있습니다. 재정의 하 여 하나 이상의 클래스의 라우팅을 변경 하는 개념은 `OnCmdMsg` 해당 클래스에 있습니다. 이 수행 합니다.

- 기본이 아닌 개체에 전달 하는 순서를 무시 하는 클래스입니다.

- 새 기본이 아닌 개체에서 또는 명령 대상에서이 수에 명령을 전달할 합니다.

라우팅에 일부 새 개체를 삽입 하면 해당 클래스는 명령 대상 클래스 여야 합니다. 재정의 버전에서 `OnCmdMsg`를 재정의 하는 버전을 호출 해야 합니다. 참조를 [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg) 클래스의 멤버 함수 `CCmdTarget` 에 *MFC 참조* 와 같은 클래스의 버전 `CView` 및 `CDocument` 예제에 대 한 제공 된 소스 코드에서.

## <a name="see-also"></a>참고자료

[프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)
