---
title: 컴파일러 오류 C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: d4234626bc246d6da87be68b03d44562dd5990ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744513"
---
# <a name="compiler-error-c2432"></a>컴파일러 오류 C2432

' identifier '의 16 비트 데이터에 대 한 참조가 잘못 되었습니다.

16 비트 레지스터가 인덱스 또는 기본 레지스터로 사용 됩니다. 컴파일러는 16 비트 데이터 참조를 지원 하지 않습니다. 16 비트 레지스터는 32 비트 코드를 컴파일할 때 인덱스 또는 기본 레지스터로 사용할 수 없습니다.

다음 샘플에서는 C2432를 생성 합니다.

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
