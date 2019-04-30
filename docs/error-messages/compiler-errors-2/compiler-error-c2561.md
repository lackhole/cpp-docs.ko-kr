---
title: 컴파일러 오류 C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: 8350c5baf129b88c178be280d2da7fe856c6cf57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368424"
---
# <a name="compiler-error-c2561"></a>컴파일러 오류 C2561

'identifier': 함수가 값을 반환 해야 합니다

함수 정의 포함 되지 않은 값을 반환 하도록 선언 된 함수는 `return` 문.

이 오류는 잘못 된 함수 프로토타입에서 발생할 수 있습니다.

1. 함수 값을 반환 하지 않는 경우 함수 반환 형식이 있는 선언 [void](../../cpp/void-cpp.md)합니다.

1. 프로토타입에서 선언 된 형식의 값을 반환 하는 함수의 가능한 모든 분기를 확인 합니다.

1. C++반환 값을 저장 하는 인라인 어셈블리 루틴을 포함 하는 함수는 `AX` 등록 return 문이 해야 할 수 있습니다. 값을 복사 `AX` 를 임시 변수에 함수에서 해당 변수를 반환 합니다.

다음 샘플에서는 C2561 오류가 생성 됩니다.

```
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```