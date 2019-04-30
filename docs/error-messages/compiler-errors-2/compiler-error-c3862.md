---
title: 컴파일러 오류 C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 2ba130862b1debbe2991ca7cbcae50192f900cd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302316"
---
# <a name="compiler-error-c3862"></a>컴파일러 오류 C3862

> '*함수*': /clr을 사용 하 여 관리 되지 않는 함수를 컴파일할 수 없습니다: pure 또는 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

사용한 컴파일에 **/clr: pure** 또는 **/clr: safe** 는 MSIL만 이미지를 네이티브 (비관리) 코드를 사용 하 여 이미지를 생성 합니다.  따라서 사용할 수 없습니다는 `unmanaged` pragma는 **/clr: pure** 또는 **/clr: safe** 컴파일.

자세한 내용은 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 하 고 [관리 되는, 관리 되지 않는](../../preprocessor/managed-unmanaged.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3862 오류가 생성 됩니다.

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```