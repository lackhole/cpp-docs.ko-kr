---
title: 컴파일러 경고(수준 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: 84a0b27203cd43e8a8992c4ba599f1400c6909ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401399"
---
# <a name="compiler-warning-level-4-c4100"></a>컴파일러 경고(수준 4) C4100

'identifier': 참조 되지 않은 정식 매개 변수

형식 매개 변수는 함수 본문에서 참조 되지 않습니다. 참조 되지 않은 매개 변수가 무시 됩니다.

코드에서 소멸자를 호출할 때 C4100 발급할 수도 있습니다는 참조 되지 않는 기본 형식의 매개 변수입니다.  이 시각적 개체의 제한은 C++ 컴파일러.

다음 샘플에서는 C4100 오류가 생성 됩니다.

```
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```