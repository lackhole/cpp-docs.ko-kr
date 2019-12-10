---
title: 컴파일러 오류 C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: e9bda55c7a65eb5eec4e1f5104a779a817ad5c36
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760493"
---
# <a name="compiler-error-c3470"></a>컴파일러 오류 C3470

'type': 클래스에 인덱서(인덱싱된 기본 속성)와 operator[]가 동시에 포함될 수 없습니다.

하나의 형식으로 기본 인덱서와 연산자[]를 모두 정의할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3470을 생성합니다.

```cpp
// C3470.cpp
// compile with: /clr
using namespace System;

ref class R {
public:
   property int default[int] {
      int get(int i) {
         return i+1;
      }
   }

   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470
};

int main() {
   R ^ r = gcnew R;
   // return r[9] + r["32"] - 42;
}
```
