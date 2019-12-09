---
title: 컴파일러 오류 C3737
ms.date: 11/04/2016
f1_keywords:
- C3737
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
ms.openlocfilehash: 25dbb8897db45cbddaaf7f0530bcb2a8653b03cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752797"
---
# <a name="compiler-error-c3737"></a>컴파일러 오류 C3737

' delegate ': 대리자는 명시적 호출 규칙을 사용할 수 없습니다.

`delegate`에 대 한 [호출 규칙](../../cpp/calling-conventions.md) 은 지정할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3737를 생성 합니다.

```cpp
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
