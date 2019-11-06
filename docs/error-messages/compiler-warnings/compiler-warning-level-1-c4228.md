---
title: 컴파일러 경고 (수준 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: 75bd34a4338db7a430c1951d5bc3bd61dbce4f64
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627269"
---
# <a name="compiler-warning-level-1-c4228"></a>컴파일러 경고 (수준 1) C4228

비표준 확장이 사용 됨: 선언 자 목록에서 쉼표 뒤의 한정자가 무시 됩니다.

변수를 선언 하는 경우 쉼표 뒤에 **const** 또는 `volatile`와 같은 한정자를 사용 하는 것은 Microsoft 확장 ([/ze](../../build/reference/za-ze-disable-language-extensions.md))입니다.

## <a name="example"></a>예제

```cpp
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```