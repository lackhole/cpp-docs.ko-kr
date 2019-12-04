---
title: 컴파일러 오류 C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: 47363da66416c326755cad12fe4cfd448e3154e2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741731"
---
# <a name="compiler-error-c3824"></a>컴파일러 오류 C3824

' member ':이 형식은이 컨텍스트 (함수 매개 변수, 반환 형식 또는 정적 멤버)에 사용할 수 없습니다.

고정 포인터는 함수 매개 변수, 반환 형식 또는 선언 된 `static`일 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3824를 생성 합니다.

```cpp
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
