---
title: 컴파일러 경고 C4984
ms.date: 08/19/2019
f1_keywords:
- C4984
helpviewer_keywords:
- C4984
ms.openlocfilehash: 91ae30018c7de633d8ba23d538b301ad4bbac984
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69632907"
---
# <a name="compiler-warning-c4984"></a>컴파일러 경고 C4984

> ' i n t e r '는 c + + 17 언어 확장입니다.

## <a name="remarks"></a>설명

컴파일러가 기본 c + `if constexpr` + 14 표준을 사용 하 여 컴파일된 코드에서 식을 찾았습니다. 이 식은 c + + 17 표준에서 시작 하 여 지정 됩니다. C + + 11 또는 c + + 14 호환성이 필요한 경우에는이 식이 이식 가능 하지 않습니다.

C4984은 기본적으로 오류로 실행 되지만 suppressible입니다. 코드를 c + + 17로 컴파일하여이 식을 활성화 하려면 [/sd: c + + 17 또는/std: c + + 최신](../../build/reference/std-specify-language-standard-version.md)을 사용 합니다. C + + `if constexpr` 14 용으로 컴파일된 코드에서 식을 Microsoft 확장으로 사용 하려면 오류 메시지의 경고 수준을 표시 하거나 사용 하지 않도록 설정 하거나 변경할 수 있습니다. [/Wd4984](../../build/reference/compiler-option-warning-level.md) 를 사용 하 여 C4984를 사용 하지 않도록 설정 하거나 __/w__*n*__4984__ 을 사용 하 여 오류 대신 수준 *N* 경고로 사용할 수 있습니다. 또는 소스 파일에서 경고를 발생 시키는 줄 앞에 [#pragma 경고 (표시 안 함: 4984)](../../preprocessor/warning.md) 를 사용 합니다.

이 경고는 Visual Studio 2017 버전 15.3부터 사용할 수 있습니다. 특정 컴파일러 버전 이상에서 도입 된 경고를 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 컴파일러 [버전 별 컴파일러 경고](compiler-warnings-by-compiler-version.md)를 참조 하세요.

## <a name="example"></a>예제

이 샘플에서는 C4984를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C4984.cpp
// compile with: cl /EHsc C4984.cpp
#include <iostream>

int main()
{
    constexpr bool compile_time = true;
    // Uncomment the following line or use /std:c++17 to fix
    // #pragma warning(suppress:4984)
    if constexpr (compile_time)
    {
        std::cout << "compile_time is true";
    }
    else
    {
        std::cout << "compile_time is false";
    }
}
```
