---
title: 컴파일러 오류 C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: bcc801bb5802598e936d577f08729214bb7e13a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759791"
---
# <a name="compiler-error-c2768"></a>컴파일러 오류 C2768

' function ': 명시적 템플릿 인수를 잘못 사용 했습니다.

컴파일러는 함수 정의가 함수 템플릿의 명시적 특수화 여야 하는지 또는 함수 정의가 새 함수에 대해 이어야 하는지 여부를 확인할 수 없습니다.

이 오류는 컴파일러 규칙 향상의 일환으로 Visual Studio .NET 2003에서 도입 되었습니다.

다음 샘플에서는 C2768를 생성 합니다.

```cpp
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```
