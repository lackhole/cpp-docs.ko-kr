---
title: 컴파일러 경고 (수준 1) C4286
ms.date: 11/04/2016
f1_keywords:
- C4286
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
ms.openlocfilehash: ed2e6c10e35e53c6a67de9fecfce5da5ae429b93
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626667"
---
# <a name="compiler-warning-level-1-c4286"></a>컴파일러 경고 (수준 1) C4286

' type1 ': 줄 번호에서 기본 클래스 (' type2 ')에 의해 catch 되었습니다.

지정 된 예외 형식이 이전 처리기에 의해 처리 됩니다. 두 번째 catch의 형식은 첫 번째의 형식에서 파생 됩니다. 기본 클래스에 대 한 예외는 파생 클래스에 대 한 예외를 catch 합니다.

## <a name="example"></a>예제

```cpp
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```