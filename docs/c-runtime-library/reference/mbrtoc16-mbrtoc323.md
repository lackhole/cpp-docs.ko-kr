---
title: mbrtoc16, mbrtoc323
ms.date: 11/04/2016
apiname:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: f8573ac321772d19141be0228891b290ba48b217
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331586"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

반각 문자열의 첫 번째 멀티바이트 문자를 해당하는 UTF-16 또는 UTF-32 문자로 변환합니다.

## <a name="syntax"></a>구문

```C
size_t mbrtoc16(
   char16_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

size_t mbrtoc32(
   char32_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);
```

### <a name="parameters"></a>매개 변수

*destination*<br/>
에 대 한 포인터를 **char16_t** 하거나 **char32_t** 변환할 멀티 바이트 문자에 해당 합니다. Null인 경우 함수는 값을 저장하지 않습니다.

*source*<br/>
변환할 멀티바이트 문자열의 포인터입니다.

*max_bytes*<br/>
최대 바이트 수가 *원본* 변환할 문자에 대 한 검사 합니다. 1과에 남아 있는 모든 null 종결자를 포함 한 바이트 수 사이의 값이 있어야 *원본*합니다.

*state*<br/>
에 대 한 포인터를 **mbstate_t** 변환 상태 개체를 하나 이상의 출력 문자로 멀티 바이트 문자열을 해석 하는 데 사용 합니다.

## <a name="return-value"></a>반환 값

성공 하면 첫 번째 값을 반환 합니다. 지정 된 현재 적용 되는 이러한 조건 중 *상태* 값:

|값|조건|
|-----------|---------------|
|0|다음 *max_bytes* 또는 더 적은 문자에서 변환 *원본* 하는 경우 저장 된 값은 null 와이드 문자에 해당 *대상* null이 아닙니다.<br /><br /> *상태* 초기 이동 상태가 포함 되어 있습니다.|
|1 및 *max_bytes*(포함)|반환 값은 바이트 수가 *원본* 유효한 멀티 바이트 문자를 완성 하는 합니다. 경우 저장 되는 변환 된 와이드 문자 *대상* null이 아닙니다.|
|-3|에 저장 된 함수에 대 한 이전 호출에서 발생 하는 다음 와이드 문자가 *대상* 하는 경우 *대상* null이 아닙니다. 바이트 *원본* 이 호출 함수에 의해 사용 됩니다.<br /><br /> 때 *소스* (예: 서로게이트 쌍)을 나타내기 위해 둘 이상의 와이드 문자는 멀티 바이트 문자를 가리키는 경우 *상태* 값이 다음 함수 호출 기록 되도록 업데이트  추가 문자입니다.|
|-2|다음 *max_bytes* 바이트는 완료 되지 않았지만 잠재적으로 유효한 멀티 바이트 문자를 나타냅니다. 값에 저장 됩니다 *대상*합니다. 이 결과 경우에 발생할 수 있습니다 *max_bytes* 은 0입니다.|
|-1|인코딩 오류가 발생했습니다. 다음 *max_bytes* 또는 개 이하의 바이트가 완전 하며 올바른 멀티 바이트 문자에 기여 하지 않습니다. 값에 저장 됩니다 *대상*합니다.<br /><br /> **EILSEQ** 에 저장 됩니다 **errno** 되며, 변환 상태 *상태* 지정 되지 않았습니다.|

## <a name="remarks"></a>설명

합니다 **mbrtoc16** 함수를 읽고 *max_bytes* 바이트 *원본* 그 다음으로 첫 번째 완전 하 고 유효한 멀티 바이트 문자를 해당 하는 utf-16 저장소를 찾을 수 문자 *대상*합니다. 소스 바이트는 현재 스레드 멀티바이트 로캘에 따라 해석됩니다. 멀티 바이트 문자에 서로게이트 쌍을 같은 둘 이상의 utf-16 출력 문자가 필요한 경우 해당 *상태* 값에 다음 utf-16 문자를 저장 하도록 설정 됩니다 *대상* 의다음호출에서**mbrtoc16**합니다. 합니다 **mbrtoc32** 함수는 동일 하지만, 출력이 UTF-32 문자로 저장 됩니다.

경우 *원본* 가 null 이면 반환 이러한 함수 호출에 해당 하는 인수를 사용 하 여 만든 **NULL** 에 대 한 *대상*하십시오 **""** 에대한*소스*, 및 1 *max_bytes*합니다. 전달 된 값 *대상* 하 고 *max_bytes* 무시 됩니다.

하는 경우 *소스* 는 null이 아닌 함수 문자열의 시작 부분에서 시작 하 고 최대 검사 *max_bytes* 다음 멀티 바이트 문자를 완성 하는 데 필요한 바이트 수를 결정 하는 바이트 포함 이동 시퀀스입니다. 검사된 바이트에 유효하고 완전한 멀티바이트 문자가 포함되는 경우 함수는 문자를 해당하는 16비트 또는 32비트 와이드 문자로 변환합니다. 하는 경우 *대상* null이 아닌 대상에 첫 번째 (그리고 유일 할 수 있음) 결과 문자 함수 저장 합니다. 값이 설정 추가 출력 문자가 필요한 경우 *상태*함수에 대 한 후속 호출에서 추가 문자를 출력 하 고-3 값을 반환 되도록 합니다. 출력 문자가 더 이상 다음 필요한 경우 *상태* 초기 이동 상태로 설정 됩니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uchar.h>|\<cuchar>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
