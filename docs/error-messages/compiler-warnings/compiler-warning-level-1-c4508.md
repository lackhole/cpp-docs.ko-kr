---
title: 컴파일러 경고(수준 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: c96db3d4bd1124c96b22363531b7739d0757b613
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160811"
---
# <a name="compiler-warning-level-1-c4508"></a>컴파일러 경고(수준 1) C4508

'function': 함수에 값을 반환 해야 'void' 반환 형식으로 간주 됩니다.

함수는 지정 된 반환 형식이 없습니다. 이 경우 C4430도 발생 하 고 컴파일러 구현 C4430 (기본값은 int)에서 보고 된 문제를 해결 합니다.

이 경고를 해결 하려면 함수의 반환 형식을 명시적으로 선언 합니다.

다음 샘플에서는 C4508 오류가 생성 됩니다.

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```