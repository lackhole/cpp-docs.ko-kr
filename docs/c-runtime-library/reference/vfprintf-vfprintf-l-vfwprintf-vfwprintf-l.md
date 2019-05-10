---
title: vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l
ms.date: 11/04/2016
apiname:
- _vfprintf_l
- vfprintf
- vfwprintf
- _vfwprintf_l
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
- vfwprintf
- _vftprintf
- vfprintf
helpviewer_keywords:
- _vfwprintf_l function
- _vftprintf function
- vfprintf function
- _vftprintf_l function
- vfprintf_l function
- vftprintf_l function
- vfwprintf_l function
- vftprintf function
- vfwprintf function
- _vfprintf_l function
- formatted text [C++]
ms.assetid: 4443be50-cedf-40b2-b3e2-ff2b3af3b666
ms.openlocfilehash: 889fedde263b9815597702f1e9d5b252f3998bdd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364898"
---
# <a name="vfprintf-vfprintfl-vfwprintf-vfwprintfl"></a>vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l

인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다. 이러한 함수의 더 안전한 버전이 있습니다. [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)을 참조하세요.

## <a name="syntax"></a>구문

```C
int vfprintf(
   FILE *stream,
   const char *format,
   va_list argptr
);
int _vfprintf_l(
   FILE *stream,
   const char *format,
   locale_t locale,
   va_list argptr
);
int vfwprintf(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
int _vfwprintf_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

*format*<br/>
형식 사양입니다.

*argptr*<br/>
인수 목록에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="return-value"></a>반환 값

**vfprintf** 하 고 **vfwprintf** 출력 오류가 발생 하면 null 종결 문자 또는 음수 값을 포함 하지 않고 작성 된 문자 수를 반환 합니다. 경우 *스트림을* 하거나 *형식* 가 null 포인터인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 설정 **errno** 하 **EINVAL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

이러한 함수는 각각 인수 목록에 대 한 포인터 형식을 지정 하 고 지정된 된 데이터를 씁니다 *스트림을*합니다.

**vfwprintf** 의 와이드 문자 버전이 **vfprintf**; 두 함수는 스트림이 ANSI 모드에서 열리는 경우 동일 하 게 작동 합니다. **vfprintf** 유니코드 스트림으로 출력을 현재 지원 하지 않습니다.

포함 된 이러한 함수의 버전을 **_l** 접미사는 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftprintf**|**vfprintf**|**vfprintf**|**vfwprintf**|
|**_vftprintf_l**|**_vfprintf_l**|**_vfprintf_l**|**_vfwprintf_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**vfprintf**, **_vfprintf_l**|\<stdio.h> 및 \<stdarg.h>|\<varargs.h>*|
|**vfwprintf**, **_vfwprintf_l**|\<stdio.h> 또는 \<wchar.h> 및 \<stdarg.h>|\<varargs.h>*|

\* UNIX V 호환성을 위해 필요합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
