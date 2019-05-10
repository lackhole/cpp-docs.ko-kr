---
title: 컴파일러 오류 C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: d7c55ede285d027b1a65b33adbf6407df243f068
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390609"
---
# <a name="compiler-error-c3824"></a>컴파일러 오류 C3824

'member':이 형식 (함수 매개 변수, 반환 형식 또는 정적 멤버)이 컨텍스트에서 나타날 수 없습니다

고정 포인터는 함수 매개 변수, 반환 형식 수 없거나 또는 선언 `static`합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3824 오류가 생성 됩니다.

```
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
