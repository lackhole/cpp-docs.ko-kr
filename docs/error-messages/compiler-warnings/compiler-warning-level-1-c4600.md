---
title: 컴파일러 경고 (수준 1) C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: 6eae37d006b5fcd6bd1c5e2993f1752c0534ee45
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966221"
---
# <a name="compiler-warning-level-1-c4600"></a>컴파일러 경고 (수준 1) C4600

\#pragma ' macro name ': 비어 있지 않은 유효한 문자열이 필요 합니다.

[Pop_macro](../../preprocessor/pop-macro.md) 또는 [push_macro](../../preprocessor/push-macro.md)를 사용 하 여 매크로 이름을 푸시 하거나 pop 할 때 빈 문자열을 지정할 수 없습니다.

다음 샘플에서는 C4600를 생성 합니다.

```cpp
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```