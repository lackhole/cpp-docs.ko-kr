---
title: 컴파일러 오류 C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 1861810f4598fa81d1b7662a57651b1648de1317
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749050"
---
# <a name="compiler-error-c3904"></a>컴파일러 오류 C3904

' property_accessor ': 숫자 매개 변수를 지정 해야 합니다.

`get`의 매개 변수 수와 속성 차원에 대 한 `set` 메서드를 확인 합니다.

- `get` 메서드의 매개 변수 개수는 속성 차원의 수와 동일 하거나 인덱싱되지 않은 속성의 경우 0 이어야 합니다.

- `set` 메서드의 매개 변수 개수는 속성의 차원 수보다 하나 이상 커야 합니다.

자세한 내용은 [property](../../extensions/property-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3904를 생성 합니다.

```cpp
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

## <a name="example"></a>예제

다음 샘플에서는 C3904를 생성 합니다.

```cpp
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```
