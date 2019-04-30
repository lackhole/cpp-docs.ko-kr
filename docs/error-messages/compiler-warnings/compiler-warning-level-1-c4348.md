---
title: 컴파일러 경고(수준 1) C4348
ms.date: 11/04/2016
f1_keywords:
- C4348
helpviewer_keywords:
- C4348
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
ms.openlocfilehash: b39d5a596594367d1ca2aea17d9a752c991d06be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352897"
---
# <a name="compiler-warning-level-1-c4348"></a>컴파일러 경고(수준 1) C4348

'type': 기본 매개 변수 재정의: 매개 변수 번호

템플릿 매개 변수를 다시 정의 되었습니다.

다음 샘플에서는 C4348 오류가 생성 됩니다.

```
// C4348.cpp
// compile with: /LD /W1
template <class T=int> struct A;   // forward declaration

template <class T=int> struct A { };
// C4348, redefinition of default parameter
// try the following line instead
// template <class T> struct A { };
```