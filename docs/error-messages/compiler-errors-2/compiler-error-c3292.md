---
title: 컴파일러 오류 C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 566c92a5dc24c28b334653c6b5507b0bd9330992
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760129"
---
# <a name="compiler-error-c3292"></a>컴파일러 오류 C3292

cli 네임스페이스를 다시 열 수 없습니다.

cli 네임스페이스를 코드에서 선언할 수 없습니다.  자세한 내용은 [Platform, default 및 cli 네임스페이스](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md)를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3292를 생성합니다.

```cpp
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```
