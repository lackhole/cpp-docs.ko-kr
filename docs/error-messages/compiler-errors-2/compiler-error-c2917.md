---
title: 컴파일러 오류 C2917
ms.date: 11/04/2016
f1_keywords:
- C2917
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
ms.openlocfilehash: 6926d96eccadacd427cc4d13b93db494809c3775
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406784"
---
# <a name="compiler-error-c2917"></a>컴파일러 오류 C2917

'name': 템플릿-매개 변수가 잘못되었습니다.

템플릿 매개 변수 목록에 템플릿 매개 변수가 아닌 식별자가 포함되어 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2917을 생성합니다.

```
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```