---
title: 컴파일러 오류 C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 9ac8f5e5edb1a6ed7314c5b5d125fcc9bfbe67de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378923"
---
# <a name="compiler-error-c2879"></a>컴파일러 오류 C2879

'symbol':만 기존 네임 스페이스 별칭 정의 네임 스페이스로 대체 이름을 지정할 수 있습니다

만들 수 없습니다는 [네임 스페이스 별칭](../../cpp/namespaces-cpp.md#namespace_aliases) 네임 스페이스 이외의 기호입니다.

다음 샘플에서는 C2879를 생성합니다.

```
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```