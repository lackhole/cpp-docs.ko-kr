---
title: 컴파일러 오류 C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: d48806982bbb6cdda4d29e47f6692e7e3601d6de
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503207"
---
# <a name="compiler-error-c2362"></a>컴파일러 오류 C2362

> 초기화의 '*식별자*' 의해 생략 되었습니다. ' goto *레이블을*'

사용 하 여 컴파일하면 [/Za](../../build/reference/za-ze-disable-language-extensions.md)에서 레이블로 점프 초기화 되는 식별자 수 없습니다.

선언 되지 입력 블록에 포함 되어 있으면 또는 변수가 이미 초기화 된 경우에 이니셜라이저를 사용 하는 선언이 지나서 이동할 수 있습니다.

다음 샘플에서는 C2362 오류가 생성 됩니다.

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

해결 방법:

```cpp
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```