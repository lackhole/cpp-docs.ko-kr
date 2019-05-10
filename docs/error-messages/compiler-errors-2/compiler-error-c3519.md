---
title: 컴파일러 오류 C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: e9a998e1c3a6c2fb770fb9d26d97b8a24e5554d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360036"
---
# <a name="compiler-error-c3519"></a>컴파일러 오류 C3519

'invalid_param': embedded_idl 특성에 잘못 된 매개 변수

에 전달 된 매개 변수를 `embedded_idl` 의 특성 [#import](../../preprocessor/hash-import-directive-cpp.md), 하지만 컴파일러에서 매개 변수를 인식할 수 없습니다.

에 허용 되는 매개 변수만 `embedded_idl` 됩니다 `emitidl` 고 `no_emitidl`입니다.

다음 샘플에서는 C3519 오류가 생성 됩니다.

```
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```