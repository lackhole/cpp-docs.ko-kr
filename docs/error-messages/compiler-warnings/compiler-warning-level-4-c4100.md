---
title: 컴파일러 경고(수준 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: bcd51c66359d0553b7657d85f5b45ee22d4648ff
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991652"
---
# <a name="compiler-warning-level-4-c4100"></a>컴파일러 경고(수준 4) C4100

'identifier' : 참조되지 않은 정식 매개 변수

정식 매개 변수가 함수 본문에서 참조되지 않습니다. 참조되지 않은 매개 변수는 무시됩니다.

C4100은 코드가 기본 형식의 다른 참조되지 않은 매개 변수에서 소멸자를 호출할 경우에도 발생할 수 있습니다.  이는 Microsoft C++ 컴파일러의 제한 사항입니다.

다음 샘플에서는 C4100 오류가 발생하는 경우를 보여 줍니다.

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
