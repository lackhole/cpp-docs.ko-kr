---
title: 링커 도구 경고 LNK4221
ms.date: 11/04/2016
f1_keywords:
- LNK4221
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
ms.openlocfilehash: baea8643001c550aeb3cb35dc6fe414e4330c0c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160382"
---
# <a name="linker-tools-warning-lnk4221"></a>링커 도구 경고 LNK4221

이 개체 파일 않으므로이 라이브러리를 사용 하는 링크 작업에 사용 됩니다. 모든 이전에 정의 되지 않은 공용 기호를 정의 하지 않습니다.

다음 두 가지 코드 조각을 고려해 야 합니다.

```
// a.cpp
#include <atlbase.h>
```

```
// b.cpp
#include <atlbase.h>
int function()
{
   return 0;
}
```

실행을 파일을 컴파일 및 두 개의 개체 파일을 만듭니다 **cl /c a.cpp b.cpp** 명령 프롬프트에서. 개체 파일을 실행 하 여 연결 하면 **연결/lib /out:test.lib a.obj b.obj**, LNK4221 경고를 받게 됩니다. 실행 하 여 개체를 링크 하는 경우 **연결/lib /out:test.lib b.obj a.obj**, 경고가 표시 되지 것입니다.

경고가 발생 하지 않습니다는 두 번째 시나리오에서 링커-lifo (후입선출) 방식으로 작동 하기 때문에 합니다. 첫 번째 시나리오에서는 b.obj a.obj, 보다 먼저 처리 됩니다 하 고 a.obj 기호가 없는 새 추가 합니다. A.obj를 먼저 처리 하도록 링커에 지시 합니다 하 여 경고를 방지할 수 있습니다.

두 개의 소스 파일 옵션을 지정할 때이 오류의 일반적인 원인은 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 동일한 이름의 헤더 파일에 지정 된 된 **미리 컴파일된 헤더** 필드. 이 문제의 일반적인 원인은 다룹니다 stdafx.h 되므로 기본적으로 stdafx.cpp stdafx.h를 포함 하 고 새 기호를 추가 하지 않습니다. 다른 소스 파일에 사용 하 여 stdafx.h에 포함 된 경우 **/Yc** 및 연결 된.obj 파일 stdafx.obj 보다 먼저 처리 됩니다, 링커 LNK4221을 throw 합니다.

첫 번째 되도록 하는 각 미리 컴파일된 헤더에 대 한이 문제를 해결할 수, 있습니다 방법은 사용 하 여 포함 하는 원본 파일 하나만 **/Yc**합니다. 다른 모든 소스 파일에는 미리 컴파일된 헤더 사용 해야 합니다. 이 설정을 변경 하는 방법에 대 한 자세한 내용은 참조 하세요. [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)합니다.