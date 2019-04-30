---
title: 컴파일러 오류 C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 7fcf333f62253eb676c0f0ada1c927ab962ae1ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338924"
---
# <a name="compiler-error-c2441"></a>컴파일러 오류 C2441

> '*변수*': __declspec (process)를 사용 하 여 선언 된 기호는 /clr에서 const 여야 합니다: pure 모드

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

변수는 기본적으로 응용 프로그램 도메인 별로 **/clr: pure**합니다. 변수 표시 `__declspec(process)` 아래 **/clr: pure** 다른 읽고 응용 프로그램 도메인에서 수정 하는 경우 오류가 발생할 가능성이 높습니다.

변수 프로세스당 경우 컴파일러는 따라서 `const` 에서 **/clr: pure**, 모든 응용 프로그램 도메인 에서만 읽을 만들기.

자세한 내용은 [프로세스](../../cpp/process.md) 하 고 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예제

다음 샘플 C2441를 생성합니다.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```