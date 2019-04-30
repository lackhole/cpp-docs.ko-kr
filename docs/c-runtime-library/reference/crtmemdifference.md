---
title: _CrtMemDifference
ms.date: 11/04/2016
apiname:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: f2c6306bf604737d0ace142674b21845a08e2dee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339470"
---
# <a name="crtmemdifference"></a>_CrtMemDifference

두 메모리 상태를 비교하고 해당 차이점을 반환합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>매개 변수

*stateDiff*<br/>
에 대 한 포인터를 **_CrtMemState** (반환) 하는 두 메모리 상태 차이점을 저장 하는 데 사용 되는 구조입니다.

*oldState*<br/>
이전 메모리 상태에 대 한 포인터 (**_CrtMemState** 구조).

*newState*<br/>
이후 메모리 상태에 대 한 포인터 (**_CrtMemState** 구조).

## <a name="return-value"></a>반환 값

메모리 상태가 현저 하 게 서로 **_CrtMemDifference** TRUE를 반환 합니다. 그렇지 않은 경우 이 함수는 FALSE를 반환합니다.

## <a name="remarks"></a>설명

합니다 **_CrtMemDifference** 비교 함수 *oldState* 및 *newState* 의 차이점을 가져와 *stateDiff*를 수 있습니다는 사용할 응용 프로그램에서 메모리 누수 및 기타 메모리 문제를 감지할 수 있습니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtMemDifference** 전처리 중 제거 됩니다.

*newState* 하 고 *oldState* 에 대 한 유효한 포인터 여야를 **_CrtMemState** 에 의해 채워진, Crtdbg.h에 정의 된 [_CrtMemCheckpoint](crtmemcheckpoint.md)호출 하기 전에 **_CrtMemDifference**합니다. *stateDiff* 이전에 할당 된 인스턴스에 대 한 포인터 여야 합니다 합니다 **_CrtMemState** 구조입니다. 하는 경우 *stateDiff*를 *newState*, 또는 *oldState* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 로 설정 된 **EINVAL** 고 함수가 FALSE를 반환 합니다.

**_CrtMemDifference** 비교 합니다 **_CrtMemState** 블록의 값 필드 *oldState* 의 *newState* 의결과가져와*stateDiff*합니다. 할당된 블록 형식의 수 또는 각 형식에 대해 할당된 총 블록 수가 두 메모리 상태 간에 다를 경우 상태가 현저하게 다르다고 합니다. 할당 된 한 번에 두 개의 상태 및 총 할당 수 간의 차이 대 한 두 가지 상태에도 저장 됩니다에 대 한 최대 크기의 차이 *stateDiff*합니다.

기본적으로 내부 C 런타임 블록 (**_CRT_BLOCK**) 메모리 상태 작업에 포함 되지 않습니다. [_CrtSetDbgFlag](crtsetdbgflag.md) 켜려면 함수를 사용할 수 있습니다 합니다 **_CRTDBG_CHECK_CRT_DF** 비트의 **_crtDbgFlag** 이러한 블록을 누수 검색 및 기타 메모리 상태 포함 작업입니다. 해제 된 메모리 블록 (**_FREE_BLOCK**)를 일으키지 **_CrtMemDifference** 에서 TRUE를 반환 합니다.

힙 상태 함수에 대 한 자세한 내용은 하며 **_CrtMemState** 구조체를 참조 하십시오 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md) 만 합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
