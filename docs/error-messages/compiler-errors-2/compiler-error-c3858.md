---
title: 컴파일러 오류 C3858
ms.date: 11/04/2016
f1_keywords:
- C3858
helpviewer_keywords:
- C3858
ms.assetid: 46e178d5-a55f-4ac6-a9dc-561fbcba5c1f
ms.openlocfilehash: b4246ba76b453e8cc841062a4184dc2cb02df479
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265453"
---
# <a name="compiler-error-c3858"></a>컴파일러 오류 C3858

'type': 현재 범위에서 다시 선언할 수 없습니다

형식은 두 번 동일한 범위에서에서 선언할 수 없습니다.

다음 샘플에서는 C3858를 생성합니다.

```
// C3858.cpp
// compile with: /LD
template <class T>
struct Outer
{
   struct Inner;
};

template <class T>
struct Outer<T>::Inner;   // C3858
// try the following line instead
// struct Outer<T>::Inner{};
```