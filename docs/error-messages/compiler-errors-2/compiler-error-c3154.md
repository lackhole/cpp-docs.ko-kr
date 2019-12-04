---
title: 컴파일러 오류 C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: e40b0c2a56c36b92465fb3bb3451a48c88b5822e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745930"
---
# <a name="compiler-error-c3154"></a>컴파일러 오류 C3154

줄임표 앞에 ', '가 필요 합니다. 매개 변수 배열 함수에서는 쉼표가 아닌 구분 된 줄임표가 지원 되지 않습니다.

변수 인수 함수가 올바르게 선언 되지 않았습니다.

자세한 내용은 [가변 인수 목록 (...)C++(/cli)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3154를 생성 합니다.

```cpp
// C3154.cpp
// compile with: /clr
ref struct R {
   void Func(int ... array<int> ^);   // C3154
   void Func2(int i, ... array<int> ^){}   // OK
   void Func3(array<int> ^){}   // OK
   void Func4(... array<int> ^){}   // OK
};

int main() {
   R ^ r = gcnew R;
   r->Func4(1,2,3);
}
```
