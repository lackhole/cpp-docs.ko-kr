---
title: 프레임워크가 코드를 호출하는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
ms.openlocfilehash: 81b0749167391a841badff5494023a2ca5d3147e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407954"
---
# <a name="how-the-framework-calls-your-code"></a>프레임워크가 코드를 호출하는 방법

것 MFC 프레임 워크의 코드와 소스 코드 간의 관계를 이해 하는 데 중요 합니다. 응용 프로그램을 실행 하는 경우 대부분의 제어 흐름의 프레임 워크의 코드에 상주 합니다. 프레임 워크 사용자 명령을 선택 하 고 보기에서 데이터를 편집 하는 대로 Windows에서 메시지를 가져오는 메시지 루프를 관리 합니다. 프레임 워크는 자체적으로 처리할 수 있는 이벤트 전혀 코드에 의존 하지 않습니다. 예를 들어, 프레임 워크에는 windows를 종결 하는 방법 및 사용자 명령에 대 한 응답으로 응용 프로그램을 종료 하는 방법을 알고 있습니다. 메시지 처리기 프레임 워크를 사용 하 여 이러한 작업을 처리 하므로 및 C++ 에서도 이러한 이벤트에 응답할 수 있는 기회를 제공 하는 가상 함수입니다. 그러나 컨트롤에 없는 코드를 프레임 워크가입니다.

프레임 워크는 응용 프로그램 관련 이벤트에 대 한 코드를 호출합니다. 예를 들어 사용자가 메뉴 명령을 선택, 프레임 워크의 시퀀스를 따라 명령을 라우팅합니다 C++ 개체: 현재 뷰 및 프레임 창, 뷰, 문서의 문서 템플릿 및 응용 프로그램 개체와 연결 된 문서입니다. 명령을 처리할 수 있는 이러한 개체 중 하나 그렇게 되 면이 적절 한 메시지 처리기 함수를 호출 합니다. 지정 된 모든 명령에 대 한 호출 코드 일 수도 있고 프레임 워크의 수도 있습니다.

이 정렬은 Windows에 대 한 기존의 프로그래밍 또는 이벤트 구동 프로그래밍에 익숙한 프로그래머에 게 어느 정도 알고 있습니다.

관련된 항목에서 어떤 프레임 워크를 초기화 되는 응용 프로그램을 실행 및 정리 응용 프로그램이 종료 설명 합니다. 작성 하는 코드 적합 한 위치를 이해할 수 있습니다.

자세한 내용은 참조 하세요. [클래스 CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md) 하 고 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)합니다.

## <a name="see-also"></a>참고자료

[프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)
