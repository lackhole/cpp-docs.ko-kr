---
title: 컴파일러 오류 C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 39f779ee846cf4f328f9c7af59ae394d97d7a3ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744734"
---
# <a name="compiler-error-c2422"></a>컴파일러 오류 C2422

' 피연산자 '에 잘못 된 세그먼트 재정의가 있습니다.

인라인 어셈블리 코드에서 피연산자에 대 한 세그먼트 재정의 연산자 (콜론)를 잘못 사용 했습니다.  이 오류가 발생하는 원인은 다음과 같습니다.

- 연산자 앞의 레지스터가 세그먼트 레지스터가 아닙니다.

- 연산자 앞의 레지스터가 피연산자의 유일한 세그먼트 레지스터가 아닙니다.

- 세그먼트 재정의 연산자는 간접 참조 연산자 (대괄호) 내에 표시 됩니다.

- 세그먼트 재정의 연산자 다음의 식은 직접 피연산자 또는 메모리 피연산자가 아닙니다.

다음 샘플에서는 C2422를 생성 합니다.

```cpp
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```
