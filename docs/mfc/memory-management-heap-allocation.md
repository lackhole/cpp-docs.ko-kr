---
title: '메모리 관리: 힙 할당'
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
ms.openlocfilehash: 93eee5cbfe1cd49042a9080f06657e751640de69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219479"
---
# <a name="memory-management-heap-allocation"></a>메모리 관리: 힙 할당

힙에 프로그램에 필요한 메모리 할당에 대 한 예약 되어 있습니다. 이 외에도 프로그램 코드와 스택에 영역입니다. 함수를 사용 하 여 일반적인 C 프로그램 **malloc** 하 고 **무료** 할당 하 고 힙 메모리의 할당을 취소 합니다. MFC의 디버그 버전의 수정 된 버전을 제공 합니다 C++ 기본 제공 연산자 **새** 및 **삭제** 할당 하 고 힙 메모리에 개체 할당을 취소 합니다.

사용 하는 경우 **새** 하 고 **삭제** 대신 **malloc** 고 **무료**, 클래스 라이브러리의 기능을 활용할 수 있습니다 메모리 관리 디버깅 기능을 향상 메모리 누수를 탐지 하는 데 유용할 수 있습니다. MFC의 표준 버전의 릴리스 버전을 사용 하 여 프로그램을 작성 하는 경우는 **새** 하 고 **삭제** 연산자 할당 (릴리스 버전의 MFC 메모리 할당을 취소 하는 효율적인 방법을 제공 이러한 연산자의 수정 된 버전 제공 하지 않습니다).

힙에 할당 된 개체의 총 크기 시스템의 사용 가능한 가상 메모리에 의해서만 제한 되는 참고 합니다.

## <a name="see-also"></a>참고자료

[메모리 관리](../mfc/memory-management.md)
