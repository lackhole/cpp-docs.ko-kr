---
title: 컴파일러 경고(수준 1) C4397
ms.date: 11/04/2016
f1_keywords:
- C4397
helpviewer_keywords:
- C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
ms.openlocfilehash: 4ad690d78c1544adbe365a35ba3b5921c883631e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365392"
---
# <a name="compiler-warning-level-1-c4397"></a>컴파일러 경고(수준 1) C4397

DefaultCharSetAttribute가 무시 됩니다.

<xref:System.Runtime.InteropServices.DefaultCharSetAttribute> 시각적 개체에서 무시 됩니다 C++ 컴파일러. DLL에 대해 설정 하는 문자를 지정 하려면 DllImport의 CharSet 옵션을 사용 합니다. 자세한 내용은 [사용 C++ (암시적 PInvoke) Interop](../../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

## <a name="example"></a>예제

다음 샘플 C4397를 생성합니다.

```
// C4397.cpp
// compile with: /W1 /c /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397

[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK
extern "C" bool ImportDefault(IntPtr hObject);

public ref class MySettingVC {
public:
   void method() {
      ImportDefault(IntPtr::Zero);
   }
};

[StructLayout(LayoutKind::Explicit)]
public ref struct StructDefault1{};

public ref class ClassDefault1{};
```