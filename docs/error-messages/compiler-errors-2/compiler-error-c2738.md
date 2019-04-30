---
title: 컴파일러 오류 C2738
ms.date: 11/04/2016
f1_keywords:
- C2738
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
ms.openlocfilehash: 8f8342f07d8062c5a1ec18d17423996c1b0dab39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360244"
---
# <a name="compiler-error-c2738"></a>컴파일러 오류 C2738

'declaration': 모호 하거나 't y'의 구성원이 아닙니다

함수를 잘못 선언 되었습니다.

다음 샘플에서는 C2738 오류가 생성 됩니다.

```
// C2738.cpp
struct A {
   template <class T> operator T*();
   // template <class T> operator T();
};

template <>
A::operator int() {   // C2738

// try the following line instead
// A::operator int*() {

// or use the commented member declaration

   return 0;
}
```