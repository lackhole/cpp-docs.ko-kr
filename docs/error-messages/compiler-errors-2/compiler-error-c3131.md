---
title: 컴파일러 오류 C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 082839c01a2da4b0d149962367b9719932d2b272
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349934"
---
# <a name="compiler-error-c3131"></a>컴파일러 오류 C3131

프로젝트에 'name' 속성과 'module' 특성이 있어야 합니다.

합니다 [모듈](../../windows/module-cpp.md) 특성 이름 매개 변수가 있어야 합니다.

다음 샘플에서는 C3131를 생성합니다.

```
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```