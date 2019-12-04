---
title: 컴파일러 오류 C2917
ms.date: 11/04/2016
f1_keywords:
- C2917
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
ms.openlocfilehash: 9f4b82c1138326bad93d3836d6a77c55f2f546e4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761047"
---
# <a name="compiler-error-c2917"></a>컴파일러 오류 C2917

'name': 템플릿-매개 변수가 잘못되었습니다.

템플릿 매개 변수 목록에 템플릿 매개 변수가 아닌 식별자가 포함되어 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2917을 생성합니다.

```cpp
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```
