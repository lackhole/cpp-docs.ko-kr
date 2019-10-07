---
title: /Zc:inline(참조되지 않은 COMDAT 제거)
ms.date: 09/05/2019
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: f0c0d9a4e5e5f52d239f1a8591006b3d9e369778
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740109"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline(참조되지 않은 COMDAT 제거)

COMDAT이거나 내부 링크만 있는 참조되지 않은 함수 또는 데이터를 제거합니다. **/Zc: inline** 을 지정 하면 컴파일러가 인라인 데이터 또는 인라인 함수를 사용 하는 변환 단위에도 데이터 또는 함수에 대 한 정의를 포함 해야 합니다.

## <a name="syntax"></a>구문

> **/Zc:inline**[ **-** ]

## <a name="remarks"></a>설명

**/Zc: inline** 이 지정 된 경우 컴파일러는 참조 되지 않은 COMDAT 함수 또는 데이터에 대 한 기호 정보나 내부 링크만 있는 함수 또는 데이터에 대 한 기호 정보를 내보내지 않습니다. 이러한 최적화는 링커 옵션 [/opt: REF](opt-optimizations.md) 가 지정 된 경우 또는 릴리스 빌드에서 링커가 수행 하는 작업의 일부를 간소화 합니다. 컴파일러가 이러한 최적화를 수행하면 .obj f파일의 크기를 크게 줄이고 링커 속도를 상당히 높일 수 있습니다. 최적화를 사용 하지 않도록 설정 ([/od](od-disable-debug.md)) 하거나 [/Gl (전체 프로그램 최적화)](gl-whole-program-optimization.md) 을 지정한 경우에는이 컴파일러 옵션을 사용할 수 없습니다.

기본적으로이 옵션은 명령줄 빌드에서 off ( **/zc: inline**)입니다. [/Permissive-](permissive-standards-conformance.md) 옵션은 **/zc: inline**을 사용 하도록 설정 하지 않습니다. MSBuild 프로젝트에서 옵션은 **구성 속성** >  > **C/C++** **언어** > **제거 참조 되지 않은 코드 및 데이터** 속성으로 설정 됩니다 .이 속성은 **예** 로 설정 됩니다. 기본.

**/Zc: inline** 이 지정 된 경우 컴파일러는 선언 `inline` 된 모든 함수가 사용 되는 경우 동일한 변환 단위에서 사용할 수 있는 정의를 포함 하도록 c + + 11 요구 사항을 적용 합니다. 이 옵션을 지정 하지 않으면 정의가 표시 되지 않는 경우에도 선언 `inline` 된 함수를 호출 하는 호환 되지 않는 코드가 Microsoft 컴파일러에서 허용 됩니다. 자세한 내용은 섹션 3.2 및 7.1.2에서 C++11 표준을 참조하세요. 이 컴파일러 옵션은 Visual Studio 2013 업데이트 2에서 정의되었습니다.

**/Zc: inline** 옵션을 사용 하려면 비호환 코드를 업데이트 합니다.

이 예제에서는 기본 **/zc: inline-** 옵션이 사용 될 때 정의가 없는 인라인 함수 선언에 대 한 비규격 사용을 컴파일하고 연결 하는 방법을 보여 줍니다.

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

**/Zc: inline**을 사용하는 경우 컴파일러는 예: `Example::inline_call`의에 대해 인라인 되지않은 코드 본문을 내보내지 않으므로 [LNK2019 오류](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)가 발생 합니다. 따라서 `main`에서 인라인되지 않은 호출이 발생해 정의되지 않은 외부 기호를 참조하게 됩니다.

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

1. **구성 속성** > **C/C++** 언어 > 속성 페이지를 선택 합니다.

1. 참조 되지 않은 **코드 및 데이터 제거** 속성을 수정한 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
