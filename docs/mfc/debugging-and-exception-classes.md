---
title: 디버깅 및 예외 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 328d7a38c544b56f83ea3e8b1136b1122c4dfa14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241183"
---
# <a name="debugging-and-exception-classes"></a>디버깅 및 예외 클래스

이러한 클래스는 동적 메모리 할당을 디버깅하고 예외가 throw된 함수에서 예외가 catch된 함수로 예외 정보를 전달하기 위한 지원을 제공합니다.

클래스를 사용 하 여 [CDumpContext](../mfc/reference/cdumpcontext-class.md) 하 고 [CMemoryState](../mfc/reference/cmemorystate-structure.md) 에 설명 된 대로 디버깅을 지원 하기 위해 개발 하는 동안 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다. 사용 하 여 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) 문서에 설명 된 대로 런타임 시 개체의 클래스를 확인 하려면 [런타임 클래스 정보 액세스](../mfc/accessing-run-time-class-information.md)합니다. 프레임워크는 `CRuntimeClass`를 사용해서 특정 클래스의 개체를 동적으로 만듭니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
