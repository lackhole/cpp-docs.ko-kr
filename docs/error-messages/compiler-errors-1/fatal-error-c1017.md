---
title: 심각한 오류 C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: e2309b93be65b049c35abf96572e144a0a518007
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383180"
---
# <a name="fatal-error-c1017"></a>심각한 오류 C1017

정수 계열 상수 식이 잘못되었습니다.

식에는 `#if` 지시문 없었습니다 또는 상수 식이 아닙니다.

사용 하 여 정의 된 상수 `#define` 정수 상수에 사용 되는 경우 계산 되는 값을 가져야 합니다는 `#if`를 `#elif`, 또는 `#else` 지시문입니다.

다음 샘플에서는 C1017를 생성합니다.

```
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

해결 방법:

```
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

때문에 `CONSTANT_NAME` 문자열과 정수가 아닌 계산 되는 `#if` 지시어 심각한 오류 C1017를 생성 합니다.

다른 경우 전처리기는 0으로 정의 되지 않은 상수를를 평가합니다. 다음 샘플에 표시 된 대로 의도 하지 않은 결과가 발생할 수 있습니다. `YES` 아니므로 정의 0으로 계산 합니다. 식을 `#if` `CONSTANT_NAME` false이 고 코드에서 사용할 `YES` 전처리기에 의해 제거 됩니다. `NO` 정의 되지 않은 (영) 따라서 이기도 `#elif` `CONSTANT_NAME==NO` true로 평가 (`0 == 0`), 전처리기에서 코드를 `#elif` 문의 부분-의도 된 동작의 정확히 반대입니다.

```
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

컴파일러 전처리기 지시문을 처리 하는 방식을 정확 하 게 보려면 [/P](../../build/reference/p-preprocess-to-a-file.md)를 [/E](../../build/reference/e-preprocess-to-stdout.md), 또는 [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)합니다.