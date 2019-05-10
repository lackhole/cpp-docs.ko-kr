---
title: 컴파일러 오류 C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: 0a1b0b82241c6e48d2c1941ff8122697d11492eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352990"
---
# <a name="compiler-error-c3808"></a>컴파일러 오류 C3808

> '*형식*': ComImport 특성이 있는 클래스 멤버를 정의할 수 없습니다 '*멤버*', 추상만 또는 dllimport 함수를 사용할 수

## <a name="remarks"></a>설명

파생 된 형식은 <xref:System.Runtime.InteropServices.ComImportAttribute> 정의할 수 없습니다 *멤버*합니다.

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

## <a name="example"></a>예제

다음 샘플 C3808를 생성합니다.

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```