---
title: fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l
ms.date: 11/04/2016
apiname:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
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
- _ftprintf_s
- fprintf_s
- fwprintf_s
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
ms.openlocfilehash: 05886dc4ce7de771749f157913a222b6b01a5c5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333159"
---
# <a name="fprintfs-fprintfsl-fwprintfs-fwprintfsl"></a>fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l

형식이 지정된 데이터를 스트림에 출력합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
int fprintf_s(
   FILE *stream,
   const char *format [,
   argument_list ]
);
int _fprintf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument_list ]
);
int fwprintf_s(
   FILE *stream,
   const wchar_t *format [,
   argument_list ]
);
int _fwprintf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument_list ]
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

*format*<br/>
형식 컨트롤 문자열입니다.

*argument_list*<br/>
형식 문자열에 대 한 선택적 인수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**fprintf_s** 쓴 바이트 수를 반환 합니다. **fwprintf_s** 쓴 와이드 문자의 수를 반환 합니다. 이러한 각 함수는 출력 오류가 발생할 때 대신 음수 값을 반환합니다.

## <a name="remarks"></a>설명

**fprintf_s** 형식을 지정 하 고 일련의 문자 및 출력 값을 인쇄 *스트림*합니다. 각 인수 *argument_list* (있는 경우) 변환 되 고 해당 형식 사양에 따라 출력 *형식*합니다. 합니다 *형식* 인수 사용 합니다 [형식 사양 구문 printf 및 wprintf 함수에 대 한](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다.

**fwprintf_s** 의 와이드 문자 버전이 **fprintf_s**; **fwprintf_s**를 *형식* 는 와이드 문자 문자열입니다. 스트림이 ANSI 모드에서 열리는 경우 이러한 함수는 동일하게 작동합니다. **fprintf_s** 유니코드 스트림으로 출력을 현재 지원 하지 않습니다.

포함 된 이러한 함수의 버전을 **_l** 접미사 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요.

안전 하지 않은 버전과 같이 (참조 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)), 이러한 함수는 매개 변수 유효성 검사 및에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개변수유효성검사](../../c-runtime-library/parameter-validation.md)경우, *스트림* 또는 *형식* 가 null 포인터입니다. 형식 문자열 자체도 유효성이 검사도 됩니다. 알 수 없거나 잘못된 형식의 형식 지정자가 있는 경우 이러한 함수는 잘못된 매개 변수 예외를 생성합니다. 모든 경우에 실행을 계속 하도록 허용 된 경우 함수는-1을 반환 하 고 설정 **errno** 하 **EINVAL**합니다. 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftprintf_s**|**fprintf_s**|**fprintf_s**|**fwprintf_s**|
|**_ftprintf_s_l**|**_fprintf_s_l**|**_fprintf_s_l**|**_fwprintf_s_l**|

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fprintf_s**, **_fprintf_s_l**|\<stdio.h>|
|**fwprintf_s**, **_fwprintf_s_l**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fprintf_s.c
// This program uses fprintf_s to format various
// data and print it to the file named FPRINTF_S.OUT. It
// then displays FPRINTF_S.OUT on the screen using the system
// function to invoke the operating-system TYPE command.

#include <stdio.h>
#include <process.h>

FILE *stream;

int main( void )
{
   int    i = 10;
   double fp = 1.5;
   char   s[] = "this is a string";
   char   c = '\n';

   fopen_s( &stream, "fprintf_s.out", "w" );
   fprintf_s( stream, "%s%c", s, c );
   fprintf_s( stream, "%d\n", i );
   fprintf_s( stream, "%f\n", fp );
   fclose( stream );
   system( "type fprintf_s.out" );
}
```

```Output
this is a string
10
1.500000
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
