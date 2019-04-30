---
title: 컴파일러 경고(수준 1) C4329
ms.date: 11/04/2016
f1_keywords:
- C4329
helpviewer_keywords:
- C4329
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
ms.openlocfilehash: 31ea3aec2c7dd8e02a23a5c3cf6e5ac406636516
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390518"
---
# <a name="compiler-warning-level-1-c4329"></a>컴파일러 경고(수준 1) C4329

__declspec(align())는 enum에서 무시 됩니다.

사용 합니다 [맞춤](../../cpp/align-cpp.md) 키워드는 [__declspec](../../cpp/declspec.md) 한정자에서 허용 되지 않습니다는 `enum`합니다. 다음 샘플에서는 C4329 오류가 생성 됩니다.

```
// C4329.cpp
// compile with: /W1 /LD
enum __declspec(align(256)) TestEnum {   // C4329
   TESTVAL1,
   TESTVAL2,
   TESTVAL3
};
__declspec(align(256)) enum TestEnum1;
```