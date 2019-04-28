---
title: '메모리 관리: 크기 조정 가능한 메모리 블록'
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: 124a2599e1523d5393fcf6255c88de0fd8cd72cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219144"
---
# <a name="memory-management-resizable-memory-blocks"></a>메모리 관리: 크기 조정 가능한 메모리 블록

합니다 **새** 하 고 **삭제** 연산자를 문서에서 설명한 [메모리 관리: 예제](../mfc/memory-management-examples.md)를 할당 하 고 크기가 고정 된 메모리 블록 및 개체 할당을 취소 하는 경우에 유용 합니다. 경우에 따라 응용 프로그램 크기 조정 가능한 메모리 블록을 해야 합니다. 표준 C 런타임 라이브러리 함수를 사용 해야 [malloc](../c-runtime-library/reference/malloc.md)를 [realloc](../c-runtime-library/reference/realloc.md), 및 [무료](../c-runtime-library/reference/free.md) 힙의 크기 조정 가능한 메모리 블록을 관리할 수 있습니다.

> [!IMPORTANT]
>  혼합 합니다 **새** 하 고 **삭제** 연산자 동일한 메모리 블록의 크기 조정 가능한 메모리 할당 함수를 사용 하면 MFC의 디버그 버전에서 손상 된 메모리입니다. 사용 하지 않아야 **realloc** 사용 하 여 할당 된 메모리 블록 **새**합니다. 마찬가지로 인 메모리 블록을 하지 할당 해야 합니다 **새** 연산자를 사용 하 여 삭제 **무료**, 사용할지를 **삭제** 를사용하여할당된메모리블록에서연산자**malloc**합니다.

## <a name="see-also"></a>참고자료

[메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)
