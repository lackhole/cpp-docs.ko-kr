---
title: 컴파일러 오류 C2857
ms.date: 09/13/2018
f1_keywords:
- C2857
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
ms.openlocfilehash: 10c0ea3b54ded29bf80f83713cea33428dca6ca0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350441"
---
# <a name="compiler-error-c2857"></a>컴파일러 오류 C2857

> ' #include ' /Yc를 사용 하 여 지정 된 문에*filename* 소스 파일에서 명령줄 옵션을 찾을 수 없습니다

합니다 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션 컴파일할 소스 파일에 포함 되지 않은 include 파일의 이름을 지정 합니다.

## <a name="remarks"></a>설명

사용 하는 경우는 **/Yc**<em>filename</em> 소스 파일에서 파일의 소스가 되는 미리 컴파일된 헤더 (PCH) 파일을 만드는 옵션을 포함 해야 합니다는 *filename* 헤더 파일입니다. 소스 파일에 지정 된 포함 하 여 포함 된 모든 파일 *filename*, PCH 파일에 포함 됩니다. 사용 하 여 컴파일된 다른 소스 파일에는 **/Yu**<em>filename</em> 했습니다. PCH를 사용 하는 옵션 파일의 포함 *filename* 파일의 첫 번째 비 주석 줄을 이어야 합니다. 컴파일러가이 포함 하기 전에 소스 파일에 있는 모든 내용을 무시 합니다.

이 오류를 때문일 수 있습니다는 `#include "filename"` PCH 소스 파일에 컴파일되지 않은 조건부 컴파일 블록의 문이 있습니다.

## <a name="example"></a>예제

일반적인 사용법에서 PCH 소스 파일로 프로젝트에 하나의 원본 파일 지정 하 고 PCH 헤더 파일과 헤더 파일 사용 됩니다. 일반적인 PCH 헤더 파일에는 모든 프로젝트에서 사용 되는 라이브러리 헤더 되지만 아직 개발 중인 로컬 헤더 이 샘플에서는 PCH 헤더 파일의 이름은 *my_pch.h*합니다.

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

PCH 원본 파일을 사용 하 여 컴파일하는 **/Yc**<em>my_pch.h</em> 옵션입니다. 컴파일러에서이 PCH 헤더 파일의 include를 찾지 못하면 C2857 발생 합니다.

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

이 PCH 파일을 사용 하려면 소스 파일 사용 하 여 컴파일된 해야 합니다 **/Yu**<em>my_pch.h</em> 옵션입니다. PCH 헤더 파일을 했습니다. PCH를 사용 하는 소스 파일에 먼저 포함 되어야 합니다.

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```