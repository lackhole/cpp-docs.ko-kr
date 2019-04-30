---
title: 컴파일러 오류 C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 5d9becbdfad2afc8940a9e1ded08a15842607e4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385929"
---
# <a name="compiler-error-c3640"></a>컴파일러 오류 C3640

'member': 지역 클래스 참조 또는 가상 멤버 함수를 정의 해야 합니다

컴파일러는 특정 함수를 정의할 수 필요 합니다.

다음 샘플에서는 C3640 오류가 생성 됩니다.

```
// C3640.cpp
void f()
{
   struct S
   {
      virtual void f1();   // C3640
      // Try the following line instead:
      // virtual void f1(){}
   };
}
```