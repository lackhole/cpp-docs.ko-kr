---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 11/04/2016
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
ms.openlocfilehash: 059d0781e465f6491f27fd634bbc4479104bc12f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331300"
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l

비교 **n** 두 멀티 바이트 문자열 및 대/소문자를 무시 합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>매개 변수

*string1*, *string2*<br/>
비교할 Null 종료 문자열입니다.

*count*<br/>
비교할 바이트 수입니다.

## <a name="return-value"></a>반환 값

반환 값은 부분 문자열 간의 관계를 나타냅니다.

|반환 값|설명|
|------------------|-----------------|
|< 0|*string1* 부분 문자열 보다 작거나 *string2* 부분 문자열입니다.|
|0|*string1* substring 동일 *string2* 부분 문자열입니다.|
|> 0|*string1* 부분 문자열 보다 큰 *string2* 부분 문자열입니다.|

오류 발생 시 **_mbsnbicmp** 반환 **_NLSCMPERROR**, String.h 및 Mbstring.h에 정의 되어 있습니다.

## <a name="remarks"></a>설명

합니다 **_mbsnbicmp** 최대 첫 번째 서 수 비교를 수행 하는 함수 *개수* 바이트 *string1* 및 *string2*합니다. 각 문자를 소문자로 변환 하 여 비교를 수행 [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) 의 대/소문자 구분 버전이 **_mbsnbicmp**합니다. 하기 전에 두 문자열 중 하나에서 종결 null 문자에 도달 하면 비교가 종료 *개수* 자를 비교 합니다. 문자열이 같으면 null 종결 문자에 도달할 때 하기 전에 두 문자열 중 하나에 *개수* 자를 비교, 더 짧은 문자열이 작습니다.

**_mbsnbicmp** 비슷합니다 [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)까지의 문자열을 비교 하는 점을 제외 하 고 *개수* 문자가 아닌 바이트입니다.

ASCII 테이블의 'Z'와 'a' 사이에 있는 문자('[', '\\', ']', '^', '_' 및 '\`')를 포함하는 두 문자열은 대소문자에 따라 서로 다른 방식으로 비교됩니다. "ABCDE" 문자열을 두는 예를 들어, 및 "ABCD ^"는 한 가지 방법은 비교는 소문자 비교 ("abcde" > "abcd ^") 및 다른 방법으로 ("ABCDE" < "ABCD ^") 대문자 인 경우.

**_mbsnbicmp** 에 따라 멀티 바이트 문자 시퀀스를 인식 합니다 [멀티 바이트 코드 페이지](../../c-runtime-library/code-pages.md) 에서 현재 사용 합니다. 현재 로캘 설정은 적용되지 않습니다.

경우 *string1* 하거나 *string2* 가 null 포인터 **_mbsnbicmp** 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개변수유효성검사](../../c-runtime-library/parameter-validation.md). 실행을 계속 하도록 허용 된 경우 함수 반환 **_NLSCMPERROR** 설정 **errno** 하 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
