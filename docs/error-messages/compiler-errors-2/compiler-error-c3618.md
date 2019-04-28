---
title: 컴파일러 오류 C3618
ms.date: 11/04/2016
f1_keywords:
- C3618
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
ms.openlocfilehash: 97f2738a67ee84196a49b96301c885c28c41050b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222067"
---
# <a name="compiler-error-c3618"></a>컴파일러 오류 C3618

'function': DllImport로 표시 된 메서드를 정의할 수 없습니다

메서드를 사용 하 여 표시할지 <xref:System.Runtime.InteropServices.DllImportAttribute> 정의 됩니다 지정 합니다. DLL입니다.

## <a name="example"></a>예제

다음 샘플 C3618를 생성합니다.

```
// C3618.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED
void Func();

void Func() {}   // C3618, remove this function definition to resolve
```