---
title: 컴파일러 경고(수준 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 439c4976f25688fd9220c3f58ceb933266b5f15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187511"
---
# <a name="compiler-warning-level-1-c4342"></a>컴파일러 경고(수준 1) C4342

동작 변경: '*함수*' 호출 되었지만 이전 버전에서는 멤버 연산자가 호출

시각적 개체의 버전에서 C++ Visual Studio 2002 년 이전 멤버를 호출 되지만이 동작이 변경 되었습니다 및 컴파일러는 이제 가장 일치 하는 네임 스페이스 범위에서 찾습니다.

멤버 연산자가 있으면 컴파일러가 이전에 고려 하지 않습니다 모든 네임 스페이스 범위 연산자입니다. 네임 스페이스 범위에 더 적합 한 경우 현재 컴파일러 올바르게 호출 하 여, 하지만 이전 컴파일러를 고려 하지 않습니다.

이 경고는 현재 버전으로 코드를 성공적으로 포트 후 해제 되어야 합니다.  컴파일러는 코드에 대 한이 경고를 생성 하는 거짓 긍정을 제공할 수 있는 동작이 변경 되지 않습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

다음 샘플에서는 C4342 오류가 생성 됩니다.

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```