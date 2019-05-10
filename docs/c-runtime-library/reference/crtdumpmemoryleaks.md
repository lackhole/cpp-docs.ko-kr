---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: baf4f8d8234ba744acda20541d37bbc3ed076678
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339457"
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

메모리 누수가 발생한 경우 디버그 힙의 모든 메모리 블록을 덤프합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>반환 값

**_CrtDumpMemoryLeaks** 메모리 누수가 발견 되는 경우 TRUE를 반환 합니다. 그렇지 않은 경우 이 함수는 FALSE를 반환합니다.

## <a name="remarks"></a>설명

합니다 **_CrtDumpMemoryLeaks** 함수는 프로그램 실행의 시작 이후 메모리 누수가 발생 했는지 여부를 결정 합니다. 누수를 발견하면 힙에 있는 모든 개체에 대한 디버그 헤더 정보를 사용자가 읽을 수 있는 형식으로 덤프합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtDumpMemoryLeaks** 전처리 중 제거 됩니다.

**_CrtDumpMemoryLeaks** 자주 응용 프로그램에 의해 할당 된 모든 메모리 해제 되었는지 확인 하려면 프로그램 실행이 끝날 때 호출 됩니다. 함수 설정 하 여 자동으로 프로그램 종료 시 호출할 수 있습니다는 **_CRTDBG_LEAK_CHECK_DF** 비트 필드를 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 사용 하 여 플래그를 [_CrtSetDbgFlag](crtsetdbgflag.md)함수입니다.

**_CrtDumpMemoryLeaks** 호출 [_CrtMemCheckpoint](crtmemcheckpoint.md) 힙의 현재 상태를 가져오지 후 해제 되지 않은 블록에 대 한 상태를 검색 합니다. 해제 되지 않은 블록이 발견 되 면 **_CrtDumpMemoryLeaks** 호출 [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) 프로그램 실행의 시작부터 힙에 할당 된 모든 개체에 대 한 정보를 덤프 합니다.

기본적으로 내부 C 런타임 블록 (**_CRT_BLOCK**) 메모리 덤프 작업에 포함 되지 않습니다. 합니다 [_CrtSetDbgFlag](crtsetdbgflag.md) 켜려면 함수를 사용할 수 있습니다 합니다 **_CRTDBG_CHECK_CRT_DF** 비트의 **_crtDbgFlag** 누수 검색 프로세스에서 이러한 블록을 포함 하도록 합니다.

힙 상태 함수에 대 한 자세한 내용은 하며 **_CrtMemState** 구조체를 참조 하십시오 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

샘플을 사용 하는 방법에 대 한 **_CrtDumpMemoryLeaks**를 참조 하십시오 [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
