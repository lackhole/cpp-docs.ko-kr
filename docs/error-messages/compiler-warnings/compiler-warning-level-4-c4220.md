---
title: 컴파일러 경고(수준 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: 781626e20f787bf582605ebd2d4943a7d5f2aa0c
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541914"
---
# <a name="compiler-warning-level-4-c4220"></a>컴파일러 경고(수준 4) C4220

varargs는 나머지 매개 변수와 일치 합니다.

기본 Microsoft 확장 (/Ze)에서 함수에 대 한 포인터는 유사 하지만 변수 인수가 있는 함수에 대 한 포인터와 일치 합니다.

## <a name="example"></a>예제

```c
// C4220.c
// compile with: /W4

int ( *pFunc1) ( int a, ... );
int ( *pFunc2) ( int a, int b);

int main()
{
   if ( pFunc1 != pFunc2 ) {};  // C4220
}
```

이러한 포인터는 ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 일치 하지 않습니다.