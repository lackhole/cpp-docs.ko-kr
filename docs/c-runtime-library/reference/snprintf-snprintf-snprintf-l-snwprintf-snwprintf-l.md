---
title: snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
ms.date: 11/04/2016
apiname:
- _snwprintf
- _snprintf
- _snprintf_l
- _snwprintf_l
- snprintf
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _snprintf
- snprintf_l
- snwprintf_l
- sntprintf
- snprintf
- _sntprintf
- _sntprintf_l
- sntprintf_l
- snwprintf
- _snprintf_l
- _snwprintf
- _snwprintf_l
helpviewer_keywords:
- snwprintf_l function
- sntprintf_l function
- snprintf_l function
- _snwprintf_l function
- _sntprintf_l function
- _snwprintf function
- _snprintf function
- _sntprintf function
- _snprintf_l function
- snwprintf function
- snprintf function
- sntprintf function
- formatted text [C++]
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
ms.openlocfilehash: 202f2f12de3955a2c9b0f785c3e89280d91a4a95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355721"
---
# <a name="snprintf-snprintf-snprintfl-snwprintf-snwprintfl"></a>snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l

문자열에 서식이 지정된 데이터를 씁니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int snprintf(
   char *buffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf(
   char *buffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
);
int _snwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument] ...
);
int _snwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int _snprintf(
   char (&buffer)[size],
   size_t count,
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
출력을 위한 스토리지 위치입니다.

*count*<br/>
저장할 최대 문자 수입니다.

*format*<br/>
형식 컨트롤 문자열입니다.

*argument*<br/>
선택적 인수입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)를 참조하세요.

## <a name="return-value"></a>반환 값

수 있도록 **len** 없습니다 종결 null을 포함 하 여 서식이 지정 된 데이터 문자열의 길이입니다. 둘 다 **len** 하 고 *개수* 바이트에 **snprintf** 및 **_snprintf**, 와이드 문자에 대 한 **_snwprintf**.

모든 함수에 대 한 경우 **len** < *개수*를 **len** 문자에 저장 됩니다 *버퍼*, null 종결자가 추가 및 **len** 반환 됩니다.

합니다 **snprintf** 함수는 출력을 자르 때 **len** 보다 크거나 같음 *개수*에 null 종결자를 배치 하 여 `buffer[count-1]`입니다. 값이 반환 됩니다 **len**, 경우 출력 될 수 있는 문자 수가 *개수* 가 충분히 큰 합니다. 합니다 **snprintf** 함수 인코딩 오류가 발생 하는 경우 음수 값을 반환 합니다.

모든 함수 이외의 **snprintf**이면 **len** = *개수*를 **len** 문자에 저장 된  *버퍼*에 없는 null 종결자가 추가 하 고 **len** 반환 됩니다. 하는 경우 **len** > *개수*를 *개수* 문자에 저장 됩니다 *버퍼*, 없는 null 종결자가 추가 된, 및 음수 값이 반환 됩니다.

경우 *버퍼* 가 null 포인터와 *개수* 가 0 이면 **len** 종결 null을 포함 하지 않습니다는 출력의 서식을 지정 하는 데 필요한 문자의 개수로 반환 됩니다. 동일한 성공적으로 호출 하려면 *인수* 하 고 *로캘* 매개 변수를 하나 이상 보유 되는 버퍼를 할당 **len** + 1 자로.

하는 경우 *버퍼* 가 null 포인터 및 *개수* 값은 0 이거나 *형식* 가 null 포인터인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수가-1를 반환 하는 설정 **errno** 하 **EINVAL**합니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **snprintf** 함수 및 **_snprintf** 형식을 지정 하 고 저장소 제품군 *개수* 자 미만의 *버퍼*합니다. 합니다 **snprintf** 함수는 항상 필요한 경우 출력 자르기 종결 null 문자를 저장 합니다. 합니다 **_snprintf** 서식이 지정 된 문자열 길이 엄격 하 게 하는 경우만 함수 패밀리는 종료 null 문자를 추가 미만 *개수* 문자입니다. 각 *인수* (있는 경우) 변환 되 고 해당 형식 사양에 따라 출력이 *형식*합니다. 형식은 일반 문자로 구성 되어 있으며 동일한 폼 및 함수는 *형식* 에 대 한 인수가 [printf](printf-printf-l-wprintf-wprintf-l.md)합니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요. 때문에 합니다 **_snprintf** 함수는 null 종료를 보장 하지 않습니다-특히 반환 값이 *개수*-는 이러한 뒤에 null 종결자를 추가 하는 코드가 있는지 확인 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

Visual Studio 2015 및 Windows 10의 UCRT부터 **snprintf** 는 더 이상 동일 **_snprintf**합니다. 합니다 **snprintf** 함수 동작은 이제 C99 표준을 준수 합니다.

**_snwprintf** 의 와이드 문자 버전이 **_snprintf**;에 대 한 포인터 인수 **_snwprintf** 는 와이드 문자 문자열입니다. 인코딩 오류의 탐지 **_snwprintf** 에 다를 수 있습니다 **_snprintf**합니다. **_snwprintf**, 마찬가지로 **swprintf**에 출력 유형의 대상 대신 문자열을 씁니다 **파일**합니다.

접미사가 있는 이러한 함수 버전을 **_l** 접미사는 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

C++에서 이러한 함수는 보다 최신의 안전한 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sntprintf**|**_snprintf**|**_snprintf**|**_snwprintf**|
|**_sntprintf_l**|**_snprintf_l**|**_snprintf_l**|**_snwprintf_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**snprintf**, **_snprintf**,  **_snprintf_l**|\<stdio.h>|
|**_snwprintf**, **_snwprintf_l**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_snprintf.c
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

#if !defined(__cplusplus)
typedef int bool;
const bool true = 1;
const bool false = 0;
#endif

#define FAIL 0 // change to 1 and see what happens

int main(void)
{
   char buffer[200];
   const static char s[] = "computer"
#if FAIL
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
"computercomputercomputercomputercomputercomputercomputercomputer"
#endif
   ;
   const char c = 'l';
   const int i = 35;
#if FAIL
   const double fp = 1e300; // doesn't fit in the buffer
#else
   const double fp = 1.7320534;
#endif
   /* !subtract one to prevent "squeezing out" the terminal null! */
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;
   int bufferUsed = 0;
   int bufferLeft = bufferSize - bufferUsed;
   bool bSuccess = true;
   buffer[0] = 0;

   /* Format and print various data: */

   if (bufferLeft > 0)
   {
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],
      bufferLeft, "   String: %s\n", s ); // C4996
      // Note: _snprintf is deprecated; consider _snprintf_s instead
      if (bSuccess = (perElementBufferUsed >= 0))
      {
         bufferUsed += perElementBufferUsed;
         bufferLeft -= perElementBufferUsed;
         if (bufferLeft > 0)
         {
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],
            bufferLeft, "   Character: %c\n", c ); // C4996
            if (bSuccess = (perElementBufferUsed >= 0))
            {
               bufferUsed += perElementBufferUsed;
               bufferLeft -= perElementBufferUsed;
               if (bufferLeft > 0)
               {
                  int perElementBufferUsed = _snprintf(&buffer
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996
                  if (bSuccess = (perElementBufferUsed >= 0))
                  {
                     bufferUsed += perElementBufferUsed;
                     bufferLeft -= perElementBufferUsed;
                     if (bufferLeft > 0)
                     {
                        int perElementBufferUsed = _snprintf(&buffer
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996
                        if (bSuccess = (perElementBufferUsed >= 0))
                        {
                           bufferUsed += perElementBufferUsed;
                        }
                     }
                  }
               }
            }
         }
      }
   }

   if (!bSuccess)
   {
      printf("%s\n", "failure");
   }
   else
   {
      /* !store null because _snprintf doesn't necessarily (if the string
       * fits without the terminal null, but not with it)!
       * bufferUsed might be as large as bufferSize, which normally is
       * like going one element beyond a buffer, but in this case
       * subtracted one from bufferSize, so we're ok.
       */
      buffer[bufferUsed] = 0;
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );
   }
   return EXIT_SUCCESS;
}
```

```Output
Output:
   String: computer
   Character: l
   Integer: 35
   Real: 1.732053

character count = 69
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
