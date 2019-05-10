---
title: _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l
ms.date: 11/04/2016
apiname:
- _fwprintf_p
- _fprintf_p_l
- _fwprintf_p_l
- _fprintf_p
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
- _fprintf_p
- _ftprintf_p
- fwprintf_p
- _fwprintf_p
- fprintf_p
- ftprintf_p
helpviewer_keywords:
- fprintf_p_l function
- fprintf_p function
- _fprintf_p_l function
- _fprintf_p function
- _ftprintf_p_l function
- streams, printing formatted data to
- _fwprintf_p function
- fwprintf_p function
- _ftprintf_p function
- _fwprintf_p_l function
- ftprintf_p function
- printing [C++], formatted data to streams
- ftprintf_p_l function
- fwprintf_p_l function
ms.assetid: 46b082e1-45ba-4383-9ee4-97015aa50bc6
ms.openlocfilehash: db9e9a746193c7bf35913d6792d87aa9ba85fa79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333146"
---
# <a name="fprintfp-fprintfpl-fwprintfp-fwprintfpl"></a>_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l

서식이 지정된 데이터를 스트림으로 출력합니다.

## <a name="syntax"></a>구문

```C
int _fprintf_p(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fprintf_p_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int _fwprintf_p(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwprintf_p_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

*format*<br/>
형식 컨트롤 문자열입니다.

*argument*<br/>
선택적 인수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_fprintf_p** 하 고 **_fwprintf_p** 작성 된 문자 수를 반환 하거나 출력 오류가 발생 하는 경우 음수 값을 반환 합니다.

## <a name="remarks"></a>설명

**_fprintf_p** 형식을 지정 하 고 일련의 문자 및 출력 값을 인쇄 *스트림*합니다. 각 함수 *인수* (있는 경우) 변환 되 고 해당 형식 사양에 따라 출력 *형식*합니다. 에 대 한 **_fprintf_p**서 *형식* 인수가 동일한 구문 및 사용에 있는 **_printf_p**합니다. 이러한 함수는 위치 매개 변수를 지원하므로 서식 문자열에서 사용된 매개 변수의 순서를 변경할 수 있습니다. 위치 매개 변수에 대한 자세한 내용은 [printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.

**_fwprintf_p** 의 와이드 문자 버전이 **_fprintf_p**; **_fwprintf_p**를 *형식* 는 와이드 문자 문자열입니다. 스트림이 ANSI 모드에서 열리는 경우 이러한 함수는 동일하게 작동합니다. **_fprintf_p** 유니코드 스트림으로 출력을 현재 지원 하지 않습니다.

포함 된 이러한 함수의 버전을 **_l** 접미사 현재 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요.

안전 하지 않은 버전과 같이 (참조 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)), 이러한 함수는 매개 변수 유효성 검사 및에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개변수유효성검사](../../c-runtime-library/parameter-validation.md)경우, *스트림* 또는 *형식* 가 null 포인터 이거나 알 수 없거나 잘못 된 형식의 서식 지정 자가 있는 경우. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 설정 **errno** 하 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_ftprintf_p**|**_fprintf_p**|**_fprintf_p**|**_fwprintf_p**|
|**_ftprintf_p_l**|**_fprintf_p_l**|**_fprintf_p_l**|**_fwprintf_p_l**|

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_fprintf_p**, **_fprintf_p_l**|\<stdio.h>|
|**_fwprintf_p**, **_fwprintf_p_l**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fprintf_p.c
// This program uses _fprintf_p to format various
// data and print it to the file named FPRINTF_P.OUT. It
// then displays FPRINTF_P.OUT on the screen using the system
// function to invoke the operating-system TYPE command.
//

#include <stdio.h>
#include <process.h>

int main( void )
{
    FILE    *stream = NULL;
    int     i = 10;
    double  fp = 1.5;
    char    s[] = "this is a string";
    char    c = '\n';

    // Open the file
    if ( fopen_s( &stream, "fprintf_p.out", "w" ) == 0)
    {
        // Format and print data
        _fprintf_p( stream, "%2$s%1$c", c, s );
        _fprintf_p( stream, "%d\n", i );
        _fprintf_p( stream, "%f\n", fp );

        // Close the file
        fclose( stream );
    }

    // Verify our data
    system( "type fprintf_p.out" );
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
[printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
