---
title: 컴파일러 오류 C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6c7238faf94a2493894534ae5684634b65bb4342
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736297"
---
# <a name="compiler-error-c2879"></a>컴파일러 오류 C2879

' symbol ': 네임 스페이스 별칭 정의에 따라 기존 네임 스페이스에만 다른 이름을 지정할 수 있습니다.

네임 스페이스 이외의 기호에는 [네임 스페이스 별칭](../../cpp/namespaces-cpp.md#namespace_aliases) 을 만들 수 없습니다.

다음 샘플에서는 C2879를 생성 합니다.

```cpp
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```
