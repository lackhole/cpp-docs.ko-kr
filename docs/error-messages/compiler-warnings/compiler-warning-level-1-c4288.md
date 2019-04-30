---
title: 컴파일러 경고(수준 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: d8769f5663ca0bde9048e52d4579012dfccab0a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207097"
---
# <a name="compiler-warning-level-1-c4288"></a>컴파일러 경고(수준 1) C4288

비표준 확장이 사용 됨: 'var': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위 외부에 외부 범위에 있는 선언과 충돌

로 컴파일하는 경우 [/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **/zc: forscope-** 에 선언 된 변수를 **에 대 한** 루프 된 후 사용 하는 [에 대 한](../../cpp/for-statement-cpp.md)-루프 범위. 에 대 한 Microsoft 확장은 C++ 언어가이 변수를 범위에 남아 있으며 C4288 알려 변수의 첫 번째 선언은 사용 되지 않습니다.

참조 [/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 에서 Microsoft 확장을 지정 하는 방법에 대 한 내용은 **에 대 한** /Ze를 사용 하 여 루프입니다.

다음 샘플에서는 C4288 오류가 생성 됩니다.

```
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```