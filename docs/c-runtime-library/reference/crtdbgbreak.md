---
title: _CrtDbgBreak
ms.date: 11/04/2016
apiname:
- _CrtDbgBreak
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _CrtDbgBreak
- CrtDbgBreak
helpviewer_keywords:
- CrtDbgBreak function
- _CrtDbgBreak function
ms.assetid: 01f8b4a2-a2c7-4e1f-9f39-e573b4a7871f
ms.openlocfilehash: 4cf64daaea3193f7cf6b3aaa0b1aab031f104704
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340172"
---
# <a name="crtdbgbreak"></a>_CrtDbgBreak

특정 코드 줄에 중단점을 설정합니다. 디버그 모드에서만 사용됩니다.

## <a name="syntax"></a>구문

```C
void _CrtDbgBreak( void );
```

## <a name="return-value"></a>반환 값

반환 값이 없습니다.

## <a name="remarks"></a>설명

합니다 **_CrtDbgBreak** 함수 디버그 중단점을 설정 코드의 특정 줄에 함수가 상주 합니다. 이 함수는 디버그 모드 에서만 사용 되며 종속 **_DEBUG** 이전에 정의 되 고 있습니다.

다른 후크 가능 런타임 함수를 사용하고 고유한 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은 [고유한 디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtDbgBreak**|\<CRTDBG.h>|

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참조

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[__debugbreak](../../intrinsics/debugbreak.md)<br/>
