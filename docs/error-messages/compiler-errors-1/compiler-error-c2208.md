---
title: 컴파일러 오류 C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 208e15e98a05089c0e9b1c98400f5267e4f3a48f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758933"
---
# <a name="compiler-error-c2208"></a>컴파일러 오류 C2208

' type ':이 형식을 사용 하 여 정의 된 멤버가 없습니다.

형식 이름으로 확인 하는 식별자는 집계 선언에 있지만 컴파일러에서 멤버를 선언할 수 없습니다.

다음 샘플에서는 C2208를 생성 합니다.

```cpp
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```
