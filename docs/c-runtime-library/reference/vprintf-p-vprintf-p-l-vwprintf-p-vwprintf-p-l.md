---
title: _vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l
ms.date: 11/04/2016
apiname:
- _vwprintf_p
- _vprintf_p
- _vprintf_p_l
- _vwprintf_p_l
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
- _vwprintf_p_l
- vprintf_p
- _vprintf_p_l
- _vwprintf_p
- vprintf_p_l
- vwprintf_p_l
- vwprintf_p
- vtprintf_p
- _vtprintf_p
- _vprintf_p
helpviewer_keywords:
- _vtprintf_p_l function
- _vtprintf_p function
- vtprintf_p function
- _vwprintf_p function
- _vwprintf_p_l function
- _vprintf_p function
- _vprintf_p_l function
- vprintf_p_l function
- vwprintf_p function
- vprintf_p function
- vtprintf_p_l function
- vwprintf_p_l function
- formatted text [C++]
ms.assetid: 3f99bde3-c891-493d-908f-30559c421058
ms.openlocfilehash: 266df8c033fc9d1c8459aff9f2b95771947d88d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364703"
---
# <a name="vprintfp-vprintfpl-vwprintfp-vwprintfpl"></a>_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l

인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 작성하고, 인수가 사용되는 순서를 지정할 수 있도록 설정합니다.

## <a name="syntax"></a>구문

```C
int _vprintf_p(
   const char *format,
   va_list argptr
);
int _vprintf_p_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vwprintf_p(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_p_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>매개 변수

*format*<br/>
형식 사양입니다.

*argptr*<br/>
인수 목록에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="return-value"></a>반환 값

**_vprintf_p** 하 고 **_vwprintf_p** 출력 오류가 발생 하면 null 종결 문자 또는 음수 값을 포함 하지 않고 작성 된 문자 수를 반환 합니다.

## <a name="remarks"></a>설명

이러한 함수는 각각 인수 목록에 대 한 포인터 형식을 지정 하 고 지정된 된 데이터를 씁니다 **stdout**합니다. 이러한 함수에서 다른 **vprintf_s** 하 고 **vwprintf_s** 인수 사용 되는 순서를 지정 하는 기능 지원에 합니다. 자세한 내용은 [printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.

**_vwprintf_p** 의 와이드 문자 버전이 **_vprintf_p**; 두 함수는 스트림이 ANSI 모드에서 열리는 경우 동일 하 게 작동 합니다. **_vprintf_p** 유니코드 스트림으로 출력을 현재 지원 하지 않습니다.

포함 된 이러한 함수의 버전을 **_l** 접미사는 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

하는 경우 *형식* 가 null 포인터인 경우 또는에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 형식 문자열이 잘못 된 서식 문자열을 포함 하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 설정 **errno** 하 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf_p**|**_vprintf_p**|**_vprintf_p**|**_vwprintf_p**|
|**_vtprintf_p_l**|**_vprintf_p_l**|**_vprintf_p_l**|**_vwprintf_p_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**_vprintf_p**, **_vprintf_p_l**|\<stdio.h> 및 \<stdarg.h>|\<varargs.h>*|
|**_vwprintf_p**, **_vwprintf_p_l**|\<stdio.h> 또는 \<wchar.h> 및 \<stdarg.h>|\<varargs.h>*|

\* UNIX V 호환성을 위해 필요합니다.

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
