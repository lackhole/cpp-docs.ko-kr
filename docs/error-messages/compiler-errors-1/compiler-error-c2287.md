---
title: 컴파일러 오류 C2287
ms.date: 11/04/2016
f1_keywords:
- C2287
helpviewer_keywords:
- C2287
ms.assetid: 64556299-4e1f-4437-88b7-2464fc0b95bb
ms.openlocfilehash: f5493220c4380d1fd67b38995414f48a2ef72a41
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385825"
---
# <a name="compiler-error-c2287"></a>컴파일러 오류 C2287

'class': 상속 표현: 'representation1' 필수 'representation2' 보다 덜 일반적은

클래스는 필요한 것 보다 더 간단한 표현으로 선언 됩니다.

다음 샘플에서는 C2287 오류가 생성 됩니다.

```
// C2287.cpp
// compile with: /vmg /c
class __single_inheritance X;
class __single_inheritance Y;

struct A { };
struct B { };
struct X : A, B { };  // C2287  X uses multiple inheritance
struct Y : A { };  // OK
```