---
title: 컴파일러 경고(수준 1) C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: bcadf31eda079ebb8ea7a496efe4c945e16b1ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160759"
---
# <a name="compiler-warning-level-1-c4532"></a>컴파일러 경고(수준 1) C4532

'continue': 종료 처리 하는 동안 __finally/finally 블록 밖으로 점프 동작이 정의 되지 않았습니다

컴파일러가 다음 키워드 중 하나를 발견 했습니다.

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

점프를 일으키는 [__finally](../../cpp/try-finally-statement.md) 또는 [마지막으로](../../dotnet/finally.md) 비정상적으로 종료 하는 동안 차단 합니다.

종료 처리기를 실행 하는 동안 스택이 되는 동안 예외가 발생 하는 경우 및 (를 `__finally` finally 블록 또는), 코드 밖으로 점프 하 고는 `__finally` 되기까지 차단는 `__finally` 블록 종료 동작이 정의 되지 않습니다. 예외를 제대로 처리 되지 제어는 해제 코드를 반환 하지 않을 수 있습니다.

개 이동 해야 하는 경우는 **__finally** 차단, 먼저 비정상적인 종료를 확인 합니다.

다음 샘플에서는 C4532; 단순히 주석 사용 하 여 경고를 해결 하려면 점프 문 처리 합니다.

```
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```