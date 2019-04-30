---
title: 컴파일러 오류 C3270
ms.date: 11/04/2016
f1_keywords:
- C3270
helpviewer_keywords:
- C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
ms.openlocfilehash: 91656ee893f2ad7b3f0c53cb157cd9faf129e4c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366045"
---
# <a name="compiler-error-c3270"></a>컴파일러 오류 C3270

'field': FieldOffset 특성은 필요한 StructLayout(Explicit) 컨텍스트에서만 사용할 수 있습니다.

필드 표시 되어 있으므로 **FieldOffset**때만 허용 되는 **structlayout (explicit)** 적용 됩니다.

다음 샘플에서는 C3270을 생성합니다.

```
// C3270_2.cpp
// compile with: /clr /c
using namespace System::Runtime::InteropServices;

[ StructLayout(LayoutKind::Sequential) ]
// try the following line instead
// [ StructLayout(LayoutKind::Explicit) ]
public value struct MYUNION
{
   [FieldOffset(0)] int a;   // C3270
   // ...
};
```
