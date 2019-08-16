---
title: 메모리 관리
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
ms.openlocfilehash: 5d81bd0a8bdd24059951cba5c8b69751b3d1db86
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508266"
---
# <a name="memory-management"></a>메모리 관리

다음의 항목들을 통하여 메모리 관리와 관련된 MFC(Microsoft Foundation Class Library)의 일반 서비스를 활용하는 방법에 대해 설명합니다. 메모리 할당은 프레임 할당과 힙 할당의 두 가지 주요 범주로 나눌 수 있습니다.

두 할당 기술의 큰 차이점 중 하나는 프레임 할당을 사용하면 일반적으로 실제 메모리 블록 자체에서 작업하는 반면 힙 할당에서는 항상 메모리 블록에 대한 포인터가 제공된다는 것입니다. 두 스키마의 또 다른 주요 차이점은 프레임 객체가 자동으로 삭제되는 반면 힙 객체는 프로그래머가 명시적으로 삭제해야 한다는 것입니다.

MFC를 사용하지 않는 Windows용 프로그램의 메모리 관리에 대한 정보는 Windows SDK의 [메모리 관리](/windows/win32/memory/memory-management)를 참조하십시오.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [프레임 할당](../mfc/memory-management-frame-allocation.md)

- [힙 할당](../mfc/memory-management-heap-allocation.md)

- [배열에 대한 메모리 할당](../mfc/memory-management-examples.md)

- [힙에서 배열에 대한 메모리 할당 해제](../mfc/memory-management-examples.md)

- [데이터 구조에 대한 메모리 할당](../mfc/memory-management-examples.md)

- [개체에 대한 메모리 할당](../mfc/memory-management-examples.md)

- [크기 조정 가능한 메모리 블록](../mfc/memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>참고자료

[개념](../mfc/mfc-concepts.md)<br/>
[일반 MFC 항목](../mfc/general-mfc-topics.md)
