---
title: 컴파일러 오류 C2913
ms.date: 11/04/2016
f1_keywords:
- C2913
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
ms.openlocfilehash: deeabdb08f4b0fb3cd722d5d33a4d2cfffb15d61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256949"
---
# <a name="compiler-error-c2913"></a>컴파일러 오류 C2913

명시적 특수화 'declaration' 클래스 템플릿의 특수화 아닙니다.

템플릿이 아닌 클래스를 특수화할 수 없습니다.

다음 샘플에서는 C2913 오류가 생성 됩니다.

```
// C2913.cpp
// compile with: /c
class X{};
template <class T> class Y{};

template<> class X<int> {};   // C2913
template<> class Y<int> {};
```