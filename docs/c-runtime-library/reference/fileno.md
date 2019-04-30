---
title: _fileno
ms.date: 11/04/2016
apiname:
- _fileno
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fileno
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
ms.openlocfilehash: 682ab4b01a663bd9a6314138aa692b1c05b7437a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333770"
---
# <a name="fileno"></a>_fileno

스트림에 연결된 파일 설명자를 가져옵니다.

## <a name="syntax"></a>구문

```C
int _fileno(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**_fileno** 파일 설명자를 반환 합니다. 반환되는 오류가 없습니다. 경우에 결과가 정의 되지 않습니다 *스트림을* 열려 있는 파일을 지정 하지 않습니다. 스트림이 **NULL**하십시오 **_fileno** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행이 함수는-1 반환 하 고 집합을 계속 하도록 허용 된 경우 **errno** 하 **EINVAL**합니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

> [!NOTE]
> 하는 경우 **stdout** 하거나 **stderr** 연결 되어 있지 않습니다 (예를 들어 콘솔 창이 없는 Windows 응용 프로그램)에 출력 스트림을 사용 하 여 반환 된 파일 설명자는-2입니다. 이전 버전에서 반환된 파일 설명자는 -1이었습니다. 이렇게 변경되어 애플리케이션이 이 조건을 오류와 구분할 수 있습니다.

## <a name="remarks"></a>설명

합니다 **_fileno** 현재 연결 된 파일 설명자를 반환 하는 루틴 *스트림*합니다. 이 루틴은 함수 및 매크로로 구현됩니다. 구현 선택에 대한 자세한 내용은 [함수와 매크로 중 선택](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_fileno**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fileno.c
// This program uses _fileno to obtain
// the file descriptor for some standard C streams.
//

#include <stdio.h>

int main( void )
{
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );
}
```

```Output
The file descriptor for stdin is 0
The file descriptor for stdout is 1
The file descriptor for stderr is 2
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_filelength, _filelengthi64](filelength-filelengthi64.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
