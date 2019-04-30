---
title: 창 메모리 할당 및 할당 취소
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: 60f99c01c7a311c31602269b49efaf434d16827a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394704"
---
# <a name="allocating-and-deallocating-window-memory"></a>창 메모리 할당 및 할당 취소

사용 하지 마십시오는 C++ **삭제할** 프레임 창 또는 보기를 제거 하는 연산자입니다. 대신, 호출 된 `CWnd` 멤버 함수 `DestroyWindow`합니다. 프레임 창 따라서 할당 되는 연산자를 사용 하 여 힙에 **새**합니다. 프레임 창 또는 전역 스택 프레임에 할당할 때 주의 해야 합니다. 다른 windows 가능 하면 스택 프레임에 할당 되어야 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [창 만들기](../mfc/creating-windows.md)

- [창 소멸 시퀀스](../mfc/window-destruction-sequence.md)

- [해당 HWND에서에서 CWnd 분리](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>참고자료

[창 개체 제거](../mfc/destroying-window-objects.md)
