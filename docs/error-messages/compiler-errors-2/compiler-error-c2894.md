---
title: 컴파일러 오류 C2894
ms.date: 11/04/2016
f1_keywords:
- C2894
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
ms.openlocfilehash: ffc87008c1874f8f5c7e275778237f611dcbb5af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760825"
---
# <a name="compiler-error-c2894"></a>컴파일러 오류 C2894

템플릿에 ' C ' 링크가 있도록 선언할 수 없습니다.

이 오류는 `extern` "C" 블록 내에 정의 된 템플릿에 의해 발생할 수 있습니다.

다음 샘플에서는 C2894를 생성 합니다.

```cpp
// C2894.cpp
extern "C" {
   template<class T> class stack {};   // C2894 fail

   template<class T> void f(const T &aT) {}   // C2894
}
```

다음 샘플에서는 C2894를 생성 합니다.

```cpp
// C2894b.cpp
// compile with: /c
extern "C" template<class T> void f(const T &aT) {}   // C2894

template<class T> void f2(const T &aT) {}   // OK
```
