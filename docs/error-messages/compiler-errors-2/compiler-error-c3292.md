---
title: 컴파일러 오류 C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: a68d3e922532480063fe4c294e40f453885743e8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777005"
---
# <a name="compiler-error-c3292"></a>컴파일러 오류 C3292

cli 네임스페이스를 다시 열 수 없습니다.

cli 네임스페이스를 코드에서 선언할 수 없습니다.  자세한 내용은 [Platform, default 및 cli 네임 스페이스](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3292를 생성합니다.

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```