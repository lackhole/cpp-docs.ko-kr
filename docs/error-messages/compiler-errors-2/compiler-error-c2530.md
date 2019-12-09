---
title: 컴파일러 오류 C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 0816fcb4d9e2a3e6588dfcf937383fed7ab11395
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737129"
---
# <a name="compiler-error-c2530"></a>컴파일러 오류 C2530

' identifier ': 참조를 초기화 해야 합니다.

이미 선언 되지 않은 경우 참조를 선언할 때 초기화 해야 합니다.

- [Extern](../../cpp/using-extern-to-specify-linkage.md)키워드를 사용 합니다.

- 클래스, 구조체 또는 공용 구조체의 멤버 (및 생성자에서 초기화 됨)

- 함수 선언 또는 정의의 매개 변수로

- 함수의 반환 형식으로 반환 됩니다.

다음 샘플에서는 C2530를 생성 합니다.

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
