---
title: 문서 및 뷰 초기화 및 정리
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
ms.openlocfilehash: 59e86f4000e2da588749ca48887d34c3effdfc3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297192"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>문서 및 뷰 초기화 및 정리

초기화 하 고 문서 및 뷰 정리에 대 한 다음 지침을 따르세요.

- MFC 프레임 워크 문서 및 뷰;를 초기화합니다. 에 추가 하는 모든 데이터를 초기화 합니다.

- 프레임 워크를 문서로 정리 하 고 뷰를 닫습니다. 해당 문서 및 뷰 멤버 함수 내에서 힙의 할당 메모리 할당을 취소 해야 합니다.

> [!NOTE]
>  전체 응용 프로그램의 재정의에서 가장 잘 수행 되며에 대 한 해당 초기화를 회수 합니다 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 클래스의 멤버 함수 `CWinApp`, 전체 응용 프로그램에 대 한 정리 합니다 의재정의에서가장잘수행되며및`CWinApp`멤버 함수 [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)합니다.

수명 주기의 문서 (및 해당 프레임 창 및 보기 또는 뷰)는 mdi에서 응용 프로그램은 다음과 같습니다.

1. 동적 생성 하는 동안 문서 생성자가 호출 됩니다.

1. 각 새 문서를 문서에 대 한 [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) 하거나 [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) 라고 합니다.

1. 해당 수명 주기 동안 문서를 사용 하 여 사용자 상호 작용합니다. 일반적으로이 따라 선택 하 고 데이터를 편집 보기를 통해 문서 데이터를 지속적으로 발생 합니다. 뷰는 문서 저장소 및 다른 뷰를 업데이트 하는 중에 변경 내용을 전달 합니다. 이 시간 동안 문서 및 뷰는 명령을 처리할 수 있습니다.

1. 프레임 워크 호출 [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) 문서에 특정 데이터를 삭제 합니다.

1. 문서의 소멸자가 호출 됩니다.

SDI 응용 프로그램에서는 1 단계 문서를 처음 만들 때 한 번 수행 됩니다. 그런 다음 2 ~ 4 단계 반복 하 여 수행 새 문서를 열 때마다 합니다. 새 문서가 기존 문서 개체를 다시 사용합니다. 마지막으로, 응용 프로그램이 종료 되 면 5 단계를 수행 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [문서 및 뷰 초기화](../mfc/initializing-documents-and-views.md)

- [문서 및 뷰 정리](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>참고자료

[문서/뷰 아키텍처](../mfc/document-view-architecture.md)
