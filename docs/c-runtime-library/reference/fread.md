---
title: fread
ms.date: 11/28/2018
apiname:
- fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 7248eb08409b50d855dbb70c7638a856302b345b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287878"
---
# <a name="fread"></a>fread

스트림에서 데이터를 읽습니다.

## <a name="syntax"></a>구문

```C
size_t fread(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
데이터의 스토리지 위치입니다.

*size*<br/>
항목 크기(바이트)입니다.

*count*<br/>
읽힐 항목의 최대 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fread** 일 수 있는 반환 실제로 읽은 아이템의 수 미만 *개수* 오류가 발생 한 경우 또는 파일의 끝에 도달 하기 전에 발견 되 면 *개수*합니다. 사용 된 **feof** 또는 **ferror** 읽기 오류와 파일 끝 조건을 구별 하는 함수입니다. 하는 경우 *크기* 또는 *개수* 0 **fread** 0 고 버퍼 콘텐츠가 변경 되지 않은 반환 합니다. 하는 경우 *스트림을* 또는 *버퍼* 가 null 포인터 **fread** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** 0을 반환 합니다.

참조 [ \_doserrno, errno, \_sys\_errlist, 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 이러한 오류 코드에 대 한 자세한 내용은 합니다.

## <a name="remarks"></a>설명

**fread** 함수를 읽고 *개수* 항목 *크기* 입력에서 바이트 *stream* 에 저장 합니다 *버퍼* . 연결 된 파일 포인터 *스트림을* (있는 경우) 실제로 읽는 바이트 수 만큼 증가 됩니다. 지정 된 스트림으로 열면 [텍스트 모드](../../c-runtime-library/text-and-binary-mode-file-i-o.md), Windows 스타일 줄 바꿈 Unix 스타일 줄 바꿈 변환 됩니다. 즉, 캐리지 리턴-줄 바꿈 (CRLF) 쌍은 단일 줄 바꿈 (LF) 문자로 대체 됩니다. 이렇게 바뀌더라도 파일 포인터 또는 반환 값에는 영향을 미치지 않습니다. 오류가 발생할 경우 파일 포인터 위치는 비활성화 상태입니다. 부분적으로 읽은 항목의 값은 확인할 수 없습니다.

텍스트 모드 스트림 데이터의 양이 요청 된 경우 사용 하는 경우 (즉, *크기* \* *개수*) 보다 크거나 같은 내부 **파일** \*버퍼 크기 (기본적으로이 4096 바이트를 사용 하 여 구성할 수 있습니다 [setvbuf](../../c-runtime-library/reference/setvbuf.md)), 스트림 데이터는 사용자가 제공한 버퍼에 직접 복사 되 고 해당 버퍼에 줄 바꿈 변환이 수행 됩니다. 변환된 된 데이터는 지난 데이터 버퍼에 복사 하는 스트림 데이터를 보다 짧은 수 있으므로 *버퍼*\[*return_value* \* *크기*] ( 여기서 *return_value* 의 반환 값은 **fread**) 파일에서 변환 되지 않은 데이터를 포함할 수 있습니다. 이러한 이유로 있습니다를 null로 종료 문자 데이터에 권장 *버퍼*\[*return_value* \* *크기*] 버퍼의 의도 한 경우 에 C 스타일 문자열로 작동 합니다. 참조 [fopen](fopen-wfopen.md) 텍스트 모드 및 이진 모드에 미치는 영향에 대 한 세부 정보에 대 한 합니다.

이 함수는 다른 스레드를 잠급니다. 잠기지 않는 버전을 해야 하는 경우 사용 하 여 **_fread_nolock**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fread**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fread.c
// This program opens a file named FREAD.OUT and
// writes 25 characters to the file. It then tries to open
// FREAD.OUT and read in 25 characters. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   // Open file in text mode:
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )
   {
      for ( i = 0; i < 25; i++ )
         list[i] = (char)('z' - i);
      // Write 25 characters to stream
      numwritten = fwrite( list, sizeof( char ), 25, stream );
      printf( "Wrote %d items\n", numwritten );
      fclose( stream );

   }
   else
      printf( "Problem opening the file\n" );

   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )
   {
      // Attempt to read in 25 characters
      numread = fread( list, sizeof( char ), 25, stream );
      printf( "Number of items read = %d\n", numread );
      printf( "Contents of buffer = %.25s\n", list );
      fclose( stream );
   }
   else
      printf( "File could not be opened\n" );
}
```

```Output
Wrote 25 items
Number of items read = 25
Contents of buffer = zyxwvutsrqponmlkjihgfedcb
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[텍스트 및 이진 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
