---
title: 컴파일러 오류 C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: dbdc86330423ff83be1f188a67684a41cc55aac8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758946"
---
# <a name="compiler-error-c2206"></a>컴파일러 오류 C2206

'function': 형식 정의는 함수 정의에 사용할 수 없습니다.

`typedef` 가 함수 형식을 정의하는 데 사용됩니다.

다음 샘플에서는 C2206을 생성합니다.

```cpp
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```
