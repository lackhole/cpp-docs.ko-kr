---
title: mbrtoc16, mbrtoc323
ms.date: 11/04/2016
api_name:
- mbrtoc16
- mbrtoc32
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: 52bcec5911fdc2ecbb073ae0042777aa4eb2b963
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952431"
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
변환할 멀티 바이트 문자에 해당 하는 **char16_t** 또는 **char32_t** 에 대 한 포인터입니다. Null인 경우 함수는 값을 저장하지 않습니다.

*source*<br/>
변환할 멀티바이트 문자열의 포인터입니다.

*max_bytes*<br/>
변환할 문자를 검사할 *소스의* 최대 바이트 수입니다. 이 값은 null 종결자를 포함 하 여 *원본*에 남아 있는 바이트 수와 1 사이의 값 이어야 합니다.

*state*<br/>
멀티 바이트 문자열을 하나 이상의 출력 문자로 해석 하는 데 사용 되는 **mbstate_t** 변환 상태 개체에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

성공 하면 현재 *상태* 값이 지정 된 경우 적용 되는 이러한 조건 중 첫 번째 값을 반환 합니다.

|값|조건|
|-----------|---------------|
|0|*원본* 에서 변환 된 다음 *max_bytes* 이하의 문자는 null 와이드 문자에 해당 하며, *destination* 이 null이 아닌 경우 저장 되는 값입니다.<br /><br /> *상태* 에는 초기 이동 상태가 포함 됩니다.|
|1과 *max_bytes*사이 (포함)|반환 되는 값은 유효한 멀티 바이트 문자를 완성 하는 *원본의* 바이트 수입니다. *대상이* null이 아닌 경우 변환 된 와이드 문자가 저장 됩니다.|
|-3|*대상이* null이 아닌 경우 함수에 대 한 이전 호출로 인해 발생 하는 다음 와이드 문자가 *대상* 에 저장 되었습니다. 이 함수 호출에서 *소스* 의 바이트를 사용 하지 않습니다.<br /><br /> *원본* 에서 둘 이상의 와이드 문자가 표시 되어야 하는 멀티 바이트 문자를 가리키는 경우 (예: 서로게이트 쌍) 다음 함수 호출에서 추가 문자를 쓰도록 *상태* 값이 업데이트 됩니다.|
|-2|다음 *max_bytes* bytes는 불완전 하지만 잠재적으로 유효한 멀티 바이트 문자를 나타냅니다. *대상*에는 값이 저장 되지 않습니다. 이 결과는 *max_bytes* 가 0 인 경우에 발생할 수 있습니다.|
|-1|인코딩 오류가 발생했습니다. 다음 *max_bytes* 이상의 바이트는 완전 하 고 유효한 멀티 바이트 문자에 영향을 주지 않습니다. *대상*에는 값이 저장 되지 않습니다.<br /><br /> **Eilseq** 가 **errno** 에 저장 되 고 변환 상태 *상태가* 지정 되지 않습니다.|

## <a name="remarks"></a>설명

**Mbrtoc16** 함수는 *원본* 에서 최대 *max_bytes* 바이트를 읽어 첫 번째 완전 하 고 유효한 멀티 바이트 문자를 찾은 다음 해당 하는 utf-16 문자를 *대상*에 저장 합니다. 소스 바이트는 현재 스레드 멀티바이트 로캘에 따라 해석됩니다. 멀티 바이트 문자에서 서로게이트 쌍과 같은 둘 이상의 UTF-16 출력 문자가 필요한 경우 *상태* 값은 다음에 **mbrtoc16**에 대 한 호출 시 *destination* 에 다음 utf-16 문자를 저장 하도록 설정 됩니다. **Mbrtoc32** 함수는 동일 하지만 출력이 u t f-32 문자로 저장 됩니다.

*Source* 가 null 인 경우 이러한 함수는 *대상*에 대해 **null** 의 인수를 사용 하는 호출에 해당 하는 호출을 반환 합니다. 이때 *source*의 경우 **""** , *max_bytes*의 경우 1입니다. *Destination* 및 *max_bytes* 의 전달 된 값은 무시 됩니다.

*Source* 가 null이 아닌 경우 함수는 문자열의 시작 부분에서 시작 하 여 *max_bytes* 바이트까지 검사 하 여 다음 멀티 바이트 문자를 완성 하는 데 필요한 바이트 수를 결정 합니다 (이동 시퀀스 포함). 검사된 바이트에 유효하고 완전한 멀티바이트 문자가 포함되는 경우 함수는 문자를 해당하는 16비트 또는 32비트 와이드 문자로 변환합니다. *Destination* 이 null이 아닌 경우 함수는 대상에 첫 번째 (및 가능한 경우) 결과 문자를 저장 합니다. 추가 출력 문자가 필요한 경우에는 값이 *상태로*설정 되므로 이후에 함수를 호출할 때 추가 문자가 출력 되 고 값-3이 반환 됩니다. 출력 문자가 더 이상 필요 하지 않으면 *state* 가 초기 이동 상태로 설정 됩니다.

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
