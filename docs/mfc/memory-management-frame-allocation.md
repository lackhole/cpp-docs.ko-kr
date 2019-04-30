---
title: '메모리 관리: 프레임 할당'
ms.date: 11/04/2016
helpviewer_keywords:
- memory leaks [MFC], frame allocation
- memory [MFC], detecting leaks
- memory [MFC], reclaiming
- memory allocation [MFC], frames
- frame variables [MFC], automatic deletion of
- scope [MFC], frame variables
- heap allocation [MFC], vs. frame allocation
- variables [MFC], frame variables
- memory leaks [MFC], detecting
- memory, releasing [MFC]
- stack frames [MFC]
- memory leaks [MFC], allocating objects on the frame
- detecting memory leaks [MFC]
- frame allocation [MFC]
- frame variables [MFC]
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
ms.openlocfilehash: 1acf2ce89e18dd64c166103b59b5eb7007214efd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352129"
---
# <a name="memory-management-frame-allocation"></a>메모리 관리: 프레임 할당

프레임 할당 설정 된 "스택 프레임"의 이름을 가져옵니다 때마다 함수를 호출 합니다. 스택 프레임에 임시로 보관 하는 인수를 함수 뿐만 아니라 정의 된 모든 변수가 함수에 로컬 메모리 영역입니다. 프레임 변수가 컴파일러에 자동으로 공간을 할당 하기 때문에 "automatic" 변수 라고도 합니다.

프레임 할당의 주요 특징을 두 가지입니다. 먼저 지역 변수를 정의할 때 충분 한 공간이 할당 됩니다 전체 변수를 포함 하는 스택 프레임 인 경우라도 큰 배열이 나 데이터 구조입니다. 둘째, 프레임 변수가 범위를 벗어날 때 자동으로 삭제 됩니다.

[!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]

로컬 함수 변수에 대 한 중첩 된 중괄호를 사용 하는 경우 프레임 변수의 범위를 제외한 함수가 종료 되는 함수 보다 작을 수 있습니다이 범위 전환을 발생 합니다. 프레임 변수의 자동 삭제 하는 것이 매우 중요 합니다. 간단한 기본 형식의 경우 (같은 **int** 또는 **바이트**), 배열 또는 데이터 구조를 자동으로 삭제할 변수로 사용 하는 메모리를 간단 하 게 회수 합니다. 변수의 범위를 벗어난, 이후 계속 액세스할 수 없습니다. 경우 C++ 개체는 프로세스를 자동으로 삭제할 것 인데, 조금 더 복잡 합니다.

프레임 변수 개체를 정의할 때 해당 생성자 정의 발생 지점에 자동으로 호출 됩니다. 개체가 범위를 벗어나면 개체에 대 한 메모리를 회수 하기 전에 해당 소멸자가 자동으로 호출 됩니다. 자동 생성 및 소멸이 매우 유용한 수 있지만 특히 소멸자를 자동 호출을 알고 있어야 합니다.

자동으로 삭제는 하는 프레임에서 개체를 할당 하는 이점이 있습니다. 프레임에서 개체를 할당 하면 메모리 누수를 일으키는 잊어버린된 개체에 걱정할 필요가 없습니다. (메모리 누수에 대 한 내용은 문서 참조 [MFC의 메모리 누수 탐지](/previous-versions/visualstudio/visual-studio-2010/c99kz476(v=vs.100)).) 프레임 할당의 단점은 범위 밖 프레임 변수를 사용할 수 없습니다. 프레임 할당과 힙 할당을 선택 하는 다른 요소 있다는 것 큰 구조와 개체에 대 한 자주 스택 공간이 제한 된 경우가 있으므로 저장소에 대 한 힙의 스택 대신 사용 하 여 합니다.

## <a name="see-also"></a>참고자료

[메모리 관리](../mfc/memory-management.md)
