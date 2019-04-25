---
title: 컴파일러 오류 C2735
ms.date: 11/04/2016
f1_keywords:
- C2735
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
ms.openlocfilehash: 73d5f61b5f86153db74a970d97b4656fb662bdad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152451"
---
# <a name="compiler-error-c2735"></a>컴파일러 오류 C2735

정식 매개 변수 형식 지정자에는 'keyword' 키워드를 사용할 수 없습니다.

키워드가이 컨텍스트에서 올바르지 않습니다.

다음 샘플에서는 C2735 오류가 생성 됩니다.

```
// C2735.cpp
void f(inline int){}   // C2735
```