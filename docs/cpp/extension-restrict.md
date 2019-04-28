---
title: __restrict
ms.date: 10/10/2018
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
ms.openlocfilehash: 76cdf9424e6eab33a3a92b3f98d9c2b0b04ff667
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183754"
---
# <a name="restrict"></a>__restrict

**__declspec ([restrict](../cpp/restrict.md) )** 수정자와 마찬가지로 **__restrict** 키워드는 현재 범위에서 기호에 별칭이 지정되지 않음을 나타냅니다. 합니다 **__restrict** 에서 다른 키워드는 `__declspec ( restrict )` 다음과 같이 한정자:

- **__restrict** 키워드는 변수에 대해서만 유효하며 `__declspec ( restrict )` 는 함수 선언 및 정의에 대해서만 유효합니다.

- **__restrict**는 C99 사양의 **restrict**와 비슷하지만 **__restrict**의 경우에는 C++ 또는 C 프로그램에서 사용할 수 있습니다.

- **__restrict**를 사용하는 경우 컴파일러는 변수의 별칭 없음 속성을 전파하지 않습니다. 즉, **__restrict**가 아닌 변수에 **__restrict** 변수를 할당하면 컴파일러는 __restrict가 아닌 변수에 별칭이 지정되도록 허용합니다. 이 동작은 C99 사양의 **restrict** 키워드 동작과는 다릅니다.  

일반적으로 전체 함수의 동작을 변경하려면 키워드보다는 `__declspec ( restrict )`를 사용하는 것이 효율적입니다.

이전 버전과 호환성을 위해 **_restrict**에 대한 동의어가 **__restrict** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md)을 지정합니다.

Visual Studio 2015 이상에서는 **__restrict** C++ 참조에 사용할 수 있습니다.

> [!NOTE]
>  [volatile](../cpp/volatile-cpp.md) 키워드도 포함된 변수에 사용하는 경우 **volatile**이 우선적으로 적용됩니다.

## <a name="example"></a>예제

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)