---
title: fputs, fputws
ms.date: 11/04/2016
apiname:
- fputs
- fputws
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
- fputs
- fputws
- _fputts
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
ms.openlocfilehash: 3f7c7cff3300ae28717062a41aebd9e19c0cb5e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287969"
---
# <a name="fputs-fputws"></a>fputs, fputws

스트림에 문자열을 씁니다.

## <a name="syntax"></a>구문

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
출력 문자열입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 성공할 경우 음수가 아닌 값을 반환합니다. 오류 발생 시 **fputs** 하 고 **fputws** 반환 **EOF**합니다. 하는 경우 *str* 또는 *스트림을* 가 null 포인터인 경우 이러한 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 차례로 **fputs** 반환 **EOF**, 및  **fputws** 반환 **WEOF**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수 복사본 *str* 출력 *스트림* 현재 위치에서. **fputws** 와이드 문자 인수를 복사 *str* 하려면 *스트림* 멀티 바이트 문자 문자열 또는 와이드 문자열로 여부에 따라 *stream*각각에 텍스트 모드 또는 이진 모드로 열려 있습니다. 어떤 함수도 null 종결 문자를 복사하지 않습니다.

스트림이 ANSI 모드에서 열리는 경우 두 함수는 동일하게 작동합니다. **fputs** 유니코드 스트림으로 출력을 현재 지원 하지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputts**|**fputs**|**fputs**|**fputws**|

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fputs**|\<stdio.h>|
|**fputws**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 —**stdin**를 **stdout**, 및 **stderr**-C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
