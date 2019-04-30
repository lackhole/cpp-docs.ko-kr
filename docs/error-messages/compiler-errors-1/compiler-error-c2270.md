---
title: 컴파일러 오류 C2270
ms.date: 11/04/2016
f1_keywords:
- C2270
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
ms.openlocfilehash: 704d397f06432575b7db531039b4454d4716c54e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388919"
---
# <a name="compiler-error-c2270"></a>컴파일러 오류 C2270

'function': 한정자 비멤버 함수를 사용할 수 없습니다

비멤버 함수를 사용 하 여 선언 [const](../../cpp/const-cpp.md)를 [volatile](../../cpp/volatile-cpp.md), 또는 다른 메모리 모델 한정자입니다.

다음 샘플에서는 C2270 오류가 생성 됩니다.

```
// C2270.cpp
// compile with: /c
void func1(void) const;   // C2270, nonmember function

void func2(void);

class CMyClass {
public:
   void func2(void) const;
};
```