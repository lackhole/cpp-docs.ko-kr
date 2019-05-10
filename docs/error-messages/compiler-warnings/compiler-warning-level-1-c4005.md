---
title: 컴파일러 경고 (수준 1) C4005
ms.date: 11/04/2016
f1_keywords:
- C4005
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
ms.openlocfilehash: 76aab2160bd5f7918771dcf63b7297a869da751e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187341"
---
# <a name="compiler-warning-level-1-c4005"></a>컴파일러 경고 (수준 1) C4005

'identifier': 매크로 재정의

매크로 식별자를 두 번 정의 됩니다. 컴파일러는 두 번째 매크로 정의 사용 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 명령줄에 포함 된 코드에서는 매크로 정의 `#define` 지시문입니다.

1. 포함 파일에서 가져온 매크로입니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 정의 중 하나를 제거 합니다.

1. 사용 하 여는 [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) 두 번째 정의 하기 전에 지시문입니다.

다음 샘플에서는 C4005 오류가 생성 됩니다.

```
// C4005.cpp
// compile with: /W1 /EHsc
#include <iostream>
using namespace std;

#define TEST "test1"
#define TEST "test2"   // C4005 delete or rename to resolve the warning

int main() {
   cout << TEST << endl;
}
```