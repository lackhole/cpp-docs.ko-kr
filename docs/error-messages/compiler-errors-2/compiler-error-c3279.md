---
title: 컴파일러 오류 C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 3025dbf7c6bf4701218c2d9a956cae26d7180848
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757607"
---
# <a name="compiler-error-c3279"></a>컴파일러 오류 C3279

cli 네임스페이스에 선언된 클래스 템플릿의 명시적 인스턴스화 및 부분/명시적 특수화는 허용되지 않습니다.

`cli` 네임스페이스는 Microsoft에 의해 정의되며 의사(pseudo) 템플릿을 포함합니다. Microsoft C++ 컴파일러는이 네임 스페이스에서 사용자 정의, 부분 및 명시적 특수화와 클래스 템플릿의 명시적 인스턴스화를 허용 하지 않습니다.

다음 샘플에서는 C3279를 생성합니다.

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
