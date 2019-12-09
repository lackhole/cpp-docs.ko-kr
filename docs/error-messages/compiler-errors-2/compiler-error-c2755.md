---
title: 컴파일러 오류 C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: fcd4bb5d49f6f6e807ad240c377debb220138c93
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759557"
---
# <a name="compiler-error-c2755"></a>컴파일러 오류 C2755

' param ': 부분 특수화의 비 형식 매개 변수는 단순 식별자 여야 합니다.

형식이 아닌 매개 변수는 컴파일러가 컴파일 타임에 단일 식별자 또는 상수 값으로 확인할 수 있는 간단한 식별자 여야 합니다.

다음 샘플에서는 C2755를 생성 합니다.

```cpp
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```
