---
title: 컴파일러 오류 C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f2ed5c49a9f8243fd5c9c302caf2876493c26bc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388945"
---
# <a name="compiler-error-c2273"></a>컴파일러 오류 C2273

'type': '->' 연산자의 오른쪽에 사용할 수 없습니다

오른쪽 피연산자로 형식이 표시를 `->` 연산자입니다.

이 오류는 사용자 정의 형식 변환에 액세스 하려고 시도 하 여 발생할 수 있습니다. 키워드를 사용 하 여 `operator` 간의-> 및 `type`합니다.

다음 샘플에서는 C2273를 생성합니다.

```
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```