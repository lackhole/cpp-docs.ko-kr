---
title: 컴파일러 오류 C2430
ms.date: 11/04/2016
f1_keywords:
- C2430
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
ms.openlocfilehash: f82eb4914ec36aa513822964f551a05fbb77aa97
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744578"
---
# <a name="compiler-error-c2430"></a>컴파일러 오류 C2430

' identifier '에 인덱스 레지스터가 두 개 이상 있습니다.

둘 이상의 레지스터가 확장 됩니다. 컴파일러는 크기 조정 된 인덱싱을 지원 하지만 하나의 레지스터를 확장할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2430를 생성 합니다.

```cpp
// C2430.cpp
// processor: x86
int main() {
   _asm mov eax, [ebx*2+ecx*4] // C2430
}
```
