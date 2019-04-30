---
title: 뷰를 통해 사용자 입력 해석
ms.date: 11/04/2016
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
ms.openlocfilehash: 3ef23ad74e1ff53d947453faa5682c5ecc1f4e43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310918"
---
# <a name="interpreting-user-input-through-a-view"></a>뷰를 통해 사용자 입력 해석

보기의 다른 멤버 함수를 처리 및 모든 사용자 입력 해석 합니다. 일반적으로 처리할 뷰 클래스의 메시지 처리기 멤버 함수를 정의 합니다.

- Windows [메시지](../mfc/messages.md) 마우스 및 키보드 작업에서 생성 합니다.

- [명령을](../mfc/user-interface-objects-and-command-ids.md) 메뉴, 도구 모음 단추 및 바로 가기 키입니다.

이러한 메시지 처리기 멤버 함수에서는 다음 작업으로 해석 데이터 입력, 선택 영역 또는 편집을 클립보드에서 데이터를 이동 하는 등:

- 마우스 움직임, 클릭, 끌기 및 두 번 클릭

- 키 입력

- 메뉴 명령

Windows 메시지 뷰에서 처리 응용 프로그램의 필요에 따라 달라 집니다.

[메시지 처리 및 매핑 항목](../mfc/message-handling-and-mapping.md) 명령에 메뉴 항목 및 기타 사용자 인터페이스 개체를 할당 하는 방법 및 명령 처리기 함수에 바인딩하는 방법에 설명 합니다. [메시지 처리 및 매핑 항목](../mfc/message-handling-and-mapping.md) 도 MFC 명령 라우트하는 방법을 설명 하 고 해당 처리기를 포함 하는 개체에 표준 Windows 메시지를 보냅니다.

예를 들어, 응용 프로그램 직접 마우스 뷰에서 그리기를 구현 해야 합니다. Scribble 샘플에는 시작, 계속 진행 한 그리기 선 세그먼트의 끝에 각각 WM_LBUTTONUP WM_LBUTTONDOWN 고 WM_MOUSEMOVE 메시지를 처리 하는 방법을 보여 줍니다. 반면에 선택 항목으로 보기에서 마우스 클릭을 해석 해야 경우가 있습니다. 보기의 `OnLButtonDown` 처리기 함수를 사용자 그리기 되었거나 선택 여부를 결정 합니다. 선택 하는 경우, 처리기를 결정 하는 보기에서 일부 개체의 경계 내에서 클릭 였는 지 여부 그리고 있다면, 선택된 된 개체를 표시 하도록 디스플레이가 변경 합니다.

보기는 잘라내기, 복사, 붙여넣기 또는 클립보드를 사용 하 여 선택한 데이터를 삭제 하려면 편집 메뉴에서 같은 특정 메뉴 명령을 처리할 수도 수 있습니다. 이러한 처리기는 함수를 호출할 클립보드와 관련 된 멤버의 일부 클래스의 `CWnd` 하거나 클립보드에서 선택한 데이터 항목을 전송 합니다.

## <a name="see-also"></a>참고자료

[뷰 사용](../mfc/using-views.md)
