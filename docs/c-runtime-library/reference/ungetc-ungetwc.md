---
title: ungetc, ungetwc
ms.date: 11/04/2016
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: c504540f8fbbe14961fa051bb93ebef350c2c1da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155435"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

스트림에 문자를 다시 푸시합니다.

## <a name="syntax"></a>구문

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
푸시할 문자 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

성공 하면 이러한 함수의 각 반환에서 문자 인수 *c*합니다. 하는 경우 *c* 다시 푸시할 수 없거나 읽은 문자가 없는 경우 입력된 스트림이 변경 하 고 **ungetc** 반환 **EOF**; **ungetwc** 반환 **WEOF**합니다. 하는 경우 *스트림을* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **EOF** 또는 **WEOF** 반환 되 고 **errno** 로 설정 되어 **EINVAL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **ungetc** 함수는 문자를 푸시 *c* 되돌려 *stream* 파일 끝 표시기를 지웁니다. 이때 스트림이 읽기를 위해 열려 있어야 합니다. 후속 읽기 작업이 *스트림을* 시작 *c*합니다. 푸시 하려고 **EOF** 사용 하 여 스트림을 **ungetc** 무시 됩니다.

의해 스트림에 배치 되는 문자 **ungetc** 경우 지워질 수 있습니다 **fflush**, [fseek](fseek-fseeki64.md)하십시오 **fsetpos**, 또는 [rewind](rewind.md) 스트림에서 해당 문자를 읽기 전에 호출 됩니다. 파일 위치 표시기에는 문자가 다시 푸시되기 전의 값이 지정됩니다. 스트림에 해당하는 외부 스토리지는 변경되지 않습니다. 정상적으로 **ungetc** 모든 다시 푸시된 문자를 읽거나 삭제 될 때까지 호출 파일 위치 표시기를 텍스트 스트림에 대해 지정 되지 않습니다. 각 성공적인 **ungetc** 파일 위치 표시기를 이진 스트림에 대해 호출 감소 이며 해당 값을 호출 하기 전에 0 인 경우 값이 정의 된 호출 후 합니다.

결과 예측할 수 없는 경우 **ungetc** 읽기 또는 두 호출 간에 파일 위치 지정 작업을 하지 않고 두 번 호출 됩니다. 호출한 후 **fscanf**에 대 한 호출 **ungetc** 않으면 다른 읽기 작업이 실패할 수 있습니다 (같은 **getc**)을 수행한 합니다. 왜냐하면 **fscanf** 호출 자체 **ungetc**합니다.

**ungetwc** 의 와이드 문자 버전이 **ungetc**합니다. 그러나 각각에서 성공적인 **ungetwc** 텍스트 또는 이진 스트림, 파일 위치 표시기의 값에 대 한 호출에 지정 되지 모든 다시 푸시된 문자를 읽거나 삭제 될 때까지 합니다.

이러한 함수는 스레드로부터 안전하며, 실행 중에 중요한 데이터를 잠급니다. 데이터를 잠그지 않는 버전은 [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
