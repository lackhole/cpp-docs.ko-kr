---
title: 컴파일러 오류 C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: f5cecd847837214f6392bead624e5377cef4833f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758647"
---
# <a name="compiler-error-c2535"></a>컴파일러 오류 C2535

' identifier ': 멤버 함수를 이미 정의 했거나 선언 했습니다.

이 오류는 오버 로드 된 함수의 여러 정의 또는 선언에서 동일한 형식 매개 변수 목록을 사용 하 여 발생할 수 있습니다.

Dispose 함수로 인해 C2535를 가져오는 경우 자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 를 참조 하세요.

다음 샘플에서는 C2535를 생성 합니다.

```cpp
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```
