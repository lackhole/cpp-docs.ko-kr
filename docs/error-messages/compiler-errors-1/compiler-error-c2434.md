---
title: 컴파일러 오류 C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: c73a8d4fcde945ddf2495cc2d0d7dc47216f2db3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166336"
---
# <a name="compiler-error-c2434"></a>컴파일러 오류 C2434

> '*기호*': __declspec (process)를 사용 하 여 선언 된 기호는 /clr에서 동적으로 초기화할 수 없습니다: pure 모드

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

동적으로 아래 프로세스별 변수를 초기화할 수 없는 **/clr: pure**합니다. 자세한 내용은 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 하 고 [프로세스](../../cpp/process.md)합니다.

## <a name="example"></a>예제

다음 샘플 C2434를 생성합니다. 이 문제를 해결 하려면 사용 하 여 상수를 초기화 `process` 변수입니다.

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```