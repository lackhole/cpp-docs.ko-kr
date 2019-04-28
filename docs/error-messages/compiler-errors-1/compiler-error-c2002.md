---
title: 컴파일러 오류 C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: 30f472aa7a9475a19eea0e92fe5c2ea0d54e382b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209038"
---
# <a name="compiler-error-c2002"></a>컴파일러 오류 C2002

잘못 된 와이드 문자 상수

멀티 바이트 문자 상수가 잘못 되었습니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 와이드 문자 상수는 예상 보다 더 많은 바이트를 포함 합니다.

1. 표준 헤더 STDDEF.h 포함 되지 않습니다.

1. 와이드 문자는 일반 문자열 리터럴을 연결할 수 없습니다.

1. 'L' 문자로 와이드 문자 상수와 야 합니다.

    ```
    L'mbconst'
    ```

1. Microsoft C++, 전처리기 지시문의 텍스트 인수에는 ASCII 이어야 합니다. 예를 들어, 지시문을 `#pragma message(L"string")`에 올바르지 않습니다.