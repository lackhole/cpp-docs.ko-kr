---
title: 컴파일러 오류 C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: f2fcb75098f18ad113ba68959035b37d9cddd6e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388872"
---
# <a name="compiler-error-c2274"></a>컴파일러 오류 C2274

'type': 오른쪽에 사용할 수 없습니다 '.' 연산자

형식 멤버 액세스 (.) 연산자의 오른쪽 피연산자로 나타납니다.

이 오류는 사용자 정의 형식 변환에 액세스 하려고 시도 하 여 발생할 수 있습니다. 키워드를 사용 하 여 `operator` 간의 기간 및 `type`합니다.

다음 샘플에서는 C2286을 생성합니다.

```
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```