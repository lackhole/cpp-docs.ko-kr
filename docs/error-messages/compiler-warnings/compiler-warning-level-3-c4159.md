---
title: 컴파일러 경고 (수준 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: e898af8f109ed23bd1784df7b39c174bbed675f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402283"
---
# <a name="compiler-warning-level-3-c4159"></a>컴파일러 경고 (수준 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma(pop,...): 이전에 푸시한 식별자를 팝 했습니다 '*식별자*'

## <a name="remarks"></a>설명

소스 코드에 **푸시** 뒤에 pragma에 대 한 식별자를 사용 하 여 명령을 **pop** 식별자 없이 명령입니다. 따라서 *식별자* 표시 되 면, 및 이후 사용 됩니다 *식별자* 예기치 않은 동작이 발생할 수 있습니다.

## <a name="example"></a>예제

이 경고를 방지 하려면에 식별자를 제공 합니다 **pop** 명령입니다. 예를 들어:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```