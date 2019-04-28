---
title: 컴파일러 경고 C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: 784179af68ff55ba70c61255c88688105ecb1738
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208098"
---
# <a name="compiler-warning-c4950"></a>컴파일러 경고 C4950

'type_or_member': 사용되지 않는 것으로 표시되었습니다.

멤버 또는 형식으로 사용 되지 않는 표시 된는 <xref:System.ObsoleteAttribute> 특성입니다.

C4950은 항상 오류로 실행됩니다. 사용 하 여이 경고를 해제할 수 있습니다 합니다 [경고](../../preprocessor/warning.md) pragma 지시문 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4950을 생성합니다.

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```