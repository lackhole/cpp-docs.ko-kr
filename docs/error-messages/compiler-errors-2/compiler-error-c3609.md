---
title: 컴파일러 오류 C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 27eba3df800c42cc53a7031e958a675c84255440
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780979"
---
# <a name="compiler-error-c3609"></a>컴파일러 오류 C3609

'member': 봉인 함수 또는 최종 함수는 virtual이어야 합니다.

[봉인](../../extensions/sealed-cpp-component-extensions.md) 하 고 [최종](../../cpp/final-specifier.md) 키워드는 표시 된 클래스, 구조체 또는 멤버 함수에만 사용할 수 `virtual`입니다.

다음 샘플에서는 C3609 오류가 발생하는 경우를 보여 줍니다.

```
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
