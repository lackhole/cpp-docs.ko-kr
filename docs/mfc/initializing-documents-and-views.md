---
title: 문서 및 뷰 초기화
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
ms.openlocfilehash: 0cf9faecbb7e0d74c2199a1a829aa68241e1c019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297114"
---
# <a name="initializing-documents-and-views"></a>문서 및 뷰 초기화

문서 두 가지 방법으로 만들어지므로 문서 클래스에는 두 가지 방법을 모두 지원 해야 합니다. 먼저 사용자 새 파일 명령을 사용 하 여 새 빈 문서를 만들 수 있습니다. 이 경우의 재정의에서 문서를 초기화 합니다 [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) 클래스의 멤버 함수 [CDocument](../mfc/reference/cdocument-class.md)합니다. 둘째, 사용자 파일에서 읽은 내용을 새 문서를 만들려면 파일 메뉴에서 열기 명령을 사용할 수 있습니다. 이 경우의 재정의에서 문서를 초기화 합니다 [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) 클래스의 멤버 함수 `CDocument`합니다. 모두 초기화가 동일한 경우 두 재정의에서 공용 멤버 함수를 호출할 수 있습니다 또는 `OnOpenDocument` 호출할 수 있습니다 `OnNewDocument` 정리 문서를 초기화 하 여 다음 열기 작업을 완료 합니다.

뷰는 해당 문서를 만든 후에 생성 됩니다. 뷰를 초기화 하려면 가장 좋은 시간은 프레임 워크에서 문서, 프레임 창 및 뷰 만들기를 완료 한 후입니다. 재정의 하 여 보기를 초기화할 수 있습니다 합니다 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 멤버 함수 [CView](../mfc/reference/cview-class.md)합니다. 문서 변경 될 때마다 다시 초기화 하거나 아무 것도 조정 해야 할 경우, 재정의할 수 있습니다 [OnUpdate](../mfc/reference/cview-class.md#onupdate)합니다.

## <a name="see-also"></a>참고자료

[문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)
