---
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 86268bd9ac49c8ea27f715404236bcb9291f5d8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339720"
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

모든 응용 프로그램에서 제공한 함수를 호출 **_CLIENT_BLOCK** 힙 (디버그 버전에만 해당)의 형식입니다.

## <a name="syntax"></a>구문

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>매개 변수

*pfn*<br/>
애플리케이션에서 제공하는 함수 콜백 함수에 대한 포인터입니다. 이 함수에 대한 첫 번째 매개 변수는 데이터를 가리킵니다. 두 번째 매개 변수는 호출에 전달 되는 상황에 맞는 포인터 **_CrtDoForAllClientObjects**합니다.

*context*<br/>
애플리케이션에서 제공하는 함수에 전달되는 애플리케이션에서 제공하는 컨텍스트에 대한 포인터입니다.

## <a name="remarks"></a>설명

**_CrtDoForAllClientObjects** 인 메모리 블록을 힙의 연결된 리스트를 검색 하는 함수는 **_CLIENT_BLOCK** 형식 및 호출 하면이 형식의 블록을 응용 프로그램에서 제공한 함수를 찾을 수 있습니다. 찾은 블록과 하며 *상황에 맞는* 매개 변수는 응용 프로그램 제공 함수에 인수로 전달 됩니다. 디버그 하는 동안 응용 프로그램을 추적할 수 있습니다 특정 그룹 할당을 명시적으로 디버그 힙 메모리를 할당 하는 함수를 호출 하 고 블록을 할당할 수 있도록 지정 하 여 합니다 **_CLIENT_BLOCK** 블록 형식입니다. 그런 다음 이러한 블록을 개별적으로 추적하여 누수 검색 및 메모리 상태 보고 시 다르게 보고할 수 있습니다.

경우는 **_CRTDBG_ALLOC_MEM_DF** 비트 필드를 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그가 켜져 있지 **_CrtDoForAllClientObjects** 즉시 반환 합니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 가 정의 되지 않은, 호출 **_CrtDoForAllClientObjects** 전처리 중 제거 됩니다.

에 대 한 자세한 내용은 합니다 **_CLIENT_BLOCK** 형식과 다른 디버그 함수에서 사용할 수 있습니다, 참조 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)합니다. 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

하는 경우 *pfn* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 로 설정 된 **EINVAL** 함수를 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

**라이브러리:** 디버그 버전의 유니버설 C 런타임 라이브러리만 해당 합니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[힙 상태 보고 함수](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
