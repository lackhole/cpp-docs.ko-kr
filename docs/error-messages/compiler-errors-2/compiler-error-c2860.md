---
title: 컴파일러 오류 C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 7d468fb2a71ce23bcd527cb02663dd5f7b7eecad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302867"
---
# <a name="compiler-error-c2860"></a>컴파일러 오류 C2860

'void', '(void)'를 제외한 인수 형식일 수 없습니다

형식 `void` 다른 인수를 포함 하는 인수 형식으로 사용할 수 없습니다.

다음 샘플에서는 C2860 오류가 생성 됩니다.

```
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```