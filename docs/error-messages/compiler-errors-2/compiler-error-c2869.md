---
title: 컴파일러 오류 C2869
ms.date: 11/04/2016
f1_keywords:
- C2869
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
ms.openlocfilehash: 38ac73484814e0089b412938ffc2776872deff3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165556"
---
# <a name="compiler-error-c2869"></a>컴파일러 오류 C2869

'name': 네임 스페이스로 이미 정의 되어

네임 스페이스를 이미 사용 되는 이름을 다시 사용할 수 없습니다.

다음 샘플에서는 C2869 오류가 생성 됩니다.

```
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```