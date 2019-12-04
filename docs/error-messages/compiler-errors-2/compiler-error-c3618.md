---
title: 컴파일러 오류 C3618
ms.date: 11/04/2016
f1_keywords:
- C3618
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
ms.openlocfilehash: 6f0edf1addf753054fbc50a1591b5b1a37394087
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759726"
---
# <a name="compiler-error-c3618"></a>컴파일러 오류 C3618

' function ': DllImport로 표시 된 메서드를 정의할 수 없습니다.

<xref:System.Runtime.InteropServices.DllImportAttribute> 표시 된 메서드가 지정 된에 정의 되어 있습니다. GDIPLUS.DLL.

## <a name="example"></a>예제

다음 샘플에서는 C3618를 생성 합니다.

```cpp
// C3618.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED
void Func();

void Func() {}   // C3618, remove this function definition to resolve
```
