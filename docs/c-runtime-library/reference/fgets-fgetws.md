---
title: fgets, fgetws
ms.date: 07/11/2018
apiname:
- fgets
- fgetws
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
- _fgetts
- fgetws
- fgets
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
ms.openlocfilehash: 16dfb7cb0401083960669a735a976fbcd4ad4081
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333864"
---
# <a name="fgets-fgetws"></a>fgets, fgetws

스트림에서 문자열을 가져옵니다.

## <a name="syntax"></a>구문

```C
char *fgets(
   char *str,
   int numChars,
   FILE *stream
);
wchar_t *fgetws(
   wchar_t *str,
   int numChars,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
데이터의 스토리지 위치입니다.

*numChars*<br/>
읽을 최대 문자 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수 반환 *str*합니다. **NULL** 오류 또는 파일 끝 조건을 나타내기 위해 반환 됩니다. 사용 하 여 **feof** 하거나 **ferror** 오류가 발생 한 것인지 확인 합니다. 하는 경우 *str* 하거나 *스트림을* 가 null 포인터인 경우 또는 *numChars* 보다 작거나 0 이면이 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **NULL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

합니다 **fgets** 함수에서 입력 문자열을 읽습니다 *스트림을* 인수에 저장 *str*합니다. **fgets** 에서 현재 스트림 위치가 스트림의 끝에 첫 번째 줄 바꿈 문자를 포함 하 여 문자를 읽거나 문자 수를 읽을 때까지 값과 같음 *numChars* -1을 먼저 도달 합니다. 결과 저장 *str* null 문자를 사용 하 여 추가 됩니다. 줄 바꿈 문자는 읽을 경우 문자열에 포함됩니다.

**fgetws** 의 와이드 문자 버전이 **fgets**합니다.

**fgetws** 와이드 문자 인수를 읽은 *str* 멀티 바이트 문자 문자열 또는 와이드 문자열로 여부에 따라 *스트림* 텍스트 모드 또는 이진 모드로 열려 각각. 텍스트 및 이진 모드를 유니코드 및 멀티바이트 스트림 I/O에서 사용하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [텍스트 및 이진 모드의 유니코드 스트림 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgetts**|**fgets**|**fgets**|**fgetws**|

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fgets**|\<stdio.h>|
|**fgetws**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgets.c
// This program uses fgets to display
// the first line from a file.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[100];

   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )
   {
      if( fgets( line, 100, stream ) == NULL)
         printf( "fgets error\numChars" );
      else
         printf( "%s", line);
      fclose( stream );
   }
}
```

### <a name="input-crtfgetstxt"></a>입력 crt_fgets.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>출력

```Output
Line one.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
