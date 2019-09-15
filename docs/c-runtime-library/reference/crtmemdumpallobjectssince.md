---
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
api_name:
- _CrtMemDumpAllObjectsSince
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: 9e3793e9b88c593968b108e2801e24476417603c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942380"
---
# <a name="_crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

프로그램 실행의 시작부터 또는 지정된 힙 상태에서 힙에 있는 개체에 대한 정보를 덤프합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>매개 변수

*state*<br/>
덤프를 시작할 힙 상태 또는 **NULL**에 대한 포인터입니다.

## <a name="remarks"></a>설명

**_CrtMemDumpAllObjectsSince** 함수는 힙에 할당 된 개체의 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프 합니다. 덤프 정보는 애플리케이션에서 할당을 추적하고 메모리 문제를 검색하는 데 사용할 수 있습니다. [_Debug](../../c-runtime-library/debug.md) 가 정의 되지 않은 경우 전처리 중에 **_CrtMemDumpAllObjectsSince** 에 대 한 호출이 제거 됩니다.

**_CrtMemDumpAllObjectsSince** 는 *state* 매개 변수 값을 사용 하 여 덤프 작업을 시작할 위치를 결정 합니다. 지정 된 힙 상태에서 덤프를 시작 하려면 *상태* 매개 변수가 **_CrtMemDumpAllObjectsSince** 를 호출 하기 전에 [_CrtMemCheckpoint](crtmemcheckpoint.md) 에 의해 채워진 **_CrtMemState** 구조체에 대 한 포인터 여야 합니다. *State* 가 **NULL**인 경우 함수는 프로그램 실행 시작부터 덤프를 시작 합니다.

응용 프로그램에서 [_CrtSetDumpClient](crtsetdumpclient.md)를 호출 하 여 덤프 후크 함수를 설치한 경우 **_CrtMemDumpAllObjectsSince** 는 **_CLIENT_BLOCK** 블록 형식에 대 한 정보를 덤프할 때마다 응용 프로그램에서 제공 하는 덤프를 호출 합니다. 함수도 있습니다. 기본적으로 내부 C **_crt_block**(런타임 블록)는 메모리 덤프 작업에 포함 되지 않습니다. [_CrtSetDbgFlag](crtsetdbgflag.md) 함수를 사용 하 여 **_crtDbgFlag** 의 **_CRTDBG_CHECK_CRT_DF** 비트를 설정 하 여 이러한 블록을 포함할 수 있습니다. 또한 해제되거나 무시된 것으로 표시된 블록( **_FREE_BLOCK**, **_IGNORE_BLOCK**)은 메모리 덤프에 포함되지 않습니다.

힙 상태 함수 및 **_CrtMemState** 구조에 대 한 자세한 내용은 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)를 참조 하세요. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

**_CrtMemDumpAllObjectsSince**를 사용 하는 방법에 대 한 샘플은 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)를 참조 하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
