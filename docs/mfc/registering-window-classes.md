---
title: 창 클래스 등록
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: 7c459b909a60fff2b7aeded9ea8d79a39ced24e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309085"
---
# <a name="registering-window-classes"></a>창 클래스 등록

"클래스"의 특성을 정의 하는 Windows에 대 한 일반적인 프로그래밍의 "classes" 창 (없습니다는 C++ 클래스)에서 임의 개수의 windows 만들 수 있습니다는. 이러한 종류의 클래스는 템플릿 또는 windows를 만들기 위한 모델.

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows에 대 한 기존 프로그램에서 창 클래스 등록

MFC 없이 Windows에 대 한 기존 프로그램에서 자체 "창 프로시저"에서 창에 모든 메시지를 처리 하거나 "`WndProc`." `WndProc` "창 클래스 등록" 프로세스를 사용 하 여 창에 연결 됩니다. 주 창에 등록 되는 `WinMain` 함수 하지만 windows의 다른 클래스에에서 등록할 수 있습니다 어디서 나 응용 프로그램입니다. 등록에 대 한 포인터를 포함 하는 구조에 따라 달라 집니다는 `WndProc` 배경 브러시 커서에 대 한 사양을 함께 함수 및 등입니다. 구조에 대 한 이전 호출에서 클래스의 문자열 이름 함께 매개 변수로 전달 되는 `RegisterClass` 함수입니다. 따라서 등록 클래스는 여러 windows에서 공유할 수 있습니다.

## <a name="window-class-registration-in-mfc-programs"></a>MFC 프로그램의 창 클래스 등록

반면, 대부분의 창 클래스 등록 작업은 MFC 프레임 워크 프로그램에서 자동으로 수행 됩니다. MFC를 사용 하는 경우 일반적으로 파생 되는 C++ 창 클래스는 보통을 사용 하 여 기존 라이브러리 클래스에서 C++ 클래스 상속에 대 한 구문입니다. 프레임 워크는 여전히 기존 사용 "등록 클래스" 하며 필요한 경우에 등록 하는 몇 표준 도구를 제공 합니다. 호출 하 여 추가 등록 클래스를 등록할 수 있습니다 합니다 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 전역 함수 및 등록 된 클래스를 전달 합니다 `Create` 멤버 함수 `CWnd`합니다. 여기에서 설명한 대로, 기존의 Windows에서 "등록 class"를 않습니다 혼동을 C++ 클래스.

자세한 내용은 [기술 참고 1](../mfc/tn001-window-class-registration.md)합니다.

## <a name="see-also"></a>참고자료

[창 만들기](../mfc/creating-windows.md)
