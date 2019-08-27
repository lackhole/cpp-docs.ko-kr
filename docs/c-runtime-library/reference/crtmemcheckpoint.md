---
title: _CrtMemCheckpoint
ms.date: 11/04/2016
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: ee435ba3e9e40795280dee0f97feaad32c8b0fc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339873"
---
# <a name="_crtmemcheckpoint"></a>_CrtMemCheckpoint

응용 프로그램에서 제공한에서 가져와 디버그 힙의 현재 상태를 가져옵니다 **_CrtMemState** 구조 (디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>매개 변수

*state*<br/>
에 대 한 포인터 **_CrtMemState** 메모리 검사점으로 채울 구조입니다.

## <a name="remarks"></a>설명

합니다 **_CrtMemCheckpoint** 함수 언제 든 디버그 힙의 현재 상태의 스냅숏을 만듭니다. 이 스냅샷은 메모리 누수를 비롯한 여러 문제를 손쉽게 감지하도록 [_CrtMemDifference](crtmemdifference.md) 같은 기타 힙 상태 함수에 사용할 수 있습니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtMemState** 전처리 중 제거 됩니다.

응용 프로그램의 이전에 할당 된 인스턴스에 대 한 포인터를 전달 해야 합니다 **_CrtMemState** 에 Crtdbg.h에 정의 된 합니다 *상태* 매개 변수. 하는 경우 **_CrtMemCheckpoint** 에서 검사점을 만드는 동안 오류가 발생 하는 함수 생성을 **_CRT_WARN** 문제를 설명 하는 보고서를 디버그 합니다.

힙 상태 함수에 대 한 자세한 내용은 하며 **_CrtMemState** 구조체를 참조 하십시오 [힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

하는 경우 *상태* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 로 설정 된 **EINVAL** 함수를 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 UCRT만 해당 합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
