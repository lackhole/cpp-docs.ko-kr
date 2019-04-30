---
title: feof
ms.date: 11/04/2016
apiname:
- feof
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
- feof
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
ms.openlocfilehash: 9c023290df601bfc48f9708af86d32d91cd52dc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334400"
---
# <a name="feof"></a>feof

스트림의 파일 끝을 테스트합니다.

## <a name="syntax"></a>구문

```C
int feof(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

합니다 **feof** 읽기 작업이 파일 끝을 넘어 읽으려고 시도한 경우 함수는 0이 아닌 값을 반환, 그렇지 않으면 0을 반환 합니다. 스트림 포인터가 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 하며 **feof** 0을 반환 합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**feof** 루틴 (함수 및 매크로로 구현 됨) 확인 여부를 끝 *스트림* 전달 되었습니다. 파일의 끝이 전달 되 면 읽기 스트림이 닫힐 때까지 또는 될 때까지 작업이 파일 끝 표시기를 반환 [rewind](rewind.md)를 **fsetpos**하십시오 [fseek](fseek-fseeki64.md), 또는  **clearerr** 에 대해 호출 됩니다.

예를 들어 10 바이트를 포함 하는 파일 및 파일에서 10 바이트를 읽는 **feof** 있습니다 끝을 넘어 읽으려고 시도 하지 파일 포인터가 파일 끝도 이므로 0을 반환 합니다. 11 번째 바이트를 읽으려고 시도한 후에 **feof** 0이 아닌 값을 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**feof**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_feof.c
// This program uses feof to indicate when
// it reaches the end of the file CRT_FEOF.TXT. It also
// checks for errors with ferror.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int  count, total = 0;
   char buffer[100];
   FILE *stream;

   fopen_s( &stream, "crt_feof.txt", "r" );
   if( stream == NULL )
      exit( 1 );

   // Cycle until end of file reached:
   while( !feof( stream ) )
   {
      // Attempt to read in 100 bytes:
      count = fread( buffer, sizeof( char ), 100, stream );
      if( ferror( stream ) )      {
         perror( "Read error" );
         break;
      }

      // Total up actual bytes read
      total += count;
   }
   printf( "Number of bytes read = %d\n", total );
   fclose( stream );
}
```

## <a name="input-crtfeoftxt"></a>입력: crt_feof.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Number of bytes read = 19
```

## <a name="see-also"></a>참고자료

[오류 처리](../../c-runtime-library/error-handling-crt.md)<br/>
[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
