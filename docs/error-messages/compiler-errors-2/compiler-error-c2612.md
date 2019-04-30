---
title: 컴파일러 오류 C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: b2d4888c1be39c4f48f0ca674426c7af612b9bb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379027"
---
# <a name="compiler-error-c2612"></a>컴파일러 오류 C2612

'char' 기본/멤버 이니셜라이저 목록에서 잘못 된 후행

마지막으로 기본 또는 멤버 이니셜라이저 목록에서 다음에 문자가 표시 합니다.

다음 샘플에서는 C2612 오류가 생성 됩니다.

```
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```