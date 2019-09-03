---
title: inline_recursion pragma
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 0169e06e8e47f7b0a7b3f73e809ddc988bcf1e95
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220959"
---
# <a name="inline_recursion-pragma"></a>inline_recursion pragma

직접 또는 상호 재귀 함수 호출의 인라인 확장을 제어합니다.

## <a name="syntax"></a>구문

> **#pragma inline_recursion (** [{ **on** | **off** }] **)**

## <a name="remarks"></a>설명

이 pragma를 사용 하면 `/Ob2` 컴파일러에서 자동으로 옵션을 확장 하는 [인라인](../cpp/inline-functions-cpp.md) 및 [__inline](../cpp/inline-functions-cpp.md) 또는 함수로 표시 된 함수를 제어할 수 있습니다. 이 pragma를 사용 하려면 [/Ob](../build/reference/ob-inline-function-expansion.md) 컴파일러 옵션을 1 또는 2로 설정 해야 합니다. **Inline_recursion** 의 기본 상태는 off입니다. 이 pragma는 pragma가 표시 된 후 첫 번째 함수 호출에서 적용 되며 함수 정의에는 영향을 주지 않습니다.

**Inline_recursion** pragma는 재귀 함수를 확장 하는 방법을 제어 합니다. **Inline_recursion** 가 off이 고 인라인 함수가 직접 또는 간접적으로 자신을 호출 하는 경우 함수는 한 번만 확장 됩니다. **Inline_recursion** 가 on 인 경우 함수는 [inline_depth](../preprocessor/inline-depth.md) pragma를 사용 하 여 설정 된 값에 도달할 때까지 여러 번 확장 되거나, `inline_depth` pragma로 정의 된 재귀 함수의 기본값 또는 용량 제한에 도달할 때까지 여러 번 확장 됩니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/Ob(인라인 함수 확장)](../build/reference/ob-inline-function-expansion.md)
