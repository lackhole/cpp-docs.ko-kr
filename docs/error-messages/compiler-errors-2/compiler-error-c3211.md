---
title: 컴파일러 오류 C3211
ms.date: 11/04/2016
f1_keywords:
- C3211
helpviewer_keywords:
- C3211
ms.assetid: 85e33fed-3b59-4315-97e6-20d31c6a985a
ms.openlocfilehash: 6de2129a1cdd6391245148816b29faa65d7e8721
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311763"
---
# <a name="compiler-error-c3211"></a>컴파일러 오류 C3211

'explicit specialization': 명시적 특수화에 부분 특수화 구문이 사용되고 있습니다. template <>을 사용하세요.

명시적 특수화의 형식이 잘못되었습니다.

다음 샘플에서는 C3211을 생성합니다.

```
// C3211.cpp
// compile with: /LD
template<class T>
struct s;

template<class T>
// use the following line instead
// template<>
struct s<int>{};   // C3211
```