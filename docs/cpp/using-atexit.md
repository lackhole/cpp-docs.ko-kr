---
title: atexit 사용
ms.date: 11/04/2016
f1_keywords:
- atexit
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
ms.openlocfilehash: 06baba59b5765f853f081b34d73be28a187730ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258000"
---
# <a name="using-atexit"></a>atexit 사용

[atexit](../c-runtime-library/reference/atexit.md) 함수를 사용하여 프로그램 종료 전에 실행되는 종료 처리 함수를 지정할 수 있습니다. **atexit**를 호출하기 전에 초기화된 전역 정적 개체는 종료 처리 함수의 실행 전에 소멸되지 않습니다.

## <a name="see-also"></a>참고자료

[추가 종료 고려 사항](../cpp/additional-termination-considerations.md)