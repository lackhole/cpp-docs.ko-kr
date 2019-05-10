---
title: _mbsnbcat, _mbsnbcat_l
ms.date: 11/04/2016
apiname:
- _mbsnbcat_l
- _mbsnbcat
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
- mbsnbcat
- mbsnbcat_l
- _mbsnbcat
- _mbsnbcat_l
helpviewer_keywords:
- tcsncat_l function
- _tcsncat function
- mbsnbcat_l function
- mbsnbcat function
- _mbsnbcat_l function
- _tcsncat_l function
- _mbsnbcat function
- tcsncat function
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
ms.openlocfilehash: c1da330ee0faba922f1e5b193fa095b97d3f4745
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285560"
---
# <a name="mbsnbcat-mbsnbcatl"></a>_mbsnbcat, _mbsnbcat_l

첫 번째를 추가 **n** 다른 하나의 멀티 바이트 문자열의 바이트입니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)을 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
unsigned char *_mbsnbcat(
   unsigned char *dest,
   const unsigned char *src,
   size_t count
);
unsigned char *_mbsnbcat_l(
   unsigned char *dest,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char *_mbsnbcat(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsnbcat_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
null로 끝나는 멀티바이트 문자 대상 문자열입니다.

*src*<br/>
null로 끝나는 멀티바이트 문자 소스 문자열입니다.

*count*<br/>
바이트 수가 *src* 에 추가할 *dest*합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbsnbcat** 대상 문자열에 대 한 포인터를 반환 합니다. 반환 값 없음은 오류를 나타내는 데 예약되어 있습니다.

## <a name="remarks"></a>설명

**_mbsnbcat** 함수를 추가, 최대, 첫 번째 *개수* 바이트 *src* 에 *dest*합니다. 경우에 null 문자 바로 앞에 바이트 *dest* 의 초기 바이트가 선행 바이트를 인지 *src* 이 선행 바이트를 덮어씁니다. 그렇지 않은 경우의 초기 바이트가 *src* 의 종료 null 문자를 덮어씁니다 *dest*합니다. Null 바이트가 나타나는 경우 *src* 하기 전에 *개수* 바이트가 추가 되기 **_mbsnbcat** 의 모든 바이트를 추가 *src*, null이 나올 때까지 합니다. 경우 *개수* 의 길이 보다 크면 *src*, 길이의 *src* 대신 사용 됩니다 *개수*. 결과 문자열은 null 문자로 끝납니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 따른 영향을 받습니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. 합니다 **_mbsnbcat** 버전의 함수가 로캘 종속 동작에 현재 로캘을 사용 합니다 **_mbsnbcat_l** 버전은 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**보안 정보** null로 끝나는 문자열을 사용하세요. null로 끝나는 문자열은 대상 버퍼의 크기를 초과할 수 없습니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

하는 경우 *dest* 또는 *src* 됩니다 **NULL**를 함수에 설명 된 대로 잘못 된 매개 변수 오류를 발생 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 오류 처리 함수를 반환 합니다 **EINVAL** 집합과 **errno** 에 **EINVAL**합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_l**|**_strncat_l**|**_mbsnbcat_l**|**_wcsncat_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbcat**|\<mbstring.h>|
|**_mbsnbcat_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)<br/>
