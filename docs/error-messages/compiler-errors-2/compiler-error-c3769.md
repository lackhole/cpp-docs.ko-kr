---
title: 컴파일러 오류 C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 68845b446541b8d76ebd2b873a34b7e32ef314e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400190"
---
# <a name="compiler-error-c3769"></a>컴파일러 오류 C3769

'type': 중첩된 된 클래스의 이름은 바로 바깥쪽의 클래스를 사용할 수 없습니다

중첩된 클래스 바로 바깥쪽 클래스와 동일한 이름을 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플 C3769를 생성합니다.

```
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```