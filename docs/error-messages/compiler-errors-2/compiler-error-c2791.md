---
title: 컴파일러 오류 C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 66a111ea6fe2ca5acfbc473d19da62d9de67372a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360166"
---
# <a name="compiler-error-c2791"></a>컴파일러 오류 C2791

잘못 사용 했습니다 'super': 'class' 기본 클래스 없는 합니다.

키워드 [super](../../cpp/super.md) 모든 기본 클래스가 없는 클래스 멤버 함수의 컨텍스트에서 사용 되었습니다.

다음 샘플에서는 C2791를 생성합니다.

```
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```