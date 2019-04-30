---
title: /Zc:inline(참조되지 않은 COMDAT 제거)
ms.date: 03/01/2018
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: 06bdb3300aae88c6c4c8f7e66af658f47548ac5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316056"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline(참조되지 않은 COMDAT 제거)

COMDAT이거나 내부 링크만 있는 참조되지 않은 함수 또는 데이터를 제거합니다. 때 **/zc: inline** 를 지정 하면 컴파일러가 필요 인라인 데이터 또는 인라인 함수를 사용 하는 변환 단위 데이터 또는 함수에 대 한 정의 포함 해야 합니다.

## <a name="syntax"></a>구문

> **/Zc:inline**[**-**]

## <a name="remarks"></a>설명

때 **/zc: inline** 를 지정 하면 컴파일러는 참조 되지 않은 COMDAT 함수 또는 데이터 나 내부 링크만 있는 데이터 또는 함수에 대 한 기호 정보를 내보내지 않습니다. 이 최적화를 간소화 하 릴리스 빌드에서 링커에 의해 수행 된 작업의 일부 때나 링커 옵션 [/opt: ref](opt-optimizations.md) 지정 됩니다. 컴파일러가 이러한 최적화를 수행하면 .obj f파일의 크기를 크게 줄이고 링커 속도를 상당히 높일 수 있습니다. 최적화는 사용 하지 않도록 설정 하는 경우에이 컴파일러 옵션 사용 되지 않습니다 ([/Od](od-disable-debug.md)) 때나 [/GL (전체 프로그램 최적화)](gl-whole-program-optimization.md) 지정 됩니다.

기본적으로이 옵션은 해제 되어 (**/Zc:inline-**). [/ permissive-](permissive-standards-conformance.md) 옵션이 사용 되지 않습니다 **/zc: inline**합니다.

하는 경우 **/zc: inline** 컴파일러가 C + + 11 요구 사항을 적용 선언한 모든 함수는 지정 된 `inline` 사용 하는 경우 동일한 변환 단위에서 사용할 수 있는 정의가 있어야 합니다. Microsoft 컴파일러는 선언 된 함수를 호출 하는 비호환 코드 허용 옵션을 지정 하지 않으면 경우 `inline` 없습니다 정의가 표시 되는 경우에 합니다. 자세한 내용은 섹션 3.2 및 7.1.2에서 C++11 표준을 참조하세요. 이 컴파일러 옵션은 Visual Studio 2013 업데이트 2에서 정의되었습니다.

사용 하는 **/zc: inline** 옵션을 호환 되지 않는 코드를 업데이트 합니다.

어떻게 정의 없이 인라인 함수 선언의 호환 되지 않는 사용 계속 컴파일하고 연결 하는 경우를 보여 주는이 예제는 기본 **/Zc:inline-** 옵션을 사용 합니다.

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n");
}

void Example::normal_call() {
   printf("normal_call was called.\n");
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

때 **/zc: inline** 을 사용 하는 동일한 코드가 [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) 오류를 컴파일러에 대 한 인라인되지 않은 코드 본문을 내보내지 않습니다 있으므로 `Example::inline_call` example.obj의 합니다. 따라서 `main`에서 인라인되지 않은 호출이 발생해 정의되지 않은 외부 기호를 참조하게 됩니다.

이러한 오류를 해결하기 위해 `inline` 선언에서 `Example::inline_call` 키워드를 제거하거나 `Example::inline_call`의 정의를 헤더 파일로 이동하거나 `Example`의 구현을 main.cpp로 이동할 수 있습니다. 다음 예제에서는 헤더를 포함한 모든 호출자에게 정의가 표시되는 헤더 파일로 정의를 이동합니다.

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n");
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n");
   inline_call();
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **C /C++** > **언어** 속성 페이지.

1. 수정 합니다 **참조 되지 않은 코드 및 데이터 제거** 속성을 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
