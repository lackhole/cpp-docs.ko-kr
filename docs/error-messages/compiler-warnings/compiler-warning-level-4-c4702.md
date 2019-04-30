---
title: 컴파일러 경고(수준 4) C4702
ms.date: 11/04/2016
f1_keywords:
- C4702
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
ms.openlocfilehash: 96ae3a0742db5e3a5006f031ce62beb281c38ccd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395250"
---
# <a name="compiler-warning-level-4-c4702"></a>컴파일러 경고(수준 4) C4702

접근할 수 없는 코드

이 경고는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과: 접근할 수 없는 코드입니다. 보고 합니다 (c4702에 생성 됩니다 (백 엔드) 컴파일러에서 접근할 수 없는 코드를 감지 하면에서는 수준 4 경고입니다.

시각적 개체의 Visual Studio.NET 2003와 Visual Studio.NET 버전에 적용 되는 코드에 대 한 C++접근할 수 없는 코드 제거 하거나 모든 소스 코드에 몇 가지 흐름을 실행 하 여 연결할 수 있는지 확인 합니다.

## <a name="example"></a>예제

다음 샘플을 보고 합니다 (c4702 발생 합니다.

```
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>예제

사용 하 여 컴파일하면 **/GX**, **데 /EHc**, **/EHsc**, 또는 **/EHac** extern C 함수를 사용 하 여 코드 수 없게 접근할 수 없는 때문에 extern C catch 블록을 연결할 수 없어서, 고, 그렇지 않으면 함수는 가정 합니다.  함수가 throw 할 수 있으므로이 경고는 유효 하는 것이 생각을 하는 경우 사용 하 여 컴파일하면 **/EHa** 하거나 **/EHs**throw 된 예외에 따라 합니다.

자세한 내용은 [/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md) 자세한 내용은 합니다.

다음 샘플을 보고 합니다 (c4702 발생 합니다.

```
// C4702b.cpp
// compile with: /W4 /EHsc
#include <iostream>

using namespace std;
extern "C" __declspec(dllexport) void Function2(){}

int main() {
   try {
      Function2();
   }
   catch (...) {
      cout << "Exp: Function2!" << endl;   // C4702
   }
}
```