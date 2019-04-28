---
title: vsscanf, vswscanf
ms.date: 11/04/2016
apiname:
- vsscanf
- vswscanf
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
- _vstscanf
- vsscanf
- vswscanf
helpviewer_keywords:
- vswscanf function
- vsscanf function
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
ms.openlocfilehash: 5bbe80cd2463c5c5b9b4ea55b8d6574675e42054
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188862"
---
# <a name="vsscanf-vswscanf"></a>vsscanf, vswscanf

문자열에서 형식이 지정된 데이터를 읽습니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [vsscanf_s, vswscanf_s](vsscanf-s-vswscanf-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int vsscanf(
   const char *buffer,
   const char *format,
   va_list arglist
);
int vswscanf(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
저장된 데이터

*format*<br/>
형식 컨트롤 문자열입니다. 자세한 내용은 [서식 지정 필드: scanf 함수 및 wscanf 함수](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)를 참조하세요.

*arglist*<br/>
가변 인수 목록입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 모두 성공적으로 변환되고 할당된 필드 수를 반환합니다. 이때 읽혀졌지만 할당되지 않은 필드는 반환 값에 포함되지 않습니다. 반환 값이 0이면 할당된 필드가 없음을 나타냅니다. 반환 값은 **EOF** 오류에 대 한 첫 번째 변환 전에 문자열의 끝에 도달 하면 또는 합니다.

하는 경우 *버퍼* 또는 *형식* 되는 **NULL** 에 설명 된 대로 포인터인 경우 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수가-1를 반환 하는 설정 **errno** 하 **EINVAL**합니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **vsscanf** 함수에서 데이터를 읽는 *버퍼* 각 인수에 의해 지정 된 위치에는 *arglist* 인수 목록입니다. 목록의 모든 인수에 대 한 포인터의 형식 지정자에 해당 하는 형식이 있는 변수 여야 합니다 *형식*합니다. *형식* 인수 해석을 제어 하는 입력 필드 동일한 폼 및 함수는 *형식* 에 대 한 인수를 **scanf** 함수. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.

> [!IMPORTANT]
> 사용 하는 경우 **vsscanf** 문자열을 읽고, 항상 너비를 지정 합니다 **%s** 형식 (예를 들어 **"32 초 %"** 대신 **"%s"**); 그렇지 않으면 서식이 잘못 된 입력 버퍼 오버런이 발생할 수 있습니다.

**vswscanf** 의 와이드 문자 버전이 **vsscanf**;에 대 한 인수 **vswscanf** 는 와이드 문자 문자열입니다. **vsscanf** 멀티 바이트 16 진수 문자를 처리 하지 않습니다. **vswscanf** 유니코드 전자 16 진수 또는 "호환 영역" 문자를 처리 하지 않습니다. 그렇지 않으면 **vswscanf** 하 고 **vsscanf** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf**|**vsscanf**|**vsscanf**|**vswscanf**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**vsscanf**|\<stdio.h>|
|**vswscanf**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_vsscanf.c
// compile with: /W3
// This program uses vsscanf to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>

int call_vsscanf(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf(tokenstring, format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    char  tokenstring[] = "15 12 14...";
    char  s[81];
    char  c;
    int   i;
    float fp;

    // Input various data from tokenstring:
    // max 80 character string:
    call_vsscanf(tokenstring, "%80s", s);
    call_vsscanf(tokenstring, "%c", &c);
    call_vsscanf(tokenstring, "%d", &i);
    call_vsscanf(tokenstring, "%f", &fp);

    // Output the data read
    printf("String    = %s\n", s);
    printf("Character = %c\n", c);
    printf("Integer:  = %d\n", i);
    printf("Real:     = %f\n", fp);
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf_s, vswscanf_s](vsscanf-s-vswscanf-s.md)<br/>
