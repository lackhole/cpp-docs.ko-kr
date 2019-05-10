---
title: 컴파일러 오류 C2724
ms.date: 11/04/2016
f1_keywords:
- C2724
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
ms.openlocfilehash: 3014a12767cb9a73dc65852c544b7ac9574b9a52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383063"
---
# <a name="compiler-error-c2724"></a>컴파일러 오류 C2724

'identifier': 'static' 해서는 안 파일 범위에서 정의 된 멤버 함수에서

외부 링크가 있는 정적 멤버 함수를 선언 해야 합니다.

다음 샘플에서는 C2724를 생성합니다.

```
// C2724.cpp
class C {
   static void func();
};

static void C::func(){};   // C2724
// try the following line instead
// void C::func(){};
```