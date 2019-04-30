---
title: '클립보드: Windows 클립보드 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
ms.openlocfilehash: 49111e4efd2a12264d61030fe038d80b974514c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326991"
---
# <a name="clipboard-using-the-windows-clipboard"></a>클립보드: Windows 클립보드 사용

이 항목에는 MFC 응용 프로그램 내에서 표준 Windows 클립보드 API를 사용 하는 방법을 설명 합니다.

Windows에 대 한 대부분의 응용 프로그램에 잘라내기 또는 Windows 클립보드에 데이터를 복사 및 붙여넣기 클립보드의에서 데이터를 지원 합니다. 응용 프로그램 간에 클립보드 데이터 형식 달라 집니다. 프레임 워크 클래스 수가 제한에 대 한 제한 된 수의 클립보드 형식 지원합니다. 일반적으로 클립보드에 관련 된 명령 구현-잘라내기, 복사 및 붙여넣기-보기에 대 한 편집 메뉴. 클래스 라이브러리는 이러한 명령에 대 한 명령 Id를 정의 합니다. **ID_EDIT_CUT**, **ID_EDIT_COPY**, and **ID_EDIT_PASTE**. 해당 메시지 줄 프롬프트도 정의 합니다.

[프레임 워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md) 메뉴 명령 처리기 함수를 매핑하여 응용 프로그램에서 메뉴 명령을 처리 하는 방법에 설명 합니다. 응용 프로그램 편집 메뉴에서 클립보드 명령에 대 한 처리기 함수를 정의 하지 않습니다,으로 계속 사용 안 함. 잘라내기 및 복사 명령에 대 한 처리기 함수를 작성 하려면 응용 프로그램에서 선택 영역을 구현 합니다. Paste 명령에 대 한 처리기 함수를 작성 하려면 쿼리 클립보드 응용 프로그램에 응하기 서식의 데이터가 포함 되어 있는지 여부를 확인 합니다. 예를 들어 복사 명령을 사용 하려면 작성할 수 있습니다 처리기를 다음과 같이 합니다.

[!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]

잘라내기, 복사 및 붙여넣기 명령을 특정 컨텍스트에서 의미 있는 수만 있습니다. 잘라내기 및 복사 명령이 선택한 항목이 있으며만 있으면 붙여넣기 명령을 클립보드의 경우에 설정 되어야 합니다. 컨텍스트에 따라 이러한 명령을 사용할지 여부를 지정 하는 업데이트 처리기 함수를 정의 하 여이 동작을 제공할 수 있습니다. 자세한 내용은 [사용자 인터페이스 개체 업데이트 하는 방법](../mfc/how-to-update-user-interface-objects.md)합니다.

Microsoft Foundation Class 라이브러리는 텍스트를 사용한 편집에 대 한 클립보드 지원을 제공 합니다 `CEdit` 및 `CEditView` 클래스입니다. OLE 클래스는 또한 OLE 항목을 포함 하는 구현 클립보드 작업을 간소화 합니다. OLE 클래스에 대 한 자세한 내용은 참조 하세요. [클립보드: OLE 클립보드 메커니즘을 사용 하 여](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)입니다.

실행 취소 같은 메뉴 명령을 편집 다른 구현 (**ID_EDIT_UNDO**) 다시 실행 하 고 (**ID_EDIT_REDO**)에 그대로 있습니다. 응용 프로그램에 이러한 명령을 지원 하지 않습니다, 경우 쉽게 삭제할 수 있습니다 이러한 시각적 개체를 사용 하 여 리소스 파일에서 C++ 리소스 편집기입니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [데이터 복사 및 붙여넣기](../mfc/clipboard-copying-and-pasting-data.md)

- [OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

## <a name="see-also"></a>참고자료

[클립보드](../mfc/clipboard.md)
