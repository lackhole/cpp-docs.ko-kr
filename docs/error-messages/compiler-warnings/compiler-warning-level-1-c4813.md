---
title: 컴파일러 경고(수준 1) C4813
ms.date: 11/04/2016
f1_keywords:
- C4813
helpviewer_keywords:
- C4813
ms.assetid: c30bf877-ab04-4fe4-897e-8162092426f0
ms.openlocfilehash: c6aaf3cc8e17cd1be1d9c964c03bb18b3bb0ff77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410327"
---
# <a name="compiler-warning-level-1-c4813"></a>컴파일러 경고(수준 1) C4813

'function': 지역 클래스의 friend 함수를 미리 선언해야 합니다.

내부 클래스의 friend 함수가 외부 클래스에서 선언되지 않았습니다.

다음 샘플에서는 C4813을 생성합니다.

```
// C4813.cpp
// compile with: /W1 /LD
void MyClass()
{
   // void func();
   class InnerClass
   {
      friend void func();   // C4813 uncomment declaration above
   };
}
```