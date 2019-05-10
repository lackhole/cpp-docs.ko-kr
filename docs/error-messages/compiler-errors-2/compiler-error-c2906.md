---
title: 컴파일러 오류 C2906
ms.date: 11/04/2016
f1_keywords:
- C2906
helpviewer_keywords:
- C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
ms.openlocfilehash: 621b31cf362c1dcc740390cf9e405b7da3f05da8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378520"
---
# <a name="compiler-error-c2906"></a>컴파일러 오류 C2906

'specialization': 명시적 특수화 'template<>' 필요

템플릿의 명시적 특수화에 대 한 새 구문을 사용 해야 합니다.

다음 샘플에서는 C2906 오류가 생성 됩니다.

```
// C2906.cpp
// compile with: /c
template<class T> class X{};   // primary template
class X<int> { }   // C2906
template<> class X<int> { };   // new syntax
```