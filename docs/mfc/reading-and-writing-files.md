---
title: 파일 읽기 및 쓰기
ms.date: 11/04/2016
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
ms.openlocfilehash: ab1ddc58ec6cc2b67e5843f46afbead3ead54eba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324261"
---
# <a name="reading-and-writing-files"></a>파일 읽기 및 쓰기

C 런타임 라이브러리 파일 처리 함수를 사용한 경우에 MFC 읽기 및 쓰기 작업 친숙 한 표시 됩니다. 이 문서에서는 설명에서 직접 읽고에 직접 작성 한 `CFile` 개체입니다. 있습니다 수 또한 수행 버퍼링 파일 I/O에는 [CArchive](../mfc/reference/carchive-class.md) 클래스입니다.

#### <a name="to-read-from-and-write-to-the-file"></a>읽고 파일에 쓸

1. 사용 된 `Read` 및 `Write` 읽고 파일에 데이터를 작성 하는 멤버 함수입니다.

     또는

1. `Seek` 멤버 함수는 또한 파일 내에서 특정 오프셋으로 이동 하는 데 사용할 수 있습니다.

`Read` 읽을 바이트 수와 버퍼에 대 한 포인터를 사용 하 고 실제 읽은 바이트 수를 반환 합니다. 필요한 바이트 수를 읽을 수 없습니다 때문에 파일의 끝 (EOF)에 도달한 경우 실제 읽은 바이트 수가 반환 됩니다. 읽기 오류가 발생 하면 예외가 throw 됩니다. `Write` 비슷합니다 `Read`, 있지만 쓴 바이트 수가 반환 되지 않습니다. 지정 된 모든 바이트를 작성 하지 포함 하 여 쓰기 오류가 발생 하면 예외가 throw 됩니다. 유효한 경우 `CFile` 개체에서 읽거나 쓸 다음 예와에서 같이 수 있습니다.

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
>  입/출력 작업 내에서 정상적으로 수행 해야 하는 **시도**/**catch** 예외 처리 블록입니다. 자세한 내용은 [예외 처리 (MFC)](../mfc/exception-handling-in-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[파일](../mfc/files-in-mfc.md)
