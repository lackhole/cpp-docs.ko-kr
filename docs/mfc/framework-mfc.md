---
title: 프레임워크(MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
ms.openlocfilehash: 933fcf97c24ed0903395e2c718f8c89d42473494
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219771"
---
# <a name="framework-mfc"></a>프레임워크(MFC)

Microsoft Foundation 클래스 (MFC) 라이브러리 프레임 워크를 사용 하 여 회사는 기반으로 몇 가지 주요 클래스 및 여러 시각적 개체 C++ 도구입니다. 일부 클래스는 Win32 API (응용 프로그래밍 인터페이스)의 많은 부분을 캡슐화합니다. 다른 클래스는 문서, 뷰 및 응용 프로그램 자체와 같은 응용 프로그램 개념을 캡슐화합니다. 여전히 다른 OLE 기능이 및 ODBC 및 DAO 데이터 액세스 기능 캡슐화합니다.

창의 Win32의 개념은 MFC 클래스에 의해 캡슐화 하는 예를 들어 `CWnd`합니다. 즉,를 C++ 라는 클래스 `CWnd` 캡슐화 또는 "래핑" 합니다 `HWND` Windows 창을 나타내는 핸들입니다. 마찬가지로 클래스 `CDialog` Win32 대화 상자를 캡슐화 합니다.

캡슐화 하는 것을 의미 합니다 C++ 클래스 `CWnd`, 예를 들어, 형식의 멤버 변수를 포함 `HWND`를 클래스의 멤버 함수는 Win32 함수에 대 한 호출을 캡슐화 하 고는 `HWND` 매개 변수로 합니다. 클래스 멤버 함수에는 일반적으로 캡슐화 하 여 Win32 함수 이름이 같은 경우

## <a name="in-this-section"></a>섹션 내용

[SDI 및 MDI](../mfc/sdi-and-mdi.md)

[문서, 뷰 및 프레임워크](../mfc/documents-views-and-the-framework.md)

[마법사 및 리소스 편집기](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>관련 섹션

[프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)

[프레임워크가 코드를 호출하는 방법](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: 애플리케이션 클래스](../mfc/cwinapp-the-application-class.md)

[문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)

[메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)

[창 개체](../mfc/window-objects.md)

## <a name="see-also"></a>참고자료

[클래스를 사용하여 Windows 애플리케이션 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
