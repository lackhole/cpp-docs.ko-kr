---
title: 컴파일러 경고(수준 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a3ce4c81a86920baddfc1b277df0236a96254be4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207398"
---
# <a name="compiler-warning-level-1-c4258"></a>컴파일러 경고(수준 1) C4258

'variable': 정의 루프 무시 됩니다. 바깥쪽 범위에서 정의 사용 하는 "

아래 [/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 [/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)에 정의 된 변수를 [에 대 한](../../cpp/for-statement-cpp.md) 루프 후 범위를 벗어납니다 합니다 **에 대 한** 루프가 종료 합니다. 루프 변수를 바깥쪽 루프에 정의 되어 있지만 이름이 같은 변수를 포함 하는 범위에서 다시 사용 하는 경우이 경고가 발생 합니다 **에 대 한** 루프입니다. 예를 들어:

```
// C4258.cpp
// compile with: /Zc:forScope /W1
int main()
{
   int i;
   {
      for (int i =0; i < 1; i++)
         ;
      i = 20;   // C4258 i (in for loop) has gone out of scope
   }
}
```