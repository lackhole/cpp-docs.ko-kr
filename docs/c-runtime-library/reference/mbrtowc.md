---
title: mbrtowc
ms.date: 11/04/2016
apiname:
- mbrtowc
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: bd719e7b336333f6e06a1db9b1e34784575a1602
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331534"
---
# <a name="mbrtowc"></a>mbrtowc

현재 로캘의 멀티바이트 문자를 해당하는 와이드 문자로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다.

## <a name="syntax"></a>구문

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>매개 변수

*wchar*<br/>
변환 된 와이드 문자 문자열을 받을 와이드 문자의 주소입니다 (형식 **wchar_t**). 반환 와이드 문자가 필요하지 않으면 이 값은 null 포인터일 수 있습니다.

*mbchar*<br/>
바이트 시퀀스(멀티바이트 문자)의 주소입니다.

*count*<br/>
검사할 바이트 수입니다.

*mbstate*<br/>
변환 상태 개체에 대한 포인터입니다. 이 값이 null 포인터이면 함수는 정적 내부 변환 상태 개체를 사용합니다. 때문에 내부 **mbstate_t** 개체는 스레드로부터 안전 하지 않습니다, 전달 하는 항상 고유한 것이 좋습니다 *mbstate* 인수입니다.

## <a name="return-value"></a>반환 값

다음 값 중 하나입니다.

0 다음 *개수* 개 이하의 바이트가 null 와이드 문자에 저장 되어 있는 나타내는 멀티 바이트 문자를 완성 *wchar*이면 *wchar* null 포인터가 아닙니다.

1 ~ *개수*(포함) 다음 *개수* 개 이하의 바이트가 올바른 멀티 바이트 문자를 완성 합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다. 해당 하는 와이드 문자에 저장 됩니다 *wchar*이면 *wchar* null 포인터가 아닙니다.

(size_t) (-1) 인코딩 오류가 발생 했습니다. 다음 *개수* 또는 개 이하의 바이트가 완전 하며 올바른 멀티 바이트 문자에 기여 하지 않습니다. 이 예에서 **errno** EILSEQ로 설정 되며에서 변환 이동 상태가 설정 됩니다 *mbstate* 지정 되지 않았습니다.

(size_t) -(2) 다음 *개수* 바이트 불완전 하지만 올바를 멀티 바이트 문자를 및 모든 참가 *개수* 처리 된 바이트입니다. 값에 저장 됩니다 *wchar*, 되지만 *mbstate* 함수를 다시 시작 하도록 업데이트 됩니다.

## <a name="remarks"></a>설명

경우 *mbchar* 가 null 포인터인 경우 함수 호출에 해당 됩니다.

`mbrtowc(NULL, "", 1, &mbstate)`

인수의 값이 예제의 *wchar* 하 고 *개수* 무시 됩니다.

하는 경우 *mbchar* 가 null 포인터가 아닌 함수 검사 *개수* 바이트 *mbchar* 다음을 완료 하는 데 필요한 바이트 수를 결정 하려면 멀티 바이트 문자입니다. 다음 문자가 올바르면 해당 멀티 바이트 문자에 저장 됩니다 *wchar* 가 null 포인터가 아닌 경우. 문자를 해당 와이드 null 문자를의 결과 상태 *mbstate* 초기 변환 상태입니다.

합니다 **mbrtowc** 함수에서 다른 [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) 해당 다시 시작할 수 있다는입니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, 응용 프로그램을 사용할지 **wcsrlen** 대신 **wcslen** 경우에 대 한 후속 호출 **wcsrtombs** 를 사용 하는 대신 **wcstombs**.

## <a name="example"></a>예제

멀티바이트 문자를 해당하는 와이드 문자로 변환합니다.

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
