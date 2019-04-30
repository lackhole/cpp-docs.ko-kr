---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
ms.date: 11/04/2016
apiname:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
ms.openlocfilehash: 7c3416397d8f43963d3be2ce9bc39707ea7865db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383466"
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l

인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
출력을 위한 스토리지 위치입니다.

*count*<br/>
작성할 최대 문자 수입니다.

*format*<br/>
형식 사양입니다.

*argptr*<br/>
인수 목록에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="return-value"></a>반환 값

합니다 **vsnprintf** 함수 제외 하 고 null 종결 문자 기록 된 문자 수를 반환 합니다. 로 지정 된 버퍼 크기가 *개수* 로 지정 된 출력을 포함할 만큼 충분히 크지 않으면 *형식* 하 고 *argptr*의 반환 값  **vsnprintf** 는 null 문자를 제외 하는 경우 작성 될 수 있는 문자 수가 *개수* 충분히 클 합니다. 반환 값 보다 크면 *개수* -1은 출력이 잘렸습니다. 반환 값 -1은 인코딩 오류가 발생했음을 나타냅니다.

둘 다 **_vsnprintf** 하 고 **_vsnwprintf** 작성할 문자 수가 보다 작거나 같은 경우 작성 된 문자 수를 반환 하는 함수 *개수*수가; 쓸 문자 보다 큼 *개수*, 이러한 함수는 출력이 잘렸음을 나타내는-1을 반환 합니다.

이러한 모든 함수에서 반환하는 값에는 작성 여부와 관계없이 종결 null이 포함되지 않습니다. 때 *개수* 가 0 이면 반환 되는 값은 함수가 작성할 없습니다 문자 수가 종결 null은 포함 됩니다. 이 결과를 사용하여 문자열과 해당 종결 null에 대해 충분한 버퍼 공간을 할당한 다음 함수를 다시 호출하여 버퍼를 채울 수 있습니다.

경우 *형식* 됩니다 **NULL**, 이거나 *버퍼* 은 **NULL** 및 *개수* 이러한 함수를 0과 같지 않은 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수가-1를 반환 하는 설정 **errno** 하 **EINVAL**합니다.

## <a name="remarks"></a>설명

이러한 함수는 각각 인수 목록에 대 한 포인터는 데이터의 형식을 지정 하 고 작성 *개수* 가리키는 메모리에 문자 *버퍼*합니다. 합니다 **vsnprintf** 출력을 자르 더라도 항상 함수 null 종결자를 씁니다. 사용 하는 경우 **_vsnprintf** 하 고 **_vsnwprintf**, 버퍼를 null로 종료 끝에 공간이 있는 경우에 (즉, 작성할 문자 수가 하는 경우 보다 작은 *count*).

> [!IMPORTANT]
> 특정 종류의 보안 위험을 방지 하려면 *형식* 사용자 정의 문자열이 아닙니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

> [!NOTE]
> 호출할 때 종료 null 위한 공간 인지 확인 **_vsnprintf**, **_vsnprintf_l**하십시오 **_vsnwprintf** 및 **_vsnwprintf_l**되어 있는지 확인 *개수* 가 버퍼 길이 보다 작아야 하 고 함수를 호출 하기 전에 null 버퍼를 초기화 합니다.
>
> 때문에 **vsnprintf** 항상 종료 null을 기록 합니다 *개수* 매개 변수 버퍼의 크기와 같을 수 있습니다.

Visual Studio 2015 및 Windows 10의 UCRT부터 **vsnprintf** 는 더 이상 동일 **_vsnprintf**합니다. 합니다 **vsnprintf** 함수는 C99 표준을 준수 **_vnsprintf** 이전 Visual Studio code 사용 하 여 이전 버전과 호환성을 위해 유지 됩니다.

포함 된 이러한 함수의 버전을 **_l** 접미사는 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf**|**_vsnprintf**|**_vsnprintf**|**_vsnwprintf**|
|**_vsntprintf_l**|**_vsnprintf_l**|**_vsnprintf_l**|**_vsnwprintf_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------------|-------------------------------|
|**vsnprintf**, **_vsnprintf**, **_vsnprintf_l**|\<stdio.h>|\<stdio.h> 또는  \<cstdio>|
|**_vsnwprintf**, **_vsnwprintf_l**|\<stdio.h> 또는 \<wchar.h>|\<stdio.h>, \<wchar.h>, \<cstdio> 또는 \<cwchar>|

**_vsnprintf**, **_vsnprintf_l**를 **_vsnwprintf** 하 고 **_vsnwprintf_l** 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_vsnwprintf.c
// compile by using: cl /W3 crt_vsnwprintf.c

// To turn off error C4996, define this symbol:
#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <wtypes.h>

#define BUFFCOUNT (10)

void FormatOutput(LPCWSTR formatstring, ...)
{
    int nSize = 0;
    wchar_t buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput(L"%ls %ls", L"Hi", L"there");
    FormatOutput(L"%ls %ls", L"Hi", L"there!");
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

좁은 문자열 매개 변수와 함께 vsnprintf를 대신 사용하면 동작이 변경됩니다. 합니다 *개수* 매개 변수 버퍼의 전체 크기 일 수 및 반환 값은 작성 되었을 경우 문자 수가 *개수* 가 충분히 큰:

## <a name="example"></a>예제

```C
// crt_vsnprintf.c
// compile by using: cl /W4 crt_vsnprintf.c
#include <stdio.h>
#include <stdarg.h> // for va_list, va_start
#include <string.h> // for memset

#define BUFFCOUNT (10)

void FormatOutput(char* formatstring, ...)
{
    int nSize = 0;
    char buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);
    printf("nSize: %d, buff: %s\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: 10, buff: Hi there!
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
[형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
