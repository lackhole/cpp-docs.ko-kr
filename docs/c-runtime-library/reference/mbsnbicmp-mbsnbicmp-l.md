---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 11/04/2016
api_name:
- _mbsnbicmp_l
- _mbsnbicmp
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 19ffa4c47f0144ba136607fe5cef09e9bd65374f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952185"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp, _mbsnbicmp_l

두 멀티 바이트 문자열의 **n** 바이트를 비교 하 고 대/소문자를 무시 합니다.

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
|< 0|문자열 1 부분 문자열 *에서 문자열이* *아닌 부분 문자열* 보다 작음|
|0|문자열 *1 부분 문자열이 문자열이 아닌* *부분 문자열과 같습니다* .|
|> 0|*문자열이 아닌 부분* 문자열이 *문자열 문자열의 하위 문자열 보다 큽니다* .|

오류가 발생 하는 경우 **_mbsnbicmp** 는 _NLSCMPERROR 및 mbstrh에 정의 된를 반환 합니다.

## <a name="remarks"></a>설명

**_Mbsnbicmp** 함수는 *문자열* 1과 *문자열 2*의 최대 *개수* 바이트 수에 대 한 서 수 비교를 수행 합니다. 각 문자를 소문자로 변환 하 여 비교를 수행 합니다. [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) 은 대/소문자를 구분 하는 **_mbsnbicmp**버전입니다. *Count* 문자를 비교 하기 전에 두 문자열 중 하나에서 종결 null 문자에 도달 하면 비교가 종료 됩니다. *Count* 문자를 비교 하기 전에 문자열 중 하나에서 종결 null 문자에 도달할 때 문자열이 같으면 문자열이 낮을수록 짧습니다.

**_mbsnbicmp** 는 문자열을 문자 대신 바이트 *수* 까지 비교 한다는 점을 제외 하 고는 [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)과 유사 합니다.

ASCII 테이블의 'Z'와 'a' 사이에 있는 문자('[', '\\', ']', '^', '_' 및 '\`')를 포함하는 두 문자열은 대소문자에 따라 서로 다른 방식으로 비교됩니다. 예를 들어 두 문자열 "ABCDE...Z" 및 "ABCD ^"는 비교가 소문자 ("abcde...z" > "abcd ^")이 고 다른 방법 ("ABCDE...Z" < "ABCD ^")이 대문자 인 경우 한 가지 방법을 비교 합니다.

**_mbsnbicmp** 는 현재 사용 중인 [멀티 바이트 코드 페이지](../../c-runtime-library/code-pages.md) 에 따라 멀티 바이트 문자 시퀀스를 인식 합니다. 현재 로캘 설정은 적용되지 않습니다.

*String1* 또는 *문자열* 하나가 null 포인터인 경우 **_Mbsnbicmp** 는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **_NLSCMPERROR** 를 반환 하 고 **errno** 를 **EINVAL**로 설정 합니다.

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
