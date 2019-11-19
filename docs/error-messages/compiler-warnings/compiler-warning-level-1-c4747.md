---
title: 컴파일러 경고 (수준 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: 623b29d345a850cc312f23e4c521aa0be5b47242
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052438"
---
# <a name="compiler-warning-level-1-c4747"></a>컴파일러 경고 (수준 1) C4747

관리 되는 ' entrypoint ' 호출: dll 진입점 및 DLL 진입점에서 호출 된 호출을 포함 하 여 관리 코드를 로더 잠금 상태에서 실행할 수 없습니다.

컴파일러가 MSIL로 컴파일된 (예상) DLL 진입점을 찾았습니다.  진입점이 MSIL로 컴파일된 DLL을 로드 하는 데 문제가 있을 수 있으므로 DLL 진입점 함수를 MSIL로 컴파일하지 않는 것이 좋습니다.

자세한 내용은 [혼합 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md) 및 [링커 도구 오류 LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md)를 참조 하세요.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. **/Clr**을 사용 하 여 모듈을 컴파일하지 마세요.

1. 진입점 함수를 `#pragma unmanaged`표시 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4747를 생성 합니다.

```cpp
// C4747.cpp
// compile with: /clr /c /W1
// C4747 expected
#include <windows.h>

// Uncomment the following line to resolve.
// #pragma unmanaged

BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {
   return TRUE;
};
```