---
title: 컴파일러 오류 C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: a75330d26b0924e60f7e46d10d617341709d7e23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353497"
---
# <a name="compiler-error-c2144"></a>컴파일러 오류 C2144

> 구문 오류: '*형식*'앞에 있어야'*토큰*'

예상 컴파일러 *토큰* 거쳐 *형식* 대신 합니다.

이 오류는 닫는 중괄호가 누락, 오른쪽 괄호 또는 세미콜론으로 발생할 수 있습니다.

C2144 공백 문자를 포함 하는 CLR 키워드에서 매크로를 만들려고 할 때 발생할 수 있습니다.

C2144는 형식을 전달 하려고 하는 경우에 나타날 수 있습니다. 참조 [형식 전달 (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) 에 대 한 자세한 내용은 합니다.

## <a name="examples"></a>예제

다음 샘플 C2144, 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

다음 샘플 C2144, 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```