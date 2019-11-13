---
title: 컴파일러 경고(수준 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 195e5532b6555210077e43ad3086ee3106f3e757
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966019"
---
# <a name="compiler-warning-level-1-c4461"></a>컴파일러 경고(수준 1) C4461

' type ':이 클래스에 종료자 ' 종료자 '가 있지만 ' dtor ' 소멸자가 없습니다.

형식에 종료 자가 있으면 삭제할 리소스가 있음을 의미 합니다. 종료자를 형식의 소멸자에서 명시적으로 호출 하지 않으면 공용 언어 런타임에서는 개체가 범위를 벗어나면 종료자를 실행할 시기를 결정 합니다.

형식에서 소멸자를 정의 하 고 소멸자에서 종료자를 명시적으로 호출 하는 경우 종료자를 명확 하 게 실행할 수 있습니다.

자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4461를 생성 합니다.

```cpp
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```