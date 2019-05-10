---
title: 컴파일러 오류 C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: 1872672e776ad13bf16be5ae69729f4f68d8f3b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302035"
---
# <a name="compiler-error-c2357"></a>컴파일러 오류 C2357

'identifier': 'type' 형식 함수 여야

코드의 버전을 선언 합니다 `atexit` 버전이 일치 하지 않는 함수는 컴파일러에서 내부적으로 선언 합니다. 선언 `atexit` 다음과 같습니다.

```
int __cdecl atexit(void (__cdecl *)());
```

자세한 내용은 [init_seg](../../preprocessor/init-seg.md)합니다.

다음 샘플에서는 C2357 오류가 생성 됩니다.

```
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```