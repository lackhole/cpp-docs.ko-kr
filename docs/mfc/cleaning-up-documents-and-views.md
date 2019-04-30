---
title: 문서 및 뷰 정리
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 940c768823d26950d9710fb1d1a52e6a1955fead
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327160"
---
# <a name="cleaning-up-documents-and-views"></a>문서 및 뷰 정리

프레임 워크를 먼저 호출 문서를 닫을 때 해당 [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) 멤버 함수입니다. 문서 작업 중 힙에서 메모리를 할당한 경우 메모리를 할당 해제하기에 가장 좋은 위치는 `DeleteContents`입니다.

> [!NOTE]
>  문서의 소멸자에서는 문서 데이터를 할당 해제하지 않아야 합니다. SDI 응용 프로그램의 경우 문서 개체를 다시 사용할 수 있습니다.

힙에 할당한 메모리를 할당 해제하도록 뷰의 소멸자를 재정의할 수 있습니다.

## <a name="see-also"></a>참고자료

[문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)
