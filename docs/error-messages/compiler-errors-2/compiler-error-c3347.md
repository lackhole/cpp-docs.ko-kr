---
title: 컴파일러 오류 C3347
ms.date: 11/04/2016
f1_keywords:
- C3347
helpviewer_keywords:
- C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
ms.openlocfilehash: 8b1c4ea76f65b9f07a96177d2e481d1abeba0927
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300646"
---
# <a name="compiler-error-c3347"></a>컴파일러 오류 C3347

'arg': idl_module 특성에 필수 인수를 지정하지 않았습니다.

필수 인수가 [idl_module](../../windows/idl-module.md) 특성에 전달되지 않았습니다.

다음 샘플에서는 C3347을 생성합니다.

```
// C3347.cpp
// compile with: /c
[module(name="xx")];

[idl_module(dllname="x")];    // C3347
// try the following line instead
// [idl_module(name="test", dllname="x")];
```