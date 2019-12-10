---
title: 컴파일러 오류 C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: 3d6cab186d4acf229a32620f33c9c86e807459dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751991"
---
# <a name="compiler-error-c2861"></a>컴파일러 오류 C2861

' function name ': 인터페이스 멤버 함수를 정의할 수 없습니다.

컴파일러가 interface 키워드를 발견 했거나 구조체를 인터페이스로 추론 했지만 멤버 함수 정의를 찾았습니다.  인터페이스는 멤버 함수에 대 한 정의를 포함할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2861를 생성 합니다.

```cpp
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```
