---
title: 컴파일러 오류 C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: 9f7af4e19fab5f5a0539e9fc3bf9dbeffb5c6fbf
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344651"
---
# <a name="compiler-error-c3154"></a>컴파일러 오류 C3154

예상 ',' 줄임표 앞입니다. 비-쉼표로 구분 줄임표 매개 변수 배열 함수에서 지원 되지 않습니다.

가변 인수 함수를 올바르게 선언 되지 않았습니다.

자세한 내용은 참조 하세요. [가변 인수 목록 (...) (C++/CLI) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>예제

다음 샘플에서는 C3154 오류가 발생 합니다.

```
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