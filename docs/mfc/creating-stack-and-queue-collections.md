---
title: 스택 및 큐 컬렉션 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC collection classes [MFC], stack collections
- collections, stack
- stack
- collection classes [MFC], creating
- queue collections
- MFC collection classes [MFC], queue collections
- stack collections
- collections, queue
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
ms.openlocfilehash: ed0ad9b98a69e56df4e66b25bc6ca08cdaaad413
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242408"
---
# <a name="creating-stack-and-queue-collections"></a>스택 및 큐 컬렉션 만들기

이 문서와 같은 기타 데이터 구조를 만드는 방법에 설명 [스택을](#_core_stacks) 하 고 [큐](#_core_queues), MFC에서 클래스를 나열 합니다. 예제에서 파생 된 클래스를 사용 `CList`를 사용할 수 있지만 `CList` 직접 기능을 추가 해야 합니다.

##  <a name="_core_stacks"></a> 스택

표준 목록 컬렉션 head와 꼬리 있으므로 마지막의 선입 선출 스택의 동작을 모방 하는 파생 된 목록 컬렉션을 만드는 쉽습니다. 스택 식당에는 접시 더미와 같습니다. 트레이 스택에 추가 되 면 스택 맨 위에 이동 합니다. 추가할 마지막 트레이 제거할 첫 번째입니다. 목록 컬렉션 멤버 함수도 `AddHead` 고 `RemoveHead` 사용 하 여 추가할 수 있습니다 하 고 특히 목록 헤드에서에서 요소를 제거 합니다. 즉, 가장 최근에 추가 된 요소는 제거 될 첫 번째입니다.

#### <a name="to-create-a-stack-collection"></a>스택 컬렉션을 만들려면

1. 기존 MFC 목록 클래스 중 하나에서 새 목록 클래스를 파생 하 고 스택 작업의 기능을 지원 하기 위해 더 많은 멤버 함수를 추가 합니다.

   다음 예제에서는 요소 스택의 맨 위에 있는 요소를 미리 보고 하면 스택에 푸시 및 스택의 맨 위에 있는 요소를 팝 하는 멤버 함수를 추가 하는 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

이 방법은 기본 표시는 `CObList` 클래스입니다. 호출할 수 `CObList` 멤버 함수를 있는지 여부는 스택에 대 한 것이 좋습니다.

##  <a name="_core_queues"></a> 큐

표준 목록 컬렉션 head와 꼬리 있어 쉽게 선입 선출 큐의 동작을 모방 하는 파생 된 목록 컬렉션을 만들 수 이기도 합니다. 큐 식당의 줄과 같습니다. 줄에서 첫 번째 사람은 제공 될 첫 번째 멤버입니다. 사람들이 더 많이으로 순서를 대기 하는 줄의 끝으로 이동 합니다. 목록 컬렉션 멤버 함수도 `AddTail` 고 `RemoveHead` 사용 하 여 추가할 수 있습니다 하 고 특히 헤드 또는 목록의 꼬리에서 요소를 제거 합니다. 즉, 가장 최근에 추가 된 요소는 항상 마지막으로 제거 합니다.

#### <a name="to-create-a-queue-collection"></a>큐 컬렉션을 만들려면

1. Microsoft Foundation Class 라이브러리를 사용 하 여 제공 되는 미리 정의 된 목록 클래스 중 하나에서 새 목록 클래스를 파생 하 고 큐 작업의 의미 체계를 지원 하기 위해 더 많은 멤버 함수를 추가 합니다.

   다음 예제에서는 큐의 앞에서 요소를 받고 큐의 끝에 요소를 추가 하는 멤버 함수를 추가할 수 있습니다 하는 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>참고자료

[컬렉션](../mfc/collections.md)
