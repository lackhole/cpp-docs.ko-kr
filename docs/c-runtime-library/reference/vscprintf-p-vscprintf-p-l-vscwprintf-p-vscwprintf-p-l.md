---
title: _vscprintf_p, _vscprintf_p_l, _vscwprintf_p, _vscwprintf_p_l
ms.date: 11/04/2016
apiname:
- _vscprintf_p_l
- _vscprintf_p
- _vscwprintf_p_l
- _vscwprintf_p
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
- _vscprintf_p
- _vscprintf_p_l
- vscwprintf_p
- vscprintf_p
- vscwprintf_p_l
- _vscwprintf_p_l
- vscprintf_p_l
- _vscwprintf_p
helpviewer_keywords:
- vscprintf_p function
- _vsctprintf_p_l function
- vscwprintf_p_l function
- _vscwprintf_p_l function
- _vscprintf_p function
- vsctprintf_p function
- _vscprintf_p_l function
- _vscwprintf_p function
- vscwprintf_p function
- vsctprintf_p_l function
- _vsctprintf_p function
- vscprintf_p_l function
ms.assetid: 5da920b3-8652-4ee9-b19e-5aac3ace9d03
ms.openlocfilehash: 357cc1f28e5495385b67fdb7c1b86bbc15f79950
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386189"
---
# <a name="vscprintfp-vscprintfpl-vscwprintfp-vscwprintfpl"></a>_vscprintf_p, _vscprintf_p_l, _vscwprintf_p, _vscwprintf_p_l

인수가 사용되는 순서를 지정하는 기능과 함께 인수 목록에 대한 포인터를 사용하여 형식이 지정된 문자열의 문자 수를 반환합니다.

## <a name="syntax"></a>구문

```C
int _vscprintf_p(
   const char *format,
   va_list argptr
);
int _vscprintf_p _l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vscwprintf_p (
   const wchar_t *format,
   va_list argptr
);
int _vscwprintf_p _l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>매개 변수

*format*<br/>
형식 컨트롤 문자열입니다.

*argptr*<br/>
인수 목록에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="return-value"></a>반환 값

**_vscprintf_p** 인수 목록이 문자열을 가리키는 경우 생성 될 문자 수를 인쇄 하거나 파일로 전송 또는 지정 된 형식에서 사용 하 여 버퍼에서 코드를 반환 합니다. 반환된 값은 종료 null 문자를 포함하지 않습니다. **_vscwprintf_p** 와이드 문자에 대 한 동일한 기능을 수행 합니다.

## <a name="remarks"></a>설명

이러한 함수에서 다른 **_vscprintf** 하 고 **_vscwprintf** 인수 사용 되는 순서를 지정 하는 기능 지원에 합니다. 자세한 내용은 [printf_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)를 참조하세요.

포함 된 이러한 함수의 버전을 **_l** 접미사는 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

하는 경우 *형식* 가 null 포인터인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 설정 **errno** 하 **EINVAL**합니다.

> [!IMPORTANT]
> 게 *형식* 는 사용자 정의 문자열 종료 null 이며 올바른 수와 형식의 매개 변수가 있습니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsctprintf_p**|**_vscprintf_p**|**_vscprintf_p**|**_vscwprintf_p**|
|**_vsctprintf_p_l**|**_vscprintf_p_l**|**_vscprintf_p_l**|**_vscwprintf_p_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_vscprintf_p**, **_vscprintf_p_l**|\<stdio.h>|
|**_vscwprintf_p**, **_vscwprintf_p_l**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[vsprintf](vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
[_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l](scprintf-p-scprintf-p-l-scwprintf-p-scwprintf-p-l.md)<br/>
[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)<br/>
