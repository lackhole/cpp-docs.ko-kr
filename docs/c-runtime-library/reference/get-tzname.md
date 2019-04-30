---
title: _get_tzname
ms.date: 10/22/2018
apiname:
- _get_tzname
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: c173832efb866eed133a908b5f2b72266fd3798a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332042"
---
# <a name="gettzname"></a>_get_tzname

표준 시간대 이름 또는 일광 표준 시간대 이름(DST)의 문자열 표현을 검색합니다.

## <a name="syntax"></a>구문

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
문자열 길이 *표준 시간대 이름* null 종결자를 포함 합니다.

*timeZoneName*<br/>
에 따라 표준 시간대 이름 또는 일광 표준 시간대 이름 (DST)의 표현에 대 한 문자에 대 한 문자열의 주소 *인덱스*합니다.

*sizeInBytes*<br/>
크기를 *표준 시간대 이름* 바이트 문자열입니다.

*index*<br/>
검색할 두 표준 시간대 이름 중 하나의 인덱스입니다.

|*index*|내용을 *표준 시간대 이름*|*표준 시간대 이름* 기본값|
|-|-|-|
|0|표준 시간대 이름|"PST"|
|1|일광 표준 시간대 이름|"PDT"|
|> 1 또는 < 0|**errno** 로 **EINVAL**|수정 안 됨|

런타임에 값을 명시적으로 변경하는 경우가 아니면 기본값은 각각 "PST" 및 "PDT"입니다.

## <a name="return-value"></a>반환 값

성공 하면 0이 고, 그렇지는 **errno** 값을 입력 합니다.

이면 *표준 시간대 이름* 됩니다 **NULL**, 또는 *sizeInBytes* 0 또는 0 (하지만 둘 다가 아닌) 보다 작으면는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EINVAL**합니다.

### <a name="error-conditions"></a>오류 조건

|*pReturnValue*|*timeZoneName*|*sizeInBytes*|*index*|반환 값|내용을 *표준 시간대 이름*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ 이름의 크기|**NULL**|0|0 또는 1|0|수정 안 됨|
|TZ 이름의 크기|any|> 0|0 또는 1|0|TZ 이름|
|수정 안 됨|**NULL**|> 0|any|**EINVAL**|수정 안 됨|
|수정 안 됨|any|0|any|**EINVAL**|수정 안 됨|
|수정 안 됨|any|> 0|> 1|**EINVAL**|수정 안 됨|

## <a name="remarks"></a>설명

합니다 **_get_tzname** 함수는 문자열 표현을 현재 표준 시간대 이름 또는 일광 표준 시간대 이름 (DST)의 주소로 검색 *표준 시간대 이름* 따라는 인덱스 값에서 문자열의 크기와 함께 *pReturnValue*합니다. 하는 경우 *표준 시간대 이름* 됩니다 **NULL** 하 고 *sizeInBytes* 0으로 지정된 된 표준 시간대를 포함 하는 데 필요한 문자열의 크기 이며 에바이트에서종결null이반환*pReturnValue*합니다. 인덱스 값을 표준 시간대에 대해 0 또는 일광 표준 시간대는 1 이어야 합니다. 다른 모든 값 *인덱스* 가 지정 되지 않은 결과입니다.

## <a name="example"></a>예제

이 샘플에서는 호출 **_get_tzname** 필요한 버퍼 크기를 현재 일광 표준 시간대 이름에 표시할 호출 해당 크기의 버퍼를 할당 **_get_tzname** 다시 이름을 로드 하는 를 버퍼링 하 고 콘솔에 출력 합니다.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>출력

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
