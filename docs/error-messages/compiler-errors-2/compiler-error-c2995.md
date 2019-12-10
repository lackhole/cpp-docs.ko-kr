---
title: 컴파일러 오류 C2995
ms.date: 11/04/2016
f1_keywords:
- C2995
helpviewer_keywords:
- C2995
ms.assetid: a57cdfe0-b40b-4a67-a95c-1a49ace4842b
ms.openlocfilehash: 542a527cee5ffca7551685741a9dcaac2a442fda
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761405"
---
# <a name="compiler-error-c2995"></a>컴파일러 오류 C2995

'function': 함수 템플릿이 이미 정의되었습니다.

템플릿 클래스의 각 멤버 함수에 대한 정의가 하나뿐인지 확인합니다.

다음 샘플에서는 C2995를 생성합니다.

```cpp
// C2995.cpp
// compile with: /c
template <class T>
void Test(T x){}

template <class T> void Test(T x){}   // C2995
template <class T> void Test2(T x){}   // OK
```
