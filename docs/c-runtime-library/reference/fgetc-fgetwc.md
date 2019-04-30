---
title: fgetc, fgetwc
ms.date: 11/04/2016
apiname:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: a853a46fc43106c9ea57be84b37fb46a18041ba8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334010"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

스트림에서 문자를 읽습니다.

## <a name="syntax"></a>구문

```C
int fgetc(
   FILE *stream
);
wint_t fgetwc(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fgetc** 으로 읽은 문자를 반환 합니다.는 **int** 하거나 반환 **EOF** 오류 또는 파일의 끝을 나타냅니다. **fgetwc** 반환으로 [wint_t](../../c-runtime-library/standard-types.md), 읽은 문자에 해당 하거나 반환 하는 와이드 문자 **WEOF** 오류 또는 파일의 끝을 나타냅니다. 두 함수 모두 사용 하 여 **feof** 또는 **ferror** 오류와 파일 끝 조건을 구분 하려면. 읽기 오류가 발생하는 경우 스트림에 대한 오류 표시기가 설정됩니다. 경우 *스트림을* 됩니다 **NULL**, **fgetc** 하 고 **fgetwc** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **EOF**합니다.

## <a name="remarks"></a>설명

이러한 각 함수에 연결 된 파일의 현재 위치에서 단일 문자를 읽습니다 *스트림을*합니다. 그러고 나서 다음 문자를 가리킬 연결된 파일 포인터(정의된 경우)를 늘립니다. 스트림이 파일 끝에 있는 경우 스트림에 대한 파일 끝 표시기가 설정됩니다.

**fgetc** 같습니다 **getc**, 함수 및 매크로가 아닌 함수로 구현 됩니다.

**fgetwc** 의 와이드 문자 버전이 **fgetc**; 읽습니다 **c** 멀티 바이트 문자 또는 여부에 따라 와이드 문자로 *stream* 에서 열릴 텍스트 모드 또는 이진 모드로 합니다.

**_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다.

와이드 문자 및 멀티바이트 문자를 텍스트 모드 및 이진 모드에서 처리하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드에서 유니코드 스트림 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgetc.c
// This program uses getc to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   char buffer[81];
   int  i, ch;

   // Open file to read line from:
   fopen_s( &stream, "crt_fgetc.txt", "r" );
   if( stream == NULL )
      exit( 0 );

   // Read in first 80 characters and place them in "buffer":
   ch = fgetc( stream );
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = fgetc( stream );
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetctxt"></a>입력: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Line one.
Line two.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
