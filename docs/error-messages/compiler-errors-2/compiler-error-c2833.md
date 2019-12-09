---
title: 컴파일러 오류 C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: c1467a3c67cccf28cc6b9bd0f987fe77b8da8988
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757880"
---
# <a name="compiler-error-c2833"></a>컴파일러 오류 C2833

' operator operator '은 (는) 인식할 수 있는 연산자 또는 형식이 아닙니다.

단어 `operator` 뒤에 재정의 하려는 연산자 또는 변환 하려는 형식이 있어야 합니다.

관리 되는 형식에서 정의할 수 있는 연산자 목록은 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)를 참조 하세요.

다음 샘플에서는 C2833를 생성 합니다.

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
