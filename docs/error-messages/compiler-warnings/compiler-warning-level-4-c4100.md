---
title: 컴파일러 경고(수준 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: 80794d270b40a8f40d44630da70455c015158423
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541239"
---
# <a name="compiler-warning-level-4-c4100"></a>컴파일러 경고(수준 4) C4100

' identifier ': 참조 되지 않은 정식 매개 변수입니다.

정식 매개 변수가 함수 본문에서 참조 되지 않습니다. 참조 되지 않은 매개 변수는 무시 됩니다.

C4100는 코드에서 기본 형식의 참조 되지 않은 매개 변수에 대해 소멸자를 호출 하는 경우에도 실행 될 수 있습니다.  이는 Microsoft C++ 컴파일러의 제한 사항입니다.

다음 샘플에서는 C4100를 생성 합니다.

```cpp
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