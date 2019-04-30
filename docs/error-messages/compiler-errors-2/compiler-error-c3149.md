---
title: 컴파일러 오류 C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 8238dcec821256dad8101cd7ad59b2d85882c218
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345518"
---
# <a name="compiler-error-c3149"></a>컴파일러 오류 C3149

'type': 최상위 'char' 하지 않고 여기이 형식을 사용할 수 없습니다

선언 올바르게 지정 되지 않았습니다.

예를 들어 수 정의 전역 범위에서 CLR 형식을 하 고 정의의 일부로 형식의 변수를 만들려고 합니다. CLR 형식의 전역 변수 허용 되지 않는 컴파일러 C3149 생성 됩니다.

이 오류를 해결 하려면 함수 또는 형식 정의 내에서 CLR 유형의 변수를 선언 합니다.

다음 샘플에서는 C3149 오류가 생성 됩니다.

```
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

다음 샘플에서는 C3149 오류가 생성 됩니다.

```
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
