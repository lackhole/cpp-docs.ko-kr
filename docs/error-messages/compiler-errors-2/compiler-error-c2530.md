---
title: 컴파일러 오류 C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 2c8164cad25d68ee61ff9fed7170482d5dfc9505
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386995"
---
# <a name="compiler-error-c2530"></a>컴파일러 오류 C2530

'identifier': 참조를 초기화 해야 합니다

초기화 해야 대 한 참조를 선언할 때 이미 선언 하지 않으면:

- 키워드로 [extern](../../cpp/using-extern-to-specify-linkage.md)합니다.

- 클래스, 구조체 또는 공용 구조체의 멤버로 (및 생성자에서 초기화).

- 매개 변수로 함수 선언 또는 정의 합니다.

- 으로 함수의 반환 형식입니다.

다음 샘플에서는 C2530 오류가 생성 됩니다.

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```