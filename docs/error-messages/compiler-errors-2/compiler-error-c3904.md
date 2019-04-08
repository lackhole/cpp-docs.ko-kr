---
title: 컴파일러 오류 C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 4675bf95012c8e6662d7dba281c38ed2d684c448
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779874"
---
# <a name="compiler-error-c3904"></a>컴파일러 오류 C3904

'property_accessor': 숫자 매개 변수를 지정 해야 합니다

매개 변수 개수를 확인 하 `get` 고 `set` 속성 차원에 대해 메서드.

- 에 대 한 매개 변수 개수는 `get` 메서드 속성의 차원 수와 동일 해야 합니다 또는 인덱싱되지 않은 속성에 대 한 0 이어야 합니다.

- 매개 변수 개수는 `set` 메서드는 하나 여야 합니다 차원 속성의 수를 초과 합니다.

자세한 내용은 [property](../../extensions/property-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플 C3904를 생성합니다.

```
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

다음 샘플 C3904를 생성합니다.

```
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