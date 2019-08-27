---
title: 메모리 관리 함수
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: 9a7810267c3eaa11ad7592774440365620e7e8f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413868"
---
# <a name="memory-management-functions"></a>메모리 관리 함수

이 문서에서는 동시성 런타임에서 메모리 할당과 해제를 동시에 수행할 수 있도록 제공 하는 메모리 관리 함수를 설명 합니다.

> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 애플리케이션에서 스케줄러를 만들 필요가 없습니다. 작업 Scheduler를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 있기 때문에 시작 하는 것이 좋습니다 합니다 [PPL 병렬 패턴 라이브러리 ()](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 있다면 동시성 런타임으로 새입니다.

동시성 런타임에서 할당 및 메모리 블록을 동시에 해제에 대 한 최적화 된 두 메모리 관리 함수를 제공 합니다. 합니다 [concurrency:: alloc](reference/concurrency-namespace-functions.md#alloc) 함수는 지정된 된 크기를 사용 하 여 메모리 블록을 할당 합니다. 합니다 [concurrency:: free](reference/concurrency-namespace-functions.md#free) 함수에 의해 할당 된 메모리를 해제 `Alloc`합니다.

> [!NOTE]
>  합니다 `Alloc` 및 `Free` 함수는 서로 의존 합니다. 사용 합니다 `Free` 만 사용 하 여 할당 하는 메모리를 해제 하는 함수는 `Alloc` 함수입니다. 또한 사용 하는 경우는 `Alloc` 메모리 할당만 사용 하는 함수는 `Free` 해당 메모리를 해제 하는 함수입니다.

사용 된 `Alloc` 및 `Free` 할당 하 고 다른 스레드 또는 작업에서 할당 크기의 고정된 된 집합을 해제 하는 경우 함수입니다. 동시성 런타임은 C 런타임 힙에서 할당 된 메모리를 캐시 합니다. 동시성 런타임의 각 실행 스레드;에 대 한 별도 메모리 캐시를 보유합니다. 따라서 런타임에서 잠금이나 메모리 장벽을 사용 하지 않고 메모리를 관리 합니다. 응용 프로그램 혜택에서 더 많은 정보를 `Alloc` 및 `Free` 메모리 캐시를 더 자주 액세스 될 때 함수입니다. 예를 들어, 자주 둘 다를 호출 하는 스레드 `Alloc` 및 `Free` 주로 호출 하는 스레드 보다 더 많은 이점을 얻습니다 `Alloc` 또는 `Free`합니다.

> [!NOTE]
>  이러한 메모리 관리 함수를 사용 하 고 입력에 응용 프로그램에서는 많은 양의 메모리를 응용 프로그램 메모리 부족 상태 예상 보다 빨리 합니다. 하나의 스레드에서 캐시 되는 메모리 블록의 스레드와 많은 메모리를 보유 하는 경우 다른 스레드를 사용할 수 없기 때문 해당 메모리를 사용할 수 없습니다.

## <a name="example"></a>예제

사용 하는 예는 `Alloc` 및 `Free` 메모리 성능을 향상 시키기 위해 함수 참조 [방법: 할당을 사용 하 여 메모리 성능 향상을 위해 무료](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)합니다.

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
