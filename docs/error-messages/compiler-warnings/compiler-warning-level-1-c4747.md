---
title: 컴파일러 경고(수준 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: ecaabd482049771b1d3915470a2be7a52e36d361
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404028"
---
# <a name="compiler-warning-level-1-c4747"></a>컴파일러 경고(수준 1) C4747

관리 되는 호출 ' 진입점 ': DLL 진입점 및 DLL 진입점에서에 도달 하는 호출을 포함 하 여, 로더 잠금 상태에서 관리 되는 코드를 실행할 수 있습니다.

컴파일러가 (예상) DLL 진입점을 MSIL로 컴파일된를 찾았습니다.  잠재적인 문제가 있어 해당 진입점 MSIL로 컴파일된 DLL을 로드를에서 한 DLL 진입점 함수가 MSIL로 컴파일하는 것이 좋습니다.

자세한 내용은 [혼합 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md) 하 고 [링커 도구 오류 LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md)합니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 사용 하 여 모듈을 컴파일되지 않습니다 **/clr**합니다.

1. 표시 된 진입점 함수 `#pragma unmanaged`합니다.

## <a name="example"></a>예제

다음 샘플 C4747를 생성합니다.

```
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