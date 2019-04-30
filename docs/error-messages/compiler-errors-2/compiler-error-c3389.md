---
title: 컴파일러 오류 C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 6a9568f3c3be88438eae1f28e12dc780301ead0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402582"
---
# <a name="compiler-error-c3389"></a>컴파일러 오류 C3389

> __declspec (*키워드*) /clr을 사용 하 여 사용할 수 없습니다: pure 또는 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

A [__declspec](../../cpp/declspec.md) 사용 되는 한정자 의미를 프로세스 상태에 따라 합니다.  [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md) 의미는 당 [appdomain](../../cpp/appdomain.md) 상태입니다.  따라서 사용 하 여 변수를 선언 합니다 `keyword` **__declspec** 한정자 및 사용 하 여 컴파일 **/clr: 순수** 허용 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3389 오류가 생성 됩니다.

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```