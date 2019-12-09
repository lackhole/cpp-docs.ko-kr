---
title: 컴파일러 오류 C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: fb019d729bc100296742b15ba95460fe0e404673
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759882"
---
# <a name="compiler-error-c2364"></a>컴파일러 오류 C2364

' type ': 사용자 지정 특성의 형식이 잘못 되었습니다.

사용자 지정 특성에 대 한 명명 된 인수는 컴파일 시간 상수로 제한 됩니다. 예를 들어 정수 계열 형식 (int, char 등), System:: Type ^ 및 System:: Object ^입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2364를 생성 합니다.

```cpp
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```
