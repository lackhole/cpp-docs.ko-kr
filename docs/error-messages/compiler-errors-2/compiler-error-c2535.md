---
title: 컴파일러 오류 C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: b2b5452cfe59284d56b019674ffbabbda0dc62d1
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344715"
---
# <a name="compiler-error-c2535"></a>컴파일러 오류 C2535

'identifier': 이미 정의 되거나 선언 된 멤버 함수

이 오류는 여러 개 정의 또는 오버 로드 된 함수의 선언에 동일한 형식 매개 변수 목록을 사용 하 여 발생할 수 있습니다.

Dispose 함수로 인해 c2535 참조 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 자세한 내용은 합니다.

다음 샘플에서는 C2535를 생성합니다.

```
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```