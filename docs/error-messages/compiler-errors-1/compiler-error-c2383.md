---
title: 컴파일러 오류 C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: e9c1774fe7cd4a6883aa79f384cc64521a57ed17
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448013"
---
# <a name="compiler-error-c2383"></a>컴파일러 오류 C2383

'*기호*':이 기호에 기본 인수를 사용할 수 없습니다

C++ 컴파일러 함수에 대 한 포인터에서 기본 인수를 허용 하지 않습니다.

이 코드는 Microsoft에서 허용 된 C++ Visual Studio 2005 이전 버전의 컴파일러 하지만 이제는 오류를 제공 합니다. 시각적 개체의 모든 버전에서 작동 하는 코드에 대 한 C++을 함수에 포인터 인수를 기본 값을 할당 하지 않습니다.

## <a name="example"></a>예제

다음 예제에서는 C2383를 생성 하 고 가능한 솔루션을 보여 줍니다.

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```