---
title: 문서 사용
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
ms.openlocfilehash: fb35d1731912b2e322bc61621f7900e0d98e1e72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411593"
---
# <a name="using-documents"></a>문서 사용

문서 및 뷰를 공동으로 작업 합니다.

- 포함, 관리 및 응용 프로그램별 표시할 [데이터](../mfc/managing-data-with-document-data-variables.md)입니다.

- 구성 된 인터페이스를 제공 [데이터 변수 문서](../mfc/managing-data-with-document-data-variables.md) 데이터 조작에 대 한 합니다.

- 참여할 [파일을 읽고 쓰는](../mfc/serializing-data-to-and-from-files.md)합니다.

- 참여할 [인쇄](../mfc/role-of-the-view-in-printing.md)합니다.

- [처리](../mfc/handling-commands-in-the-document.md) 대부분의 응용 프로그램의 명령 및 메시지입니다.

특히 데이터 관리와 관련 된 문서가 있습니다. 문서 클래스 멤버 변수에서 일반적으로 데이터를 저장 합니다. 보기 표시에 대 한 데이터를 액세스 하 고 업데이트할 이러한 변수를 사용 합니다. 문서의 기본 serialization 메커니즘에는 데이터 읽기 및 쓰기를 파일로 / 파일에서 관리 합니다. 명령 (하지만 WM_COMMAND 이외의 Windows 메시지가 없는) 문서를 처리할 수도 있습니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [CDocument에서 문서 클래스 파생 시키기](../mfc/deriving-a-document-class-from-cdocument.md)

- [문서 데이터 변수로 데이터 관리](../mfc/managing-data-with-document-data-variables.md)

- [파일로 / 파일에서 데이터를 직렬화 하는 작업](../mfc/serializing-data-to-and-from-files.md)

- [Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)

- [문서에서 명령 처리](../mfc/handling-commands-in-the-document.md)

- [OnNewDocument 멤버 함수](../mfc/reference/cdocument-class.md#onnewdocument)

- [DeleteContents 멤버 함수](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>참고자료

[문서/뷰 아키텍처](../mfc/document-view-architecture.md)
