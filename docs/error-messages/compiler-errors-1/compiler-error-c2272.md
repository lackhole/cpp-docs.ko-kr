---
title: 컴파일러 오류 C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 1a5a1e47a721cb6edd795012cc45943e63708936
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388893"
---
# <a name="compiler-error-c2272"></a>컴파일러 오류 C2272

'function': 정적 멤버 함수에서 허용 되지 않습니다 한정자

A `static` 멤버 함수는 메모리 내 모델 지정자를 사용 하 여 같은 선언 [const](../../cpp/const-cpp.md) 또는 [volatile](../../cpp/volatile-cpp.md)에서 이러한 한정자는 허용 되지 않습니다 `static` 멤버 함수입니다.

다음 샘플에서는 C2272 오류가 생성 됩니다.

```
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```