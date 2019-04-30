---
title: 컴파일러 경고(수준 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: fcfefd5b858df653551e7f3061a41d168c8ff3f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397226"
---
# <a name="compiler-warning-level-1-c4600"></a>컴파일러 경고(수준 1) C4600

\#pragma '매크로 name': 올바른 비어 있지 않은 문자열이 필요 합니다.

푸시 또는 매크로 이름을 사용 하 여 팝 하는 경우 빈 문자열을 지정할 수 없습니다는 [pop_macro](../../preprocessor/pop-macro.md) 하거나 [push_macro](../../preprocessor/push-macro.md)합니다.

다음 샘플에서는 C4600 오류가 생성 됩니다.

```
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```