---
title: strftime, wcsftime, _strftime_l, _wcsftime_l
ms.date: 03/22/2018
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
ms.openlocfilehash: 932a7827ef61a5e111f86f8bc44291827843b76e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353848"
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

시간 문자열 서식을 지정합니다.

## <a name="syntax"></a>구문

```C
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strDest*<br/>
출력 문자열입니다.

*maxsize*<br/>
크기를 *strDest* 문자 단위로 측정 한 버퍼 (**char** 하거나 **wchar_t**).

*format*<br/>
형식 컨트롤 문자열입니다.

*timeptr*<br/>
**tm** 데이터 구조입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**strftime** 에 배치 되는 문자 수를 반환 *strDest* 하 고 **wcsftime** 해당 와이드 문자 수를 반환 합니다.

종료 null을 포함 하는 문자의 총 수는 경우 둘 *maxsize*모두 **strftime** 하 고 **wcsftime** 0을 반환 하며 내용의  *strDest* 확정적이 지 않습니다.

문자 수가 *strDest* 는 리터럴 문자 수와 같습니다 *형식* 에 추가 될 수 있는 모든 문자 뿐만 아니라 *형식* 서식 코드를 통해. 문자열의 종료 null은 반환 값 계산에 포함되지 않습니다.

## <a name="remarks"></a>설명

합니다 **strftime** 및 **wcsftime** 함수 형식 합니다 **tm** 시간 값에 *timeptr* 에 제공 된 따라  *형식* 인수와 저장소 버퍼의 결과 *strDest*합니다. 최소한 *maxsize* 문자열에 문자가 배치 됩니다. 필드에 대 한 합니다 *timeptr* 구조체를 참조 하십시오 [asctime](asctime-wasctime.md)합니다. **wcsftime** 의 와이드 문자 동일 **strftime**; 해당 문자열 포인터 인수는 와이드 문자 문자열을 가리킵니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *strDest*를 *형식*, 또는 *timeptr* 가 null 포인터인 경우 또는 경우에는 **tm** 데이터 구조에서 다루는 *timeptr* (예를 들어 시간 또는 날짜 범위를 벗어난 값 포함), 유효 하지 또는 경우에는 *형식* 문자열 잘못 된 서식 코드가 들어 에설명된대로잘못된매개변수처리기가호출[매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행 함수는 0 반환 하 고 집합을 계속 하도록 허용 된 경우 **errno** 하 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

합니다 *형식* 인수에는 하나 이상의 코드에서 같이 구성 됩니다 **printf**, 형식 지정 코드를 백분율 기호 뒤 (**%**). 시작 하지 않는 문자 **%** 변경 되지 않고 복사 됩니다 *strDest*합니다. 합니다 **LC_TIME** 의 출력 서식 지정 하는 현재 로캘 범주에 영향을 줍니다 **strftime**합니다. (대 한 자세한 내용은 **LC_TIME**를 참조 하십시오 [setlocale](setlocale-wsetlocale.md).) 합니다 **strftime** 하 고 **wcsftime** 함수를 사용 하 여 현재 설정 로캘. 합니다 **_strftime_l** 하 고 **_wcsftime_l** 이러한 함수의 버전은 로캘을 매개 변수로 하며 현재 설정 대신 사용 한다는 동일 로캘. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

합니다 **strftime** 함수는 이러한 코드 서식 지원:

|||
|-|-|
|코드|바꾸기 문자열|
|**%a**|로캘에서 간략화 된 요일 이름|
|**%A**|로캘의 전체 요일 이름|
|**%b**|로캘에서 약식된 월 이름|
|**%B**|로캘의 전체 월 이름|
|**%c**|로캘에 적합한 날짜 및 시간 표현|
|**%C**|100으로 나눈 및 진수 (00−99)는 정수로 잘립니다 연도|
|**%d**|10 진수 숫자 (01-31)의 월간 일자|
|**%D**|같음 **%m/%d/%y**|
|**%e**|공백을 사용 하 여 단일 숫자 앞에 있는 10 진수 숫자 (1-31)의 월간 일자|
|**%F**|같음 **%Y-%m-%d**|
|**%g**|10 진수 숫자로 ISO 8601 주 기반 년의 마지막 두 자리 (00-99)|
|**%G**|10 진수는 ISO 8601 주 기반 연도|
|**%h**|월 약어 (같음 **%b**)|
|**%H**|24 시간 형식의 시간 (00-23)|
|**%I**|12 시간 형식의 시간 (01-12)|
|**%j**|10 진수 (001-366)으로 연간 일자|
|**%m**|(01-12) 10 진수 숫자로 월|
|**%M**|10 진수 분 (00-59)|
|**%n**|줄 바꿈 문자 (**\n**)|
|**%p**|로캘의 오전/오후 12시간제 표시기|
|**%r**|로캘의 12 시간제 시계 시간|
|**%R**|같음 **%h: %M**|
|**%S**|10 진수 초 (00-59)|
|**%t**|가로 탭 문자 (**\t**)|
|**%T**|같음 **%h:%m: %S**, ISO 8601 시간 형식|
|**%u**|ISO 8601 요일 (1-7; 10 진수 월요일은 1)|
|**%U**|주 번호는 10 진수 연도 (00-53), 여기서 첫 번째 일요일은 첫 번째 요일을 1|
|**%V**|ISO 8601 주 번호는 10 진수로 (00-53)|
|**%w**|10 진수 요일 (0-6; 일요일은 0 임)|
|**%W**|주 번호는 10 진수 연도 (00-53), 여기서 첫 번째 월요일은 첫 번째 요일을 1|
|**%x**|로캘의 날짜 표현|
|**%X**|로캘의 시간 표현|
|**%y**|세기 미 포함 10 진수 연도 (00-99)|
|**%Y**|세기 포함 10진수 연도|
|**%z**|ISO 8601 형식의 UTC 오프셋 문자가 없는 표준 시간대를 알 수 없는 경우|
|**%Z**|로캘의 표준 시간대 이름 또는 레지스트리 설정에 따라 표준 시간대 약어 문자가 없는 표준 시간대를 알 수 없는 경우|
|**%%**|퍼센트 기호|

에서처럼 합니다 **printf** 함수는 **#** 플래그는 모든 서식 코드 접두사 수 있습니다. 이 경우의 서식 코드 의미는 다음과 같이 변경됩니다.

|코드 형식|의미|
|-----------------|-------------|
|**%#a**, **%#A**, **%#b**, **%#B**, **%#g**, **%#G**, **%#h**, **%#n**, **%#p**, **%#t**, **%#u**, **%#w**, **%#X**, **%#z**, **%#Z**, **%#%**|**#** 플래그는 무시 됩니다.|
|**%#c**|긴 날짜 및 시간 표현, 로캘에 적합 합니다. 예를 들어: "화요일, 14, 1995 년 3 월 12시 41분: 29"입니다.|
|**%#x**|로캘에 적합 한 긴 날짜 표현입니다. 예를 들어: "화요일, 1995 3 월 14"입니다.|
|**%#d**, **%#D**, **%#e**를 **%#F**, **%#H**, **% #I**, **%#j**, **%#m**, **%#M**, **%#r**, **%#R**, **%#S**, **#T %** , **%#U**, **%#V**를 **%#W**, **%#y**, **#Y %**|앞에 오는 0 또는 공백 (있는 경우)를 제거 합니다.|

생성 된 ISO 8601 주와 연도의 주 기반 **%V**를 **%g**, 및 **%G**, 주 1 년 1 월 4 일, 첫 번째는 포함 된 주 인 월요일에 시작 하는 주 사용 4 일 이상의 연도 포함 하는 주입니다. 두 번째 연도의 첫 번째 월요일 이면 세 번째 또는 네 번째 이전 날짜의 일부인 이전 연도의 지난 주입니다. 해당 일에 대 한 **%V** 53, 및 바뀝니다 **%g** 하 고 **%G** 이전 연도의 숫자로 대체 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> 또는 \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> 또는 \<wchar.h>|

합니다 **_strftime_l** 하 고 **_wcsftime_l** 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[time](time-time32-time64.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[로캘](../../c-runtime-library/locale.md) <br/>
[시간 관리](../../c-runtime-library/time-management.md) <br/>
[문자열 조작](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
