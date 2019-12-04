---
title: 컴파일러 오류 C2878
ms.date: 11/04/2016
f1_keywords:
- C2878
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
ms.openlocfilehash: faf50edfcddc64a75062672175ab7fbad63081c1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736311"
---
# <a name="compiler-error-c2878"></a>컴파일러 오류 C2878

' name ':이 이름의 네임 스페이스 또는 클래스가 없습니다.

정의 되지 않은 네임 스페이스 또는 클래스를 참조 했습니다.

다음 샘플에서는 C2878를 생성 합니다.

```cpp
// C2878.cpp
// compile with: /c
namespace A {}
namespace B = C;   // C2878 namespace C doesn't exist
namespace B = A;
```
