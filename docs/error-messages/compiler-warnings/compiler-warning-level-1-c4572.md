---
title: 컴파일러 경고 (수준 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: 52285f391af0a8028307cbbc320af33f9cb1fca5
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965950"
---
# <a name="compiler-warning-level-1-c4572"></a>컴파일러 경고 (수준 1) C4572

[ParamArray] 특성은/clr에서 사용 되지 않습니다. ' ... '를 사용 하세요. 대신

가변 인수 목록을 지정 하는 데 사용 되지 않는 스타일이 사용 되었습니다. CLR에 대해 컴파일하는 경우 <xref:System.ParamArrayAttribute>대신 줄임표 구문을 사용 합니다. 자세한 내용은 [가변 인수 목록 (...)C++(/cli)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4572를 생성 합니다.

```cpp
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```