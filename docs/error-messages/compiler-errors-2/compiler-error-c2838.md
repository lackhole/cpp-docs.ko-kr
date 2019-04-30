---
title: 컴파일러 오류 C2838
ms.date: 11/04/2016
f1_keywords:
- C2838
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
ms.openlocfilehash: 1482efa8b018914a4ebc509464622726ae9ebb20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383011"
---
# <a name="compiler-error-c2838"></a>컴파일러 오류 C2838

'member': 멤버 선언의 정규화 된 이름이 잘못 되었습니다.

클래스, 구조체 또는 공용 구조체에는 다른 클래스, 구조체 또는 공용 구조체의 멤버를 다시 선언 정규화 된 이름을 사용 합니다.

다음 샘플에서는 C2838 오류가 생성 됩니다.

```
// C2838.cpp
// compile with: /c
class Bellini {
public:
    void Norma();
};

class Bottesini {
   Bellini::Norma();  // C2838
};
```