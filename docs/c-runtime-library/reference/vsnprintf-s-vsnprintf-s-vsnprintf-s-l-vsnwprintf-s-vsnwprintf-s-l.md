---
title: vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
ms.date: 11/04/2016
apiname:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
helpviewer_keywords:
- vsnwprintf_s function
- _vsntprintf_s function
- _vsntprintf_s_l function
- vsntprintf_s function
- vsnwprintf_s_l function
- vsnprintf_s_l function
- vsntprintf_s_l function
- _vsnwprintf_s_l function
- _vsnprintf_s function
- vsnprintf_s function
- _vsnprintf_s_l function
- _vsnwprintf_s function
- formatted text [C++]
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
ms.openlocfilehash: 255c3b760dec1495a4f9a82915878a5504844f24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188728"
---
# <a name="vsnprintfs-vsnprintfs-vsnprintfsl-vsnwprintfs-vsnwprintfsl"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l

인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
int vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int _vsnprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
출력을 위한 스토리지 위치입니다.

*sizeOfBuffer*<br/>
크기를 *버퍼* 출력의 경우 문자 수입니다.

*count*<br/>
작성할 최대 문자 수(종결 null은 포함되지 않음) 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)입니다.

*format*<br/>
형식 사양입니다.

*argptr*<br/>
인수 목록에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.

## <a name="return-value"></a>반환 값

**vsnprintf_s**하십시오 **_vsnprintf_s** 하 고 **_vsnwprintf_s** 출력 오류가 발생 한 경우 이며, 종결 null 또는 음수 값을 포함 하지 않고 작성 된 문자 수를 반환 합니다. **vsnprintf_s** 동일 **_vsnprintf_s**합니다. **vsnprintf_s** ANSI 표준 준수를 위해 포함 되었습니다. **_vnsprintf** 이전 버전과 호환성을 위해 유지 됩니다.

초과 하면 데이터와 종결 null을 저장 하는 데 필요한 저장소가 *sizeOfBuffer*에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)하지 않는 한, *개수*  됩니다 [_TRUNCATE](../../c-runtime-library/truncate.md),이 경우 문자열을 최대한으로에 맞는 *버퍼* 기록 됩니다 및-1이 반환 합니다. 잘못 된 매개 변수 처리기를 후 실행 계속 되 면 이러한 함수 설정 *버퍼* 빈 문자열로 설정 **errno** 에 **ERANGE**,-1을 반환 합니다.

경우 *버퍼* 또는 *형식* 은 **NULL** 포인터 이거나 *개수* 보다 작거나를 0으로 잘못 된 매개 변수 처리기가 호출 됩니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 고-1을 반환 합니다.

### <a name="error-conditions"></a>오류 조건

|**조건**|반환|**errno**|
|-----------------|------------|-------------|
|*버퍼* 는 **NULL**|-1|**EINVAL**|
|*형식* 는 **NULL**|-1|**EINVAL**|
|*count* <= 0|-1|**EINVAL**|
|*sizeOfBuffer* 너무 작아서 (및 *개수* ! = **_TRUNCATE**)|-1 (및 *버퍼* 빈 문자열로 설정)|**ERANGE**|

## <a name="remarks"></a>설명

이러한 함수는 각각 인수 목록에 대 한 포인터 형식을 지정 하 고 작성 *개수* 가리키는 메모리에 지정된 된 데이터의 문자 *버퍼* 종결 null을 추가 합니다.

경우 *개수* 됩니다 [_TRUNCATE](../../c-runtime-library/truncate.md), 이러한 함수 들어갈 수 있을 만큼 문자열을 최대한으로 작성 한 다음 *버퍼* 종료 null에 대 한 공간을 남겨 두고. 는 전체 문자열 (null 종결) 맞는지 *버퍼*, 그런 다음 이러한 함수 (종결 null 제외)에 기록 된 문자 수를 반환 합니다. 그렇지 않으면 이러한 함수 반환 잘림이 나타낼 때-1 오류가 발생 했습니다.

포함 된 이러한 함수의 버전을 **_l** 접미사는 현재 스레드 로캘 대신 전달 된 로캘 매개 변수를 사용 한다는 점을 제외 하면 동일 합니다.

> [!IMPORTANT]
> *format*이 사용자 정의 문자열이 아닌지 확인하세요. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

> [!NOTE]
> 종료 null에 대 한 공간이 있도록 해야 *개수* 버퍼 길이 사용 하 여 보다 엄격 하 게 작으면 **_TRUNCATE**합니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio.h> 및 \<stdarg.h>|\<varargs.h>*|
|**_vsnprintf_s**, **_vsnprintf_s_l**|\<stdio.h> 및 \<stdarg.h>|\<varargs.h>*|
|**_vsnwprintf_s**, **_vsnwprintf_s_l**|\<stdio.h> 또는 \<wchar.h> 및 \<stdarg.h>|\<varargs.h>*|

\* UNIX V 호환성을 위해 필요합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_vsnprintf_s.cpp
#include <stdio.h>
#include <wtypes.h>

void FormatOutput(LPCSTR formatstring, ...)
{
   int nSize = 0;
   char buff[10];
   memset(buff, 0, sizeof(buff));
   va_list args;
   va_start(args, formatstring);
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);
   printf("nSize: %d, buff: %s\n", nSize, buff);
   va_end(args);
}

int main() {
   FormatOutput("%s %s", "Hi", "there");
   FormatOutput("%s %s", "Hi", "there!");
   FormatOutput("%s %s", "Hi", "there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 함수](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
