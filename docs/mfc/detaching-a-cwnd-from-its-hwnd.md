---
title: CWnd를 해당 HWND에서 분리
ms.date: 11/04/2016
f1_keywords:
- CWnd
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: 259af94958f88643e9c3ce725b25c4e92cc38226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394574"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd를 해당 HWND에서 분리

개체-우회 해야 할 경우`HWND` 관계, MFC를 통해 다른 `CWnd` 멤버 함수 [분리](../mfc/reference/cwnd-class.md#detach), 연결을 끊는 합니다 C++ 창 개체 Windows 창에서. 이 개체가 소멸 될 때 Windows 창을 제거에서 소멸자를 방지 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [창 만들기](../mfc/creating-windows.md)

- [창 소멸 시퀀스](../mfc/window-destruction-sequence.md)

- [할당 및 창 메모리 할당 취소](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>참고자료

[창 개체](../mfc/window-objects.md)
