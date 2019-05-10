---
title: 파일 열기
ms.date: 11/04/2016
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
ms.openlocfilehash: dab7a680d9b33a6e334da99a045b709fe00f215c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394483"
---
# <a name="opening-files"></a>파일 열기

MFC에서 파일을 여는 가장 일반적인 방법은 2 단계 프로세스입니다.

#### <a name="to-open-a-file"></a>파일을 열려면

1. 경로 또는 사용 권한 플래그를 지정 하지 않고 파일 개체를 만듭니다.

   일반적으로 선언 하 여 파일 개체를 만듭니다는 [CFile](../mfc/reference/cfile-class.md) 스택 프레임에서 변수입니다.

1. 호출 된 [열려](../mfc/reference/cfile-class.md#open) 경로 및 사용 권한 플래그를 제공 하 여 파일 개체에 대 한 멤버 함수입니다.

   반환 값은 `Open` 파일을 성공적으로 연 경우에 0이 아니거나 0 될 지정된 된 파일을 열 수 없는 경우. `Open` 멤버 함수는 프로토타입 다음과 같습니다.

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   열기 플래그는 권한을 지정 합니다와 같은 파일에 대해 원하는 읽기 전용입니다. 가능한 플래그 값 내에서 열거 된 상수로 정의 됩니다 합니다 `CFile` 클래스를 사용 하 여 정규화 되므로 "`CFile::`"에서 같이 `CFile::modeRead`합니다. 사용 된 `CFile::modeCreate` 파일을 만들려는 경우 플래그입니다.

다음 예에서는 읽기/쓰기 권한 (동일한 경로 사용 하 여 이전 파일을 교체)를 사용 하 여 새 파일을 만드는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
>  이 예에서는 만들고 파일을 엽니다. 문제가 있는 경우는 `Open` 호출이 반환을 `CFileException` 다음과 같이 마지막 매개 변수인 개체입니다. TRACE 매크로 파일 이름 및 실패 이유를 나타내는 코드를 인쇄 합니다. 호출할 수 있습니다는 `AfxThrowFileException` 자세한 내용을 보려면 오류 보고 해야 하는 경우 작동 합니다.

## <a name="see-also"></a>참고자료

[CFile 클래스](../mfc/reference/cfile-class.md)<br/>
[CFile::Open](../mfc/reference/cfile-class.md#open)<br/>
[파일](../mfc/files-in-mfc.md)
