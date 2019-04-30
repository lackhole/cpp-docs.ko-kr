---
title: 컴파일러 경고(수준 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 5ec0aea543053d699db7483df7dd7ea91b3af715
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363819"
---
# <a name="compiler-warning-level-1-c4716"></a>컴파일러 경고(수준 1) C4716

'function'은 값을 반환해야 합니다.

지정된 된 함수 값을 반환 하지 않았습니다.

해당 하는 반환 값 없이 반환 명령을 사용 하는 함수만 반환 형식의 void 수 있습니다.

이 함수가 호출 될 때 정의 되지 않은 값을 반환 됩니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다.

다음 샘플에서는 C4716 오류가 생성 됩니다.

```
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```