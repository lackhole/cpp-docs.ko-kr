---
title: include_alias
ms.date: 12/16/2018
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
ms.openlocfilehash: 187fa94f7c2a5457df655081b87a7f49d38adfa2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384044"
---
# <a name="includealias"></a>include_alias

되도록 지정 *alias_filename* 에서 발견 되는 `#include` 지시문, 컴파일러 대체 *actual_filename* 그 자리에 합니다.

## <a name="syntax"></a>구문

> #<a name="pragma-includealiasaliasfilename-actualfilename"></a>pragma include_alias("*alias_filename*", "*actual_filename*")
> #<a name="pragma-includealiasaliasfilename-actualfilename"></a>pragma include_alias(\<*alias_filename*>, \<*actual_filename*>)

## <a name="remarks"></a>설명

합니다 **include_alias** pragma 지시문을 사용 하면 다른 이름이 나 원본 파일에 의해 포함 파일 이름에 대 한 경로 파일을 대체할 수 있습니다. 예를 들어, 일부 파일 시스템 8.3 FAT 파일 시스템 제한 보다 더 긴 헤더 파일을 허용합니다. 컴파일러는 두 파일명 중 더 긴 헤더 파일 이름의 처음 8자가 고유하다는 보장이 되지 않기 때문에 더 긴 이름을 8.3으로 자를 수 없습니다. 컴파일러가 합니다 *alias_filename* 대체 문자열 *actual_filename*, 및 헤더 파일을 찾습니다 *actual_filename* 대신 합니다. pragma 선언은 대체하려고 하는 `#include` 지시문 전에 배치되어야 합니다. 다음은 사용 예를 보여줍니다.

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

별칭이 올바르게 검색되어 일치하려면, 철자, 큰따옴표나 꺾쇠 괄호까지 지정된 내용과 정확하게 일치해야 합니다. **include_alias** pragma는 파일 이름에 대하여 간단한 문자열 일치 검사를 수행합니다. 다른 파일 이름의 유효성 검증은 수행되지 않습니다. 다음 예를 살펴보면,

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

헤더 파일 문자열이 정확하게 일치하지 않기 때문에 별칭 대체가 수행되지 않습니다. 또한 `/Yu`나 `/Yc` 컴파일러 옵션 또는 `hdrstop` pragma에 대한 인수로 사용되는 헤더 파일 이름은 대체되지 않습니다. 예를 들어 소스 파일에 다음 지시문이 포함된 경우,

```cpp
#include <AppleSystemHeaderStop.h>
```

해당 컴파일러 옵션이 부여되어야 합니다.

> /YcAppleSystemHeaderStop.h

**include_alias** pragma를 사용하여 헤더 파일 이름을 다른 파일 경로로 매핑할 수 있습니다. 다음은 사용 예를 보여줍니다.

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

큰따옴표로 묶인 파일 이름과 꺾쇠 괄호로 묶인 파일 이름을 섞어 사용하지 마십시오. 예를 들어, `#pragma include_alias` 지시문 두 개가 있다면 컴파일러는 다음 `#include` 지시문에 별칭 파일 이름으로 대체하지 않습니다.

```cpp
#include <api.h>
#include "stdio.h"
```

다음 지시문에서는 오류가 발생합니다.

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

오류 메시지에 나오거나 `__FILE__` 매크로가 확장하는 파일 이름은 별칭으로 대체가 수행된 후의 이름입니다. 예를 들어 다음 지시문 뒤 출력을 참조하세요.

```cpp
#pragma include_alias( "VERYLONGFILENAME.H", "myfile.h" )
#include "VERYLONGFILENAME.H"
```

VERYLONGFILENAME.H에서 다음과 같은 오류가 발생합니다.

```Output
myfile.h(15) : error C2059 : syntax error
```

전이성은 지원되지 않습니다. 다음과 같은 지시문이 주어진 경우

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

컴파일러는 파일 two.h three.h가 아니라 검색합니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
