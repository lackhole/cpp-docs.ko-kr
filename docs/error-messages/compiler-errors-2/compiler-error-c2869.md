---
title: 컴파일러 오류 C2869
ms.date: 11/04/2016
f1_keywords:
- C2869
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
ms.openlocfilehash: c543a0a4afc0d24205e5afd57cf6ca0732f3edf4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755046"
---
# <a name="compiler-error-c2869"></a>컴파일러 오류 C2869

' name ': 이미 네임 스페이스로 정의 되었습니다.

이미 네임 스페이스로 사용 된 이름을 다시 사용할 수 없습니다.

다음 샘플에서는 C2869를 생성 합니다.

```cpp
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```
