---
title: 창 개체 소멸시키기
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: f50d198f9868a70d25370f6c1399b66efaa5490b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297244"
---
# <a name="destroying-window-objects"></a>창 개체 소멸시키기

제거할 고유한 자식 창으로 주의 기울여 수는 C++ 창을 사용 하 여 사용자가 완료 될 때 창 개체입니다. 이러한 개체를 소멸 되지 않습니다 하는 경우 응용 프로그램의 메모리를 복구 되지 않습니다. 다행 스럽게도 프레임 워크는 프레임 창, 뷰 및 대화 상자에 대 한 작성 뿐만 아니라 창 소멸을 관리합니다. 추가 windows를 만든 있다면 제거 하는 일을 담당 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [창 소멸 시퀀스](../mfc/window-destruction-sequence.md)

- [할당 및 창 메모리 할당 취소](../mfc/allocating-and-deallocating-window-memory.md)

- [해당 HWND에서에서 CWnd 분리](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [일반 창 만들기 시퀀스](../mfc/general-window-creation-sequence.md)

- [프레임 창 제거](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>참고자료

[창 개체](../mfc/window-objects.md)
