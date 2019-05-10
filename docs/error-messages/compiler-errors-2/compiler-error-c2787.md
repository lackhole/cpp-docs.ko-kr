---
title: 컴파일러 오류 C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 656fcd8a1a0429546189de8c3f01ab928c6333ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256869"
---
# <a name="compiler-error-c2787"></a>컴파일러 오류 C2787

'identifier': GUID가 없는이 개체와 연결 되었습니다.

합니다 [__uuidof](../../cpp/uuidof-operator.md) 연산자 연결 된 GUID 또는 사용자 정의 형식의 개체를 사용 하 여 사용자 정의 형식을 사용 합니다. 이 오류는 인수가 없는 GUID 사용 하 여 사용자 정의 형식인 경우에 발생 합니다.

다음 샘플에서는 C2787를 생성합니다.

```
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```