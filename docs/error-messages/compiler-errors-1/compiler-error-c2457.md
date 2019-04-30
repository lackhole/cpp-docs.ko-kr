---
title: 컴파일러 오류 C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: a08ac9f9cfbc332b90ad16c663349ee227427278
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347105"
---
# <a name="compiler-error-c2457"></a>컴파일러 오류 C2457

> '*매크로*': 미리 정의 된 매크로 함수 본문 외부에서 사용할 수 없습니다

와 같은 미리 정의 된 매크로 사용 하려는 [ &#95; &#95;함수&#95;&#95;](../../preprocessor/predefined-macros.md), 전역 공간에서입니다.

## <a name="example"></a>예제

다음 샘플 C2457 생성 하 고 또한 올바른 사용법을 보여 줍니다.

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```