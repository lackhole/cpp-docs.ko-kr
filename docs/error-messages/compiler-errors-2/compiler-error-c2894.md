---
title: 컴파일러 오류 C2894
ms.date: 11/04/2016
f1_keywords:
- C2894
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
ms.openlocfilehash: 4184f6360e36a4e8ca0cfc55dc6d9c515cf655d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385968"
---
# <a name="compiler-error-c2894"></a>컴파일러 오류 C2894

'C' 링크가에 템플릿은 선언할 수 없습니다.

이 오류 때문일 수 있습니다 내에 정의 된 템플릿으로 `extern` "C" 블록입니다.

다음 샘플에서는 C2894를 생성합니다.

```
// C2894.cpp
extern "C" {
   template<class T> class stack {};   // C2894 fail

   template<class T> void f(const T &aT) {}   // C2894
}
```

다음 샘플에서는 C2894를 생성합니다.

```
// C2894b.cpp
// compile with: /c
extern "C" template<class T> void f(const T &aT) {}   // C2894

template<class T> void f2(const T &aT) {}   // OK
```