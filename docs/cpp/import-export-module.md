---
title: 모듈, 가져오기, 내보내기
ms.date: 07/15/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Import 문을 사용 하 여 지정 된 모듈에 정의 된 형식 및 함수에 액세스할 수 있습니다.
ms.openlocfilehash: fbb9c45ec816c859edb4df38ad67dc7778247e87
ms.sourcegitcommit: 7b039b5f32f6c59be6c6bb1cffafd69c3bfadd35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68537789"
---
# <a name="module-import-export"></a>모듈, 가져오기, 내보내기

**모듈**, **가져오기**및 **내보내기** 키워드는 `/experimental:modules` c + + 20에서 사용할 수 있으며와 `/std:c++latest`함께 컴파일러 스위치가 필요 합니다. 자세한 내용은 [ C++의 모듈 개요 ](modules-cpp.md)를 참조 하세요.

## <a name="module"></a>모듈(module)

모듈 구현 파일의 시작 부분에 있는 **module** 문을 사용 하 여 파일 내용이 명명 된 모듈에 속하도록 지정 합니다. 

```cpp
module ModuleA;
```

## <a name="export"></a>내보내기

모듈이 다음과 같은 기본 인터페이스 파일에 대해 **export module** 문을 사용 합니다 **.**

```cpp
export module ModuleA;
```

인터페이스 파일에서 공용 인터페이스의 일부인 이름에 대해 **내보내기** 한정자를 사용 합니다.

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

내보내지 않는 이름은 모듈을 가져오는 코드에 표시 되지 않습니다.

```cpp
//MyProgram.cpp

import module ModuleA;

void main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**Export** 키워드는 모듈 구현 파일에 표시 되지 않을 수 있습니다. **내보내기** 한정자가 네임 스페이스 이름에 적용 되 면 네임 스페이스의 모든 이름을 내보냅니다.

## <a name="import"></a>import

모듈의 이름을 프로그램에 표시 하려면 **import** 문을 사용 합니다. Import 문은 module 문 뒤, #include 지시문 뒤, 파일의 모든 선언 앞에 나타나야 합니다.

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="see-also"></a>참고 항목
[모듈 개요C++](modules-cpp.md)
