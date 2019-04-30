---
title: 파일 닫기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 69a0960c1edabab00cb71702acda526ee9ebd798
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326926"
---
# <a name="closing-files"></a>파일 닫기

일반적으로 I/O 작업에서 파일을 마친 후 닫아야 합니다.

#### <a name="to-close-a-file"></a>파일을 닫으려면

1. 사용 된 **닫기** 멤버 함수입니다. 이 함수는 파일 시스템 파일을 닫고 필요한 경우 버퍼를 플러시합니다.

할당 한 경우는 [CFile](../mfc/reference/cfile-class.md) 프레임에서 개체 (에 표시 된 예제와 같이 [파일 열기](../mfc/opening-files.md)), 개체는 자동으로 닫히고 다음 범위를 벗어나면 제거 합니다. 해당 삭제를 확인 합니다 `CFile` 개체 파일 시스템에 물리적 파일을 삭제 되지 않습니다.

## <a name="see-also"></a>참고자료

[파일](../mfc/files-in-mfc.md)
