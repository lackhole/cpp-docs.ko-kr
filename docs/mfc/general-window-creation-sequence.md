---
title: 일반 창 만들기 시퀀스
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 949cf72910654b502ca4b57be72bedc2db63c315
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219568"
---
# <a name="general-window-creation-sequence"></a>일반 창 만들기 시퀀스

설명 하는 동일한 프로세스를 훨씬 프레임 워크에는 자식 같은 고유한 창 기간을 만들면 [문서/뷰 만들기](../mfc/document-view-creation.md)합니다.

MFC 사용에서 제공 하는 모든 창 클래스 [2 단계 생성](../mfc/one-stage-and-two-stage-construction-of-objects.md)합니다. 즉, 호출 하는 동안는 C++ **새** 연산자 생성자를 할당 및 초기화를 C++ 개체 하지만 해당 Windows 창을 만들지는 않습니다. 호출 하 여 나중에 수행 되는 합니다 [만들기](../mfc/reference/cwnd-class.md#create) 창 개체의 멤버 함수입니다.

합니다 `Create` 멤버 함수는 Windows 창을 가져와 해당 `HWND` 에 C++ 개체의 공용 데이터 멤버 [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)합니다. `Create` 제공 된 생성 매개 변수를 통해 유연성을 완료합니다. 호출 하기 전에 `Create`, 전역 함수를 사용 하 여 창 클래스를 등록 하려는 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하려면.

프레임 창에 사용할 수 있습니다 합니다 [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 멤버 함수 대신 `Create`합니다. `LoadFrame` 더 적은 매개 변수를 사용 하 여 Windows 창을으로 열립니다. 프레임의 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 대부분의 기본값을 가져옵니다.

> [!NOTE]
>  프로그램 아이콘, 액셀러레이터 키 테이블 및 메뉴 리소스 ID가 있어야 일반적인 리소스와 같은 **IDR_MAINFRAME**, LoadFrame에 로드할 수 있도록 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [창 개체](../mfc/window-objects.md)

- [창 "classes"를 등록합니다.](../mfc/registering-window-classes.md)

- [창 개체 제거](../mfc/destroying-window-objects.md)

- [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>참고자료

[창 만들기](../mfc/creating-windows.md)
