---
title: 컴파일러 오류 C2206
ms.date: 11/04/2016
f1_keywords:
- C2206
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
ms.openlocfilehash: 3ee2dc24dd2472be8b69a389df1cad77337abf90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368164"
---
# <a name="compiler-error-c2206"></a>컴파일러 오류 C2206

'function': 형식 정의는 함수 정의에 사용할 수 없습니다.

`typedef` 가 함수 형식을 정의하는 데 사용됩니다.

다음 샘플에서는 C2206을 생성합니다.

```
// C2206.cpp
typedef int functyp();
typedef int MyInt;
functyp func1 {};   // C2206
int main() {
   MyInt i = 0;   // OK
}
```