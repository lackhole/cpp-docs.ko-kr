---
title: 컴파일러 경고(수준 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: 84d24d95053b962c1776dc18576e4ed236b63469
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363871"
---
# <a name="compiler-warning-level-1-c4087"></a>컴파일러 경고(수준 1) C4087

'function': 'void' 매개 변수 목록을 사용하여 선언되었습니다.

함수 선언에 정식 매개 변수가 없지만 함수 호출에 실제 매개 변수가 있습니다. 추가 매개 변수는 함수 호출 규칙에 따라 전달됩니다.

이 경고는 C 컴파일러용입니다.

## <a name="example"></a>예제

```
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```