---
title: 함수 인라이닝 문제
ms.date: 11/04/2016
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
ms.openlocfilehash: fec3884dff0dda7140f18fa53e493c12996edcf0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031526"
---
# <a name="function-inlining-problems"></a>함수 인라이닝 문제

인라인 함수를 사용 하는 경우 다음을 수행 해야 합니다.

- 인라인 함수를 포함 하는 헤더 파일에서 구현 된 경우

- 가 인라인 헤더 파일에서 ON으로 설정 합니다.

```
// LNK2019_function_inline.cpp
// compile with: /c
// post-build command: lib LNK2019_function_inline.obj
#include <stdio.h>
struct _load_config_used {
   void Test();
   void Test2() { printf("in Test2\n"); }
};

void _load_config_used::Test() { printf("in Test\n"); }
```

그리고

```
// LNK2019_function_inline_2.cpp
// compile with: LNK2019_function_inline.lib
struct _load_config_used {
   void Test();
   void Test2();
};

int main() {
   _load_config_used x;
   x.Test();
   x.Test2();   // LNK2019
}
```

사용 중인 경우는 `#pragma inline_depth` 컴파일러 지시문에 있어야 2의 큰 값을 설정 합니다. 값 0은 해제 인라인 처리 합니다. 또한 사용 하 고 있는지를 확인 합니다 **/Ob1** 하거나 **/ob2** 컴파일러 옵션입니다.

서로 다른 모듈에서 인라인 및 인라인이 아닌 컴파일 옵션을 혼합 하면 문제가 발생할 수 있습니다. 경우는 C++ 함수 인라이닝 켜져 라이브러리를 만들면 ([/Ob1](../../build/reference/ob-inline-function-expansion.md) 하거나 [/ob2](../../build/reference/ob-inline-function-expansion.md)) 함수를 설명 하는 해당 헤더 파일은 인라인 (옵션 제외)를 해제 하지만 오류가 표시 됩니다 LNK2001 합니다. 함수를 얻지 인라인 코드를 헤더 파일에서 있지만 없기 때문에 라이브러리 파일에 대 한 참조를 해결 하려면 주소가 없습니다.

마찬가지로, 인라인 함수를 사용 하는 프로젝트 함수를 정의.cpp 파일에 파일 헤더에 LNK2019를 가져올 수도 대신 합니다. 헤더 파일은 어디에서 나 적절 한 것으로 간주 포함 되지만 함수만 인라인 컴파일러를 통해.cpp 파일을 전달 하는 경우 따라서 링커는 다른 모듈에 사용 되는 경우 외부 참조로 함수를 볼 수 있습니다.

```
// LNK2019_FIP.h
struct testclass {
   void PublicStatMemFunc1(void);
};
```

그런 다음

```
// LNK2019_FIP.cpp
// compile with: /c
#include "LNK2019_FIP.h"
inline void testclass::PublicStatMemFunc1(void) {}
```

그런 다음

```
// LNK2019_FIP_2.cpp
// compile with: LNK2019_FIP.cpp
// LNK2019 expected
#include "LNK2019_FIP.h"
int main() {
   testclass testclsObject;

   // module cannot see the implementation of PublicStatMemFunc1
   testclsObject.PublicStatMemFunc1();
}
```

## <a name="see-also"></a>참고자료

[링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)