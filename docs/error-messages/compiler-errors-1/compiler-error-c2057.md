---
title: 컴파일러 오류 C2057
ms.date: 11/04/2016
f1_keywords:
- C2057
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
ms.openlocfilehash: 1c873a0ba956adedea3311ac8e1844a629caa44b
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302031"
---
# <a name="compiler-error-c2057"></a>컴파일러 오류 C2057

상수 식이 필요합니다.

컨텍스트에는 컴파일 시간에 값이 인식되는 상수 식이 필요합니다.

컴파일러는 해당 형식의 인스턴스에 대한 공간을 할당하기 위해 컴파일 시간에 형식의 크기를 알고 있어야 합니다.

## <a name="example"></a>예

다음 샘플에서는 C2057을 생성하고 해결 방법을 보여 줍니다.

```cpp
// C2057.cpp
int i;
int b[i];   // C2057 - value of i is unknown at compile time
int main() {
   const int i = 8;
   int b[i]; // OK - value of i is fixed and known to compiler
}
```

## <a name="example"></a>예

C에서는 상수 식에 대해 보다 제한적인 규칙을 제공합니다.  다음 샘플에서는 C2057을 생성하고 해결 방법을 보여 줍니다.

```c
// C2057b.c
#define ArraySize1 10
int main() {
   const int ArraySize2 = 10;
   int h[ArraySize2];   // C2057 - C does not allow variables here
   int h[ArraySize1];   // OK - uses preprocessor constant
}
```
