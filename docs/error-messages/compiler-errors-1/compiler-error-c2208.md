---
title: 컴파일러 오류 C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 7970ba5d8d2b19bd6e330fad1879880fc5cbf32d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400450"
---
# <a name="compiler-error-c2208"></a>컴파일러 오류 C2208

'type':이 형식을 사용 하 여 정의 된 멤버

형식 이름으로 확인 되는 식별자는 집계 선언 있지만 컴파일러는 멤버를 선언할 수 없습니다.

다음 샘플에서는 C2208 오류가 생성 됩니다.

```
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```