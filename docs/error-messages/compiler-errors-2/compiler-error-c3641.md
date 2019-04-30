---
title: 컴파일러 오류 C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: f6c27067e4f07c89b4226cf4d26adf2afb0b07ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385656"
---
# <a name="compiler-error-c3641"></a>컴파일러 오류 C3641

> '*함수*': 호출 규칙 'calling_convention' /clr을 사용 하 여 컴파일된 함수에 대 한 잘못 된: pure 또는 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

만 [__clrcall](../../cpp/clrcall.md) 사용 하 여 허용 되는 호출 규칙 [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3641 오류가 생성 됩니다.

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```