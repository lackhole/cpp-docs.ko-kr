---
title: MFC의 MAPI 지원
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: 9b873ca1b3384adab6487fb3af9dc1401aaad12c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225530"
---
# <a name="mapi-support-in-mfc"></a>MFC의 MAPI 지원

MFC의는 Microsoft 응용 프로그램 프로그램 인터페이스 MAPI (메시징) 클래스의 하위 집합에 대 한 지원을 제공 `CDocument`합니다. 특히 `CDocument` 메일 지원 최종 사용자의 컴퓨터에 있는지 여부를 결정 하는 멤버 함수 있고 그렇다면 표준 명령 ID가 ID_FILE_SEND_MAIL 메일 보내기 명령을 사용 합니다. 이 명령에 대 한 MFC 처리기 함수에는 사용자를 전자 메일을 통해 문서를 보낼 수 있습니다.

> [!TIP]
>  MFC는 전체 MAPI 함수 집합을 캡슐화 하지 않는, 하지만 여전히 함수를 호출할 수 MAPI를 직접 대로 MFC 프로그램에서 직접 Win32 API 함수를 호출할 수 있습니다.

메일 보내기 응용 프로그램에서 명령을 매우 쉽습니다. MFC 문서 패키지 구현을 제공 (즉,는 `CDocument`-파생 개체) 첨부 파일로 메일을 보냅니다. 이 첨부 파일 저장 하는 파일 저장 명령을 같습니다 (serialize) 메일 메시지에 문서의 내용입니다. 이 구현 시 사용자에 게 메일 주소를 메일 메시지에 제목 및 메시지 텍스트를 추가할 수 있는 기회를 제공 하는 사용자의 컴퓨터에서 메일 클라이언트를 호출 합니다. 사용자가 친숙 한 메일 응용 프로그램의 사용자 인터페이스를 참조 하세요. 이 기능은 2로 제공 됩니다 `CDocument` 멤버 함수: `OnFileSendMail` 고 `OnUpdateFileSendMail`입니다.

MAPI 첨부 파일을 전송할 파일을 읽는 데 필요 합니다. 응용 프로그램은 해당 데이터 파일 중에 열려 있는 경우는 `OnFileSendMail` 함수 호출에서 여러 프로세스 파일에 액세스할 수 있도록 하는 공유 모드를 사용 하 여 열려 파일 있어야 합니다.

> [!NOTE]
>  재정의 된 버전의 `OnFileSendMail` 클래스에 대 한 `COleDocument` 올바르게 처리 복합 문서입니다.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>MFC 사용 하 여 메일 보내기 명령을 구현 하려면

1. 시각적 개체를 사용 하 여 C++ 명령 ID가 ID_FILE_SEND_MAIL 메뉴 항목을 추가 하려면 메뉴 편집기입니다.

   이 명령은 ID AFXRES에서 프레임 워크에서 제공 됩니다. 8. 모든 메뉴에 명령을 추가할 수 있지만 일반적으로 추가 됩니다는 **파일** 메뉴.

1. 문서 메시지 맵에 다음 수동으로 추가 합니다.

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  이 메시지 맵 중 하나에서 파생 된 문서에 대해 작동 `CDocument` 또는 `COleDocument` -메시지 맵에서 파생된 문서 클래스에는 두 경우 모두 올바른 기본 클래스를 선택 합니다.

1. 응용 프로그램을 빌드하십시오.

MFC 사용 하 여 메뉴 항목을 사용 하면 전자 메일 서비스를 사용할 수 있는 경우 `OnUpdateFileSendMail` 이후에 사용 하 여 명령을 처리 하 고 `OnFileSendMail`입니다. 전자 메일 서비스를 사용할 수 없는 경우 MFC 자동으로 메뉴 항목을 제거 되므로 사용자에 게는 표시 되지 않습니다.

> [!TIP]
>  앞에서 설명한 대로 메시지 맵 항목에 수동으로 추가 하는 대신 함수에 메시지를 매핑할 클래스의 속성 창을 사용할 수 있습니다. 자세한 내용은 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.

관련된 정보에 대 한 참조를 [MAPI](../mfc/mapi.md) 개요.

에 대 한 자세한 내용은 `CDocument` MAPI를 사용 하도록 설정 하는 멤버 함수를 참조 하세요.

- [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>참고자료

[MAPI](../mfc/mapi.md)
