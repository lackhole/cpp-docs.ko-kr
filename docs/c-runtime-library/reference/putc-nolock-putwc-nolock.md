---
title: _putc_nolock, _putwc_nolock
ms.date: 11/04/2016
api_name:
- _putc_nolock
- _putwc_nolock
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _puttc_nolock
- puttc_nolock
- putwc_nolock
- _putwc_nolock
- _putc_nolock
- putc_nolock
helpviewer_keywords:
- puttc_nolock function
- putc_nolock function
- _putc_nolock function
- streams, writing characters to
- characters, writing
- putwc_nolock function
- _puttc_nolock function
- _putwc_nolock function
ms.assetid: 3cfc7f21-c9e8-4b7f-b0fb-af0d4d85e7e1
ms.openlocfilehash: fdec6373f79fd711b371014fc58e17c190a26e95
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950127"
---
# <a name="_putc_nolock-_putwc_nolock"></a>_putc_nolock, _putwc_nolock

스레드를 잠그지 않고 스트림에 문자를 씁니다.

## <a name="syntax"></a>구문

```C
int _putc_nolock(
   int c,
   FILE *stream
);
wint_t _putwc_nolock(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
쓸 문자입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**putc, putwc**를 참조하세요.

## <a name="remarks"></a>설명

**_putc_noand** **_putwc_nolock** 는 다른 스레드의 간섭 으로부터 보호 되지 않는다는 점을 제외 하면 **_nolock** 접미사가 없는 버전과 동일 합니다. 이들은 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 애플리케이션과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.

**_putwc_nolock** 는 **_putc_nolock**의 와이드 문자 버전입니다. 두 함수는 스트림이 ANSI 모드에서 열리는 경우 동일 하 게 동작 합니다. **_putc_nolock** 은 현재 UNICODE 스트림에 대 한 출력을 지원 하지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttc_nolock**|**_putc_nolock**|**_putc_nolock**|**_putwc_nolock**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_putc_nolock**|\<stdio.h>|
|**_putwc_nolock**|\<stdio.h> 또는 \<wchar.h>|

이 콘솔은 UWP (유니버설 Windows 플랫폼) 앱에서 지원 되지 않습니다. 콘솔, **stdin**, **stdout**및 **stderr**에 연결 된 표준 스트림 핸들은 C 런타임 함수가 UWP 앱에서 사용할 수 있으려면 먼저 리디렉션해야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_putc_nolock.c
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
   /* Make standard out the stream and write to it. */
   stream = stdout;
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = _putc_nolock( *p, stream );
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
