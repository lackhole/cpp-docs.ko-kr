---
title: tmpnam_s, _wtmpnam_s
ms.date: 11/04/2016
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
ms.openlocfilehash: 9bf994d16362ef461d8d25d72466721ba9a5890f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155539"
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s

임시 파일을 만드는 데 사용할 수 있는 이름을 생성합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [tmpnam 및 _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t tmpnam_s(
   char * str,
   size_t sizeInChars
);
errno_t _wtmpnam_s(
   wchar_t *str,
   size_t sizeInChars
);
template <size_t size>
errno_t tmpnam_s(
   char (&str)[size]
); // C++ only
template <size_t size>
errno_t _wtmpnam_s(
   wchar_t (&str)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*str*<br/>
생성된 이름이 저장되는 포인터입니다.

*sizeInChars*<br/>
버퍼의 크기(문자)입니다.

## <a name="return-value"></a>반환 값

이 두 함수는 정상적으로 실행되면 0을 반환하고 오류 시에는 오류 번호를 반환합니다.

### <a name="error-conditions"></a>오류 조건

|||||
|-|-|-|-|
|*str*|*sizeInChars*|**반환 값**|**내용의***str*|
|**NULL**|any|**EINVAL**|수정 안 됨|
|되지 **NULL** (유효한 메모리를 가리킴)|너무 짧음|**ERANGE**|수정 안 됨|

하는 경우 *str* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

## <a name="remarks"></a>설명

이러한 각 함수는 현재 없는 파일의 이름을 반환합니다. **tmpnam_s** 반환한 지정 된 Windows 임시 디렉터리에 고유 이름을 반환 [GetTempPathW](/windows/desktop/api/fileapi/nf-fileapi-gettemppathw)합니다. \fname21과 같이 파일 이름 앞에 백슬래시가 붙고 경로 정보는 없는 경우 현재 작업 디렉터리에 대해 해당 이름이 유효함을 나타냅니다.

에 대 한 **tmpnam_s**,이 생성 된 파일 이름에 저장할 수 있습니다 *str*합니다. 반환 된 문자열의 최대 길이 **tmpnam_s** 됩니다 **L_tmpnam_s**STDIO에 정의 된 합니다. 8. 경우 *str* 됩니다 **NULL**, 한 다음 **tmpnam_s** 결과 내부 정적 버퍼에 유지 합니다. 따라서 모든 후속 호출에서는 이 값을 제거합니다. 생성 된 이름을 **tmpnam_s** 으로 구성 됩니다 프로그램에서 생성 된 파일 이름의 첫 번째 호출 후 **tmpnam_s**, 순차적 숫자의 파일 확장명 (이름은.1-.1vvvvvu 경우 **TMP _MAX_S** STDIO에서. H 됩니다 **INT_MAX**).

**tmpnam_s** 멀티 바이트 문자열 인수를 적절 하 게 처리 OEM 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 운영 체제에서 자동으로 부여 합니다. **_wtmpnam_s** 의 와이드 문자 버전이 **tmpnam_s**;의 인수와 반환 값 **_wtmpnam_s** 는 와이드 문자 문자열입니다. **_wtmpnam_s** 하 고 **tmpnam_s** 점을 제외 하면 동일 하 게 작동 **_wtmpnam_s** 멀티 바이트 문자열을 처리 하지 않습니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_tmpnam_s.c
// This program uses tmpnam_s to create a unique filename in the
// current working directory.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char name1[L_tmpnam_s];
   errno_t err;
   int i;

   for (i = 0; i < 15; i++)
   {
      err = tmpnam_s( name1, L_tmpnam_s );
      if (err)
      {
         printf("Error occurred creating unique filename.\n");
         exit(1);
      }
      else
      {
         printf( "%s is safe to use as a temporary file.\n", name1 );
      }
   }
}
```

```Output
C:\Users\LocalUser\AppData\Local\Temp\u19q8.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.1 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.2 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.3 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.4 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.5 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.6 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.7 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.8 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.9 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.a is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.b is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.c is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.d is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.e is safe to use as a temporary file.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
