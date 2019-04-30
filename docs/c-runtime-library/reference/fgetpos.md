---
title: fgetpos
ms.date: 11/04/2016
apiname:
- fgetpos
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
- fgetpos
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
ms.openlocfilehash: e213c9830ffe6edf04b12a80828f14cc48f77524
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333932"
---
# <a name="fgetpos"></a>fgetpos

스트림의 파일 위치 표시기를 가져옵니다.

## <a name="syntax"></a>구문

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
대상 스트림입니다.

*pos*<br/>
위치 표시기 스토리지입니다.

## <a name="return-value"></a>반환 값

성공 하면 **fgetpos** 0을 반환 합니다. 오류가 발생 하면 0이 아닌 값을 반환 하 고 설정 **errno** 다음 중 하나를 매니페스트 상수 (STDIO에 정의 합니다. H): **EBADF**, 즉, 지정 된 스트림에 유효한 파일 포인터가 아니거나에 액세스할 수 없는 또는 **EINVAL**를 의미 합니다 *스트림* 값 또는 값 *pos*가 유효한 경우와 같이 하거나가 null 포인터가 아닌 합니다. 하는 경우 *스트림을* 또는 *pos* 되는 **NULL** 포인터에 설명 된 대로 함수가 잘못 된 매개 변수 처리기를 호출 하 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>설명

**fgetpos** 함수는 현재 값을 가져옵니다 합니다 *스트림* 인수 파일 위치 표시기 및 저장소에서 가리키는 개체에 *pos*합니다. 합니다 **fsetpos** 함수에 저장 된 정보를 나중에 사용할 수 있습니다 *pos* 다시 설정 하는 *stream* 해당 위치에 대 한 포인터 인수 **fgetpos** 였습니다. 합니다 *pos* 값을 내부 형식에 저장 되 고 사용 하기 위한 에서만 **fgetpos** 하 고 **fsetpos**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetpostxt"></a>입력: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crtfgetpostxt"></a>출력 crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
