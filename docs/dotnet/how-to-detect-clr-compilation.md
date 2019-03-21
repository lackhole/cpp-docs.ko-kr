---
title: '방법: -Clr 컴파일 감지'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 0b02be1bcd0afc9fd857e689ceafdcab5eaf05d1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746515"
---
# <a name="how-to-detect-clr-compilation"></a>방법: /Clr 컴파일 감지

사용 된 `_MANAGED` 또는 `_M_CEE` 모듈을 사용 하 여 컴파일된 경우 참조 하는 매크로 **/clr**. 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

매크로 대 한 자세한 내용은 참조 하세요. [미리 정의 된 매크로](../preprocessor/predefined-macros.md)합니다.

## <a name="example"></a>예제

```
// detect_CLR_compilation.cpp
// compile with: /clr
#include <stdio.h>

int main() {
   #if (_MANAGED == 1) || (_M_CEE == 1)
      printf_s("compiling with /clr\n");
   #else
      printf_s("compiling without /clr\n");
   #endif
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
