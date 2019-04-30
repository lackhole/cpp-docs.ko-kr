---
title: _mktemp_s, _wmktemp_s
ms.date: 11/04/2016
apiname:
- _mktemp_s
- _wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
ms.openlocfilehash: fef10f2cfbcc0332741d560a41a782b70ed14798
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156540"
---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s

고유한 파일 이름을 만듭니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_mktemp, _wmktemp](mktemp-wmktemp.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _mktemp_s(
   char *nameTemplate,
   size_t sizeInChars
);
errno_t _wmktemp_s(
   wchar_t *nameTemplate,
   size_t sizeInChars
);
template <size_t size>
errno_t _mktemp_s(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
errno_t _wmktemp_s(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*nameTemplate*<br/>
파일 이름 패턴입니다.

*sizeInChars*<br/>
단일 바이트 문자를 버퍼의 크기 **_mktemp_s**와이드의 문자 **_wmktemp_s**, null 종결자를 포함 합니다.

## <a name="return-value"></a>반환 값

이 두 함수는 모두 정상적으로 실행되면 0을 반환하고 실행 시 오류가 발생하면 오류 코드를 반환합니다.

### <a name="error-conditions"></a>오류 조건

|*nameTemplate*|*sizeInChars*|반환 값|새 값 *nameTemplate*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|any|**EINVAL**|**NULL**|
|형식이 잘못 되었습니다 (설명 부분 참조 올바른 형식에 대 한 섹션)|any|**EINVAL**|빈 문자열|
|any|<= X의 수|**EINVAL**|빈 문자열|

위의 오류 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수를 반환 하 고 **EINVAL**합니다.

## <a name="remarks"></a>설명

합니다 **_mktemp_s** 함수를 수정 하 여 고유한 파일 이름을 만듭니다 합니다 *nameTemplate* 인수를 있도록 호출 후는 *nameTemplate* 문자열을 가리키는 포인터 새 파일 이름을 포함 합니다. **_mktemp_s** 런타임 시스템에서 현재 사용 중인 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 하며 필요에 따라 멀티 바이트 문자열 인수를 자동으로 처리 합니다. **_wmktemp_s** 의 와이드 문자 버전이 **_mktemp_s**;의 인수 **_wmktemp_s** 는 와이드 문자 문자열입니다. **_wmktemp_s** 하 고 **_mktemp_s** 동일 하 게 한다는 점을 제외 하 고, 그렇지 동작 **_wmktemp_s** 멀티 바이트 문자열을 처리 하지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

합니다 *nameTemplate* 인수의 형식은 **baseXXXXXX**여기서 *기본* 제공 하는 새 파일 이름 부분은 속하며 각 X는에서 제공 하는 문자열에 대 한 자리 표시자 **_mktemp_s**합니다. 각 자리 표시자 문자 *nameTemplate* 는 대문자 X 여야 **_mktemp_s** 유지 *기본* 첫 번째 후행 X를 영문자로 바꿉니다. **_mktemp_s** 대체 다음 후행 X 5 자리 숫자 값을 사용 하 여이 값은 프로세스 또는 다중 스레드 프로그램을 호출 하는 스레드에서 호출을 식별 하는 고유 번호입니다.

성공한 각 호출에 **_mktemp_s** 수정 *nameTemplate*합니다. 각 후속 호출에서 동일한 프로세스 또는 스레드의 동일한 *nameTemplate* 인수 **_mktemp_s** 반환한 이름과 일치 하는 파일 이름에 대 한 검사 **_mktemp_s** 이전 호출 합니다. 지정 된 이름에 대 한 파일이 없는 경우 **_mktemp_s** 해당 이름을 반환 합니다. 이전에 반환 된 모든 이름에 대 한 파일이 존재 하는 경우 **_mktemp_s** 다음 사용 가능한 소문자를 'a' ~ 'z'까지에서 순서 대로 사용 하 여 이전에 반환 된 이름에서 사용한 영문자를 대체 하 여 새 이름을 만듭니다. 예를 들어 있으면 *기본* 됩니다.

> **fn**

및에서 제공 하는 5 자리 숫자 값 **_mktemp_s** 이 12345 인 경우 첫 번째 반환 되는:

> **fna12345**

이 이름이 FNA12345 파일을 만드는 데 사용 됩니다 하 고이 파일이 있는지, 동일한 프로세스 또는 스레드가 동일한 호출에서 반환 된 다음 이름이 *기본* 에 대 한 *nameTemplate* 됩니다.

> **fnb12345**

FNA12345가 존재하지 않는 경우 반환된 다음 이름은 다시 아래와 같습니다.

> **fna12345**

**_mktemp_s** 의 지정된 된 조합에 대 한 고유한 파일 이름 26 개까지 만들 수 있습니다 *기본* 하 고 *nameTemplate* 값입니다. 따라서 FNZ12345는 마지막 고유한 파일 이름을 **_mktemp_s** 에 대해 만들 수는 *기본* 및 *nameTemplate* 이 예제에서 사용 되는 값입니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_mktemp_s.cpp
/* The program uses _mktemp to create
* five unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>

char *fnTemplate = "fnXXXXXX";
char names[5][9];

int main()
{
   int i, err, sizeInChars;
   FILE *fp;

   for( i = 0; i < 5; i++ )
   {
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );
      /* Get the size of the string and add one for the null terminator.*/
      sizeInChars = strnlen(names[i], 9) + 1;
      /* Attempt to find a unique filename: */
      err = _mktemp_s( names[i], sizeInChars );
      if( err != 0 )
         printf( "Problem creating the template" );
      else
      {
         if( fopen_s( &fp, names[i], "w" ) == 0 )
            printf( "Unique filename is %s\n", names[i] );
         else
            printf( "Cannot open %s\n", names[i] );
         fclose( fp );
      }
   }

   return 0;
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
