---
title: 컴파일러 오류 C2099
ms.date: 11/04/2016
f1_keywords:
- C2099
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
ms.openlocfilehash: 9c83b4a50cb9cf5c5b1992f0f64e2eeb013b48e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376944"
---
# <a name="compiler-error-c2099"></a>컴파일러 오류 C2099

이니셜라이저가 상수가 아닙니다.

이 오류는 C 컴파일러에서만 나타나며, 자동이 아닌 변수에 대해서만 발생합니다.  컴파일러는 프로그램의 시작 부분에서 자동이 아닌 변수를 초기화하며 초기화된 값은 상수여야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2099를 생성합니다.

```
// C2099.c
int j;
int *p;
j = *p;   // C2099 *p is not a constant
```

## <a name="example"></a>예제

부동 소수점 정밀도 환경 설정(자세한 내용은 **_controlfp_s** 참조)은 런타임 컴파일과는 다를 수 있기 때문에 컴파일러는 [/fp:strict](../../c-runtime-library/reference/controlfp-s.md) 의 식에서 상수 폴딩을 수행할 수 없으므로 C2099가 발생할 수도 있습니다.

상수 폴딩이 실패하면 컴파일러가 동적 초기화를 호출하는데 이는 C에서는 허용되지 않습니다.

이 오류를 해결하려면 모듈을 .cpp 파일로 컴파일하거나 식을 단순화합니다.

자세한 내용은 [/fp (Specify Floating-Point Behavior)](../../build/reference/fp-specify-floating-point-behavior.md)을 참조하세요.

다음 샘플에서는 C2099를 생성합니다.

```
// C2099_2.c
// compile with: /fp:strict /c
float X = 2.0 - 1.0;   // C2099
float X2 = 1.0;   // OK
```