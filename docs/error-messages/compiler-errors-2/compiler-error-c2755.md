---
title: 컴파일러 오류 C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: c2238058dc4b7df6bbe33e98d6ccde996f36b782
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227974"
---
# <a name="compiler-error-c2755"></a>컴파일러 오류 C2755

'param': 부분 특수화의 비형식 매개 변수는 단순 식별자 여야 합니다.

비형식 매개 변수는 단순 식별자를 컴파일러가 컴파일 시간에 단일 식별자 또는 상수 값을 확인할 수 있어야 합니다.

다음 샘플에서는 C2755 오류가 생성 됩니다.

```
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```