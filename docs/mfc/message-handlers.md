---
title: 메시지 처리기
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
ms.openlocfilehash: 0d3ed6239b638a0e161cd7e3580f4fe6e1b4a7e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383765"
---
# <a name="message-handlers"></a>메시지 처리기

Mfc에서 전용 *처리기* 함수는 각 메시지를 처리 합니다. 메시지 처리기 함수는 클래스의 멤버 함수입니다. 이 설명서에서는 용어 *메시지 처리기 멤버 함수*, *메시지 처리기 함수*합니다 *메시지 처리기*, 및 *처리기*서로 교환 합니다. 일부 종류의 메시지 처리기에는 "명령 처리기입니다." 이라고 합니다.

회사의 상당한 부분에 대 한 메시지 처리기 계정을 작성 framework 응용 프로그램을 작성 합니다. 이 문서에서는 메시지 처리 메커니즘의 작동 방식을 설명 합니다.

메시지에 대 한 처리기를 설정 하는 것이 용도 대 한 응답 메시지에는 수행 하려는 모든 않습니다. 클래스의 속성 창을 사용 하 여 처리기를 만들 수 있으며 소스 코드 편집기를 사용 하 여 처리기의 코드를 채웁니다.

모든 Microsoft 시각적 개체의 기능을 사용할 수 있습니다 C++ 및 MFC 처리기를 작성 합니다. 모든 클래스의 목록을 참조 하세요 [클래스 라이브러리 개요](../mfc/class-library-overview.md) 에 *MFC 참조*합니다.

## <a name="see-also"></a>참고자료

[프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)
