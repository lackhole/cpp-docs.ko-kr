---
title: 컴파일러 오류 C3368
ms.date: 11/04/2016
f1_keywords:
- C3368
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
ms.openlocfilehash: 8e67655e90b571ea099572cdc34bc39124fc3271
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751874"
---
# <a name="compiler-error-c3368"></a>컴파일러 오류 C3368

'function declaration': IDL에 대한 호출 규칙이 잘못되었습니다.

.idl 파일에서 [__stdcall](../../cpp/stdcall.md) 또는 [__cdecl](../../cpp/cdecl.md) 호출 규칙만 사용할 수 있습니다.

다음 샘플에서는 C3368을 생성합니다.

```cpp
// C3368.cpp
// processor: x86
[idl_module(name="Name", dllname="Some.dll")];

[idl_module(name="Name")]
int __fastcall f1();   // C3368
```
