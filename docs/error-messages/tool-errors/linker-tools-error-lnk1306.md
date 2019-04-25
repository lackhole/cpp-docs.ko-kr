---
title: 링커 도구 오류 LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: ddaa8797e0cf8ff617408aedc770b21cc656cec4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160460"
---
# <a name="linker-tools-error-lnk1306"></a>링커 도구 오류 LNK1306

> DLL 진입점 함수를 관리할 수 없습니다. 네이티브 컴파일

`DllMain` MSIL로 컴파일할 수 없습니다 네이티브로 컴파일해야 합니다.

이 문제를 해결 하려면

- 없이 진입점이 포함 된 파일을 컴파일하지 **/clr**합니다.

- 진입점 배치를 `#pragma unmanaged` 섹션입니다.

자세한 내용은 다음을 참조하세요.

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed, unmanaged](../../preprocessor/managed-unmanaged.md)

- [혼합형 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)

- [DLL 및 Visual C++ 런타임 라이브러리 동작](../../build/run-time-library-behavior.md)

## <a name="example"></a>예제

다음 샘플 LNK1306를 생성합니다.

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

이 문제를 해결 하려면 넣지 마십시오 하면 /clr 옵션과이 파일을 컴파일하거나 사용 하는 `#pragma` 지시문이 예와에서 같이 관리 되지 않는 섹션에 항목 지점 정의 내릴 수:

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```
