---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
ms.date: 03/26/2019
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
ms.openlocfilehash: 28697cac20181c3dda0581c7486ebb673aec1241
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508804"
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l

표준 입력 스트림에서 형식이 지정된 데이터를 읽습니다. 이러한 버전의 [scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
int scanf_s(
   const char *format [,
   argument]...
);
int _scanf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf_s(
   const wchar_t *format [,
   argument]...
);
int _wscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>매개 변수

*format*<br/>
형식 컨트롤 문자열입니다.

*argument*<br/>
선택적 인수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공적으로 변환 하 고 할당 된 필드 수를 반환 합니다. 반환 값 혀 졌지만 할당 되지 않은 필드를 포함 하지 않습니다. 반환 값이 0 할당 된 필드가 없음을 나타냅니다. 반환 값은 **EOF** , 오류가 발생 한 파일의 끝 문자 또는 문자열의 끝 문자는 문자를 읽는 첫 번째 시도에서 발견 되 면 또는 합니다. 하는 경우 *형식* 되는 **NULL** 에 설명 된 대로 포인터인 경우 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **scanf_s** 하 고 **wscanf_s** 반환 **EOF** 설정 하 고 **errno** 에 **EINVAL**.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **scanf_s** 함수는 표준 입력 스트림에서 데이터를 읽고 **stdin**에 씁니다 *인수*합니다. 각 *인수* 의 형식 지정자에 해당 하는 변수 형식에 대 한 포인터 여야 합니다 *형식*합니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.

**wscanf_s** 의 와이드 문자 버전이 **scanf_s**; *형식* 인수를 **wscanf_s** 는 와이드 문자 문자열입니다. **wscanf_s** 하 고 **scanf_s** 스트림이 ANSI 모드에서 열리는 경우 동일 하 게 작동 합니다. **scanf_s** 현재 UNICODE 스트림에서의 입력을 지원 하지 않습니다.

접미사가 있는 이러한 함수 버전을 **_l** 접미사를 사용 하는 점을 제외 하면 동일 합니다 *로캘* 현재 스레드 로캘 대신 매개 변수.

와 달리 **scanf** 하 고 **wscanf**에 **scanf_s** 및 **wscanf_s** 일부 매개 변수에 대 한 버퍼 크기를 지정 해야 합니다. 모든 크기를 지정할 **c**, **C**를 **s**를 **S**, 또는 컨트롤 집합을 문자열 **[]** 매개 변수입니다. 문자 버퍼 크기는 추가 매개 변수로 전달 됩니다. 즉시 버퍼 또는 변수에 대 한 포인터를 따릅니다. 예를 들어 문자열을 읽는 경우 해당 문자열에 대 한 버퍼 크기를 같이 전달 됩니다.

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

버퍼 크기를 터미널 null을 포함합니다. 확인 토큰 맞도록 버퍼에서에서 읽을 수 있는 너비 사양 필드를 사용할 수 있습니다. 토큰에 맞게 너무 큰 경우 아무 것도 쓰지 버퍼에 너비 사양 경우를 제외 합니다.

> [!NOTE]
> 크기 매개 변수는 형식 **unsigned**가 아닌 **size_t**합니다. 정적 캐스트를 사용 하 여 변환할를 **size_t** 값을 **부호 없는** 64 비트 빌드 구성 합니다.

버퍼 크기 매개 변수가 바이트가 아닌 문자의 최대 수를 설명합니다. 이 예제에서는 버퍼 유형의 너비 형식 지정자의 너비를 일치 하지 않습니다.

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

합니다 **S** 형식 지정자 문자 너비의 "기본 너비 반대"에서 지 원하는 함수를 사용 하 여 의미 합니다. 문자 너비는 싱글바이트, 하지만 함수는 더블 바이트 문자를 지원 합니다. 이 예제에서는 최대 9 개의 단일 바이트 와이드 문자 문자열의 문자를 읽고 더블 바이트 와이드 문자 버퍼에 넣습니다. 문자는 싱글바이트 값으로 처리됩니다. 처음 두 문자는 `ws[0]`에 저장되고, 두 번째 두 문자는 `ws[1]`에 저장되는 방식입니다.

이 예제에서는 단일 문자를 읽습니다.

```C
char c;
scanf_s("%c", &c, 1);
```

Null로 끝나지 않는 문자열에 대 한 여러 문자를 읽을 때 정수는 너비 사양 및 버퍼 크기를 둘 다에 사용 됩니다.

```C
char c[4];
scanf_s("%4c", c, (unsigned)_countof(c)); // not null terminated
```

자세한 내용은 [scanf 너비 사양](../../c-runtime-library/scanf-width-specification.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

자세한 내용은 [서식 지정 필드: scanf 함수 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**scanf_s**, **_scanf_s_l**|\<stdio.h>|
|**wscanf_s**, **_wscanf_s_l**|\<stdio.h> 또는 \<wchar.h>|

콘솔은 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr** C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_scanf_s.c
// This program uses the scanf_s and wscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int      i,
            result;
   float    fp;
   char     c,
            s[80];
   wchar_t  wc,
            ws[80];

   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,
           wc, s, ws);
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,
            c, wc, s, ws);
}
```

이 프로그램을 실행하면 이 입력이 제공될 때 다음 출력이 생성됩니다.

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
