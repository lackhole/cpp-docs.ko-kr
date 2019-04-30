---
title: 컴파일러 오류 C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: cc6c3a3a29665ccf65b77a3d9866986cb0a46b9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353229"
---
# <a name="compiler-error-c2555"></a>컴파일러 오류 C2555

'class1::function1': 재정의 가상 함수의 반환 형식이 다른 고 아닌 'class2::function2'에서 공변 (covariant)

가상 함수 및 파생된 재정의 함수에는 있지만 다른 반환 형식은 동일한 매개 변수 목록에 있습니다. 파생된 클래스에서 재정의 함수를 반환 형식에 의해서만 기본 클래스의 가상 함수에서 다를 수 없습니다.

이 오류를 해결 하려면 가상 함수를 호출한 후 반환 값을 캐스팅 합니다.

/Clr을 사용 하 여 컴파일하는 경우에이 오류가 나타날 수 있습니다.   예를 들어, 시각적 개체 C++ 다음과 같음 C# 선언 합니다.

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

다음 샘플에서는 C2555 오류가 생성 됩니다.

```cpp
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```