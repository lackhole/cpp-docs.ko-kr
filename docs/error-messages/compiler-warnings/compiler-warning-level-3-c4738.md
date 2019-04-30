---
title: 컴파일러 경고(수준 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: 833546d20454e6104a2d5fcb272bf5bb9518ea44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401581"
---
# <a name="compiler-warning-level-3-c4738"></a>컴파일러 경고(수준 3) C4738

32비트 float 결과를 메모리에 저장하면 성능이 저하될 수 있습니다.

C4738 캐스팅, 할당의 결과 인수를 전달 하거나 다른 작업을 반올림할 해야 할 수는 또는 작업 레지스터 부족 (분산이) 메모리를 사용 하는 데 필요한 경고 합니다. 이 성능 손실 될 수 있습니다.

이 경고를 해결 하려면 반올림 방지를 사용 하 여 컴파일하면 [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) 사용할지 `double` 대신 `float`합니다.

이 경고를 해결 하 고 등록 부족을 방지 하려면 계산 순서를 변경 하 고의 사용을 수정 인라인 처리

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4738 오류가 생성 됩니다.

```
// C4738.cpp
// compile with: /c /fp:precise /O2 /W3
// processor: x86
#include <stdio.h>

#pragma warning(default : 4738)

float func(float f)
{
    return f;
}

int main()
{
    extern float f, f1, f2;
    double d = 0.0;

    f1 = func(d);
    f2 = (float) d;
    f = f1 + f2;   // C4738
    printf_s("%f\n", f);
}
```