---
title: 컴파일러 경고(수준 1 및 수준 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 8050edbd7a653776d046bc7b4155fd43094d9a5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187524"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>컴파일러 경고(수준 1 및 수준 4) C4949

pragma 'managed' 및 '는 사용 하 여 컴파일된 경우에 의미가 ' / clr [: 옵션]'

컴파일러는 무시 합니다 [managed](../../preprocessor/managed-unmanaged.md) 및 소스 코드를 사용 하 여 컴파일되지 않은 경우에 pragma를 관리 되지 않는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md). 이 경고는 정보 제공용입니다.

다음 샘플에서는 C4949 오류가 생성 됩니다.

```
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

때 **관리 되지 않는 #pragma** 없이 사용 되 면 **/clr**, C4949 수준 4 경고입니다.

다음 샘플에서는 C4949 오류가 생성 됩니다.

```
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```