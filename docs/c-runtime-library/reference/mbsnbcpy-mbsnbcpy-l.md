---
title: _mbsnbcpy, _mbsnbcpy_l
ms.date: 11/04/2016
apiname:
- _mbsnbcpy
- _mbsnbcpy_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsnbcpy
- _ftcsncpy
- _mbsnbcpy
- mbsnbcpy_l
- _mbsnbcpy_l
helpviewer_keywords:
- mbsnbcpy function
- _mbsnbcpy_l function
- _mbsnbcpy function
- _tcsncpy function
- tcsncpy_l function
- _tcsncpy_l function
- mbsnbcpy_l function
- tcsncpy function
ms.assetid: 83d17b50-3cbf-4df9-bce8-3b6d52f85d04
ms.openlocfilehash: 1f22e8066b5b32feef642b01ad82955935a450e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285576"
---
# <a name="mbsnbcpy-mbsnbcpyl"></a>_mbsnbcpy, _mbsnbcpy_l

복사본 **n** 바이트를 대상 문자열에는 문자열입니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)을 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
unsigned char * _mbsnbcpy(
   unsigned char * strDest,
   const unsigned char * strSource,
   size_t count
);
unsigned char * _mbsnbcpy_l(
   unsigned char * strDest,
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char * _mbsnbcpy(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char * _mbsnbcpy_l(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*strDest*<br/>
복사할 문자열의 대상입니다.

*strSource*<br/>
복사할 문자열입니다.

*count*<br/>
복사할 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbsnbcpy** 대상 문자열에 대 한 포인터를 반환 합니다. 반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.

## <a name="remarks"></a>설명

**_mbsnbcpy** 복사본 함수 *개수* 바이트 *strSource* 하 *strDest*합니다. 하는 경우 *개수* 크기를 초과 *strDest* 또는 소스 문자열과 대상 문자열이 겹치는 동작 **_mbsnbcpy** 정의 되지 않습니다.

하는 경우 *strSource* 또는 *strDest* 가 null 포인터인 경우이 함수에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 함수 반환 **NULL** 설정 **errno** 하 **EINVAL**합니다.

출력 값의 설정이 적용 됩니다는 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 자세한 내용은 합니다. 이러한 함수의 버전은 동일 점을 제외 되지 않은 합니다 **_l** 접미사가 있는 버전 현재 로캘을 사용 합니다 **_l** 로캘 매개 변수를 대신 사용 하는 접미사는 에 전달 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

> [!IMPORTANT]
> 이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다. 버퍼 오버런은 보증되지 않은 권한 승격을 초래하거나 시스템을 위태롭게 하는 임의의 공격자 코드를 실행하기 위해 사용될 수 있습니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncpy**|[strncpy](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|**_mbsnbcpy**|[wcsncpy](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|
|**_tcsncpy_l**|**_strncpy_l**|**_mbsnbcp_l**|**_wcsncpy_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbcpy**|\<mbstring.h>|
|**_mbsnbcpy_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
