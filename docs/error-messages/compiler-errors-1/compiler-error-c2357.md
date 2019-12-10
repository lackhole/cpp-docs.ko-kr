---
title: 컴파일러 오류 C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: ce1926468bac7e44485be5c0a0944fdf12dce3d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759921"
---
# <a name="compiler-error-c2357"></a>컴파일러 오류 C2357

' identifier ': ' type ' 형식의 함수 여야 합니다.

코드에서 컴파일러가 내부적으로 선언 된 버전과 일치 하지 않는 `atexit` 함수의 버전을 선언 합니다. 다음과 같이 `atexit`를 선언 합니다.

```
int __cdecl atexit(void (__cdecl *)());
```

자세한 내용은 [init_seg](../../preprocessor/init-seg.md)를 참조 하세요.

다음 샘플에서는 C2357를 생성 합니다.

```cpp
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```
