---
title: putchar, putwchar
ms.date: 11/04/2016
apiname:
- putchar
- putwchar
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
- putchar
- putwchar
- _puttchar
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
ms.openlocfilehash: becee3d79f58ac018d1161c1af36e9a4646640bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357997"
---
# <a name="putchar-putwchar"></a>putchar, putwchar

**stdout**에 문자를 씁니다.

## <a name="syntax"></a>구문

```C
int putchar(
   int c
);
wint_t putwchar(
   wchar_t c
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
쓸 문자입니다.

## <a name="return-value"></a>반환 값

쓴 문자를 반환합니다. 오류 또는 파일 끝 조건을 나타내기 위해 **putc** 하 고 **putchar** 반환 **EOF**; **putwc** 하 고 **putwchar** 반환 **WEOF**합니다. 4개 루틴 모두에 대해 [ferror](ferror.md) 또는 [feof](feof.md)를 사용하여 오류 또는 파일 끝을 확인합니다. Null 포인터에 전달 되 면 *스트림을*, 이러한 함수에 설명 된 대로 잘못 된 매개 변수 예외를 생성할 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 반환 **EOF** 또는 **WEOF** 설정 하 고 **errno** 하 **EINVAL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

합니다 **putc** 루틴 단일 문자를 씁니다 *c* 출력 *stream* 현재 위치에서. 임의의 정수를 전달할 수 **putc**, 낮은 8 비트만 기록 됩니다. 합니다 **putchar** 루틴은 동일 `putc( c, stdout )`합니다. 각 루틴에 대해 읽기 오류가 발생하는 경우 스트림에 대한 오류 표시기가 설정됩니다. **putc** 하 고 **putchar** 비슷합니다 **fputc** 하 고 **_fputchar**각각 함수 및 매크로로 구현 됩니다 (참조 [ 함수와 매크로 중 선택](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **putwc** 하 고 **putwchar** 와이드 문자 버전입니다 **putc** 하 고 **putchar**, 각각.

**_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다. 이러한 버전에서는 다른 스레드를 잠그는 오버헤드가 발생하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 애플리케이션과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttchar**|**putchar**|**putchar**|**putwchar**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**putchar**|\<stdio.h>|
|**putwchar**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_putchar.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;

   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putchar( *p );
}
```

### <a name="output"></a>출력

```Output
This is the line of output
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
