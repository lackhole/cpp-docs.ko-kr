---
title: 컴파일러 오류 C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: 7e56ff814b1a2dd6ec3cb41db2cbcc21d7dcf2d9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750171"
---
# <a name="compiler-error-c3519"></a>컴파일러 오류 C3519

' invalid_param ': embedded_idl 특성에 대 한 매개 변수가 잘못 되었습니다.

매개 변수가 [#import](../../preprocessor/hash-import-directive-cpp.md)의 `embedded_idl` 특성에 전달 되었지만 컴파일러가 매개 변수를 인식 하지 못했습니다.

`embedded_idl`에 허용 되는 유일한 매개 변수는 `emitidl` 및 `no_emitidl`입니다.

다음 샘플에서는 C3519를 생성 합니다.

```cpp
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```
