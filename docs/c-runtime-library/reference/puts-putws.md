---
title: puts, _putws
ms.date: 11/04/2016
api_name:
- _putws
- puts
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
- _putts
- _putws
- puts
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
ms.openlocfilehash: 1cd38678b321853cb229d86f9554bb76efbc84d6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949794"
---
# <a name="puts-_putws"></a>puts, _putws

**stdout**에 문자열을 씁니다.

## <a name="syntax"></a>구문

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
출력 문자열입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되면 음수가 아닌 값을 반환합니다. **Put** 이 실패 하면 **EOF**를 반환 합니다. **_putws** 가 실패할 경우 **weof**를 반환 합니다. *Str* 이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 **EOF** 또는 **weof**를 반환 합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**Put** 함수는 문자열의 종료 null 문자 (' \ 0 ')를 출력 스트림에서 줄 바꿈 문자 (' \n ')로 바꿔서 표준 출력 스트림 **stdout**에 *str* 을 씁니다.

**_putws** 는 **put**의 와이드 문자 버전입니다. 두 함수는 스트림이 ANSI 모드에서 열리는 경우 동일 하 게 동작 합니다. **put** 은 현재 유니코드 스트림에 대 한 출력을 지원 하지 않습니다.

**_putwch** 는 현재 콘솔 로캘 설정을 사용 하 여 유니코드 문자를 씁니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**puts**|**puts**|**_putws**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**puts**|\<stdio.h>|
|**_putws**|\<stdio.h>|

이 콘솔은 UWP (유니버설 Windows 플랫폼) 앱에서 지원 되지 않습니다. 콘솔, **stdin**, **stdout**및 **stderr**에 연결 된 표준 스트림 핸들은 C 런타임 함수가 UWP 앱에서 사용할 수 있으려면 먼저 리디렉션해야 합니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>출력

```Output
Hello world from puts!
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
