---
title: 컴파일러 경고(수준 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: dee087b73bf032a68daf0527ea584efcc7579361
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401087"
---
# <a name="compiler-warning-level-4-c4232"></a>컴파일러 경고(수준 4) C4232

비표준 확장이 사용 됨: 'identifier': dllimport 'dllimport의 주소가 정적이 아니거나, identity 보장 되지 않습니다

Microsoft 확장 (/Ze)에서는 제공할 수로 선언 된 함수의 주소가 비고정 값을 **dllimport** 한정자입니다. ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)),이 인해 오류가 발생 합니다.

다음 샘플에서는 C4232 오류가 생성 됩니다.

```
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```