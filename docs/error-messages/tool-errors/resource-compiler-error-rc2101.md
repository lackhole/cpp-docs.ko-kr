---
title: 리소스 컴파일러 오류 RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: 595e87b73d79a01993e0e9b3aaa814332b21413f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345281"
---
# <a name="resource-compiler-error-rc2101"></a>리소스 컴파일러 오류 RC2101

전처리 된 RC 파일에 잘못 된 지시문

리소스 컴파일러 파일은 포함 된 **#pragma** 지시문입니다.

사용 된 **#ifndef** 리소스 컴파일러를 정의 하는 include 파일을 처리할 때 RC_INVOKED 상수를 사용 하 여 전처리기 지시문입니다. 위치는 **#pragma** RC_INVOKED 상수 정의 될 때 처리 되지 않은 코드 블록 안에 지시문입니다. 블록의 코드는 C에 의해서만 처리 /C++ 컴파일러 및 리소스 컴파일러에 의해 없습니다. 다음 샘플 코드에는이 기술을 보여 줍니다.

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

합니다 **#pragma** 전처리기 지시문에서 의미가 없는 합니다. RC 파일입니다. 합니다 **#include** 전처리기 지시문에 자주 사용 되는 합니다. RC 파일에서 헤더 파일 (프로젝트 기반 사용자 지정 헤더 파일 또는 해당 제품 중 하나를 사용 하 여 Microsoft에서 제공 하는 표준 헤더 파일). 포함 파일의 이러한 일부 포함 된 **#pragma** 지시문입니다. 헤더 파일로 하나 이상의 다른 헤더 파일에 잘못 된 포함 된 파일을 포함할 수 있으므로 **#pragma** 지시문을 바로 알 수 있습니다.

합니다 **#ifndef** RC_INVOKED 기술 프로젝트 기반 헤더 파일의 헤더 파일 포함 하 여 제어할 수 있습니다.