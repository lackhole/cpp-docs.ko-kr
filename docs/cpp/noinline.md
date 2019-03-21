---
title: noinline
ms.date: 11/04/2016
f1_keywords:
- noinline_cpp
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
ms.openlocfilehash: e155726ad1f2f3f6f0501d3aebf7fa14e620d6bd
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742481"
---
# <a name="noinline"></a>noinline

## <a name="microsoft-specific"></a>Microsoft 전용

**__declspec(noinline)** 은 특정 멤버 함수(클래스의 함수)를 인라인 처리하지 않도록 컴파일러에 지시합니다.

함수가 작고 코드 성능에 심각한 영향을 주지 않는 경우 함수를 인라인 처리하지 않는 것이 적합할 수 있습니다. 즉, 오류 조건을 처리하는 함수처럼 함수가 작고 자주 호출될 가능성이 적은 경우가 여기에 해당합니다.

함수가 **noinline**으로 표시된 경우 호출하는 함수는 더 작기 때문에 그 자체가 컴파일러 인라인 처리의 후보가 됩니다.

```cpp
class X {
   __declspec(noinline) int mbrfunc() {
      return 0;
   }   // will not inline
};
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)
