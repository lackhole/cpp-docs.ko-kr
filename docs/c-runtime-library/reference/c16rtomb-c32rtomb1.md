---
title: c16rtomb, c32rtomb
ms.date: 01/22/2018
apiname:
- c16rtomb
- c32rtomb
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
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: ad58184c7bab6f95a842bda5f9eb545f09434a3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341758"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

UTF-16 또는 UTF-32 와이드 문자를 현재 로캘의 멀티바이트 문자로 변환합니다.

## <a name="syntax"></a>구문

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>매개 변수

*mbchar*<br/>
변환된 멀티바이트 문자를 저장하는 배열에 대한 포인터입니다.

*wchar*<br/>
변환할 와이드 문자입니다.

*state*<br/>
에 대 한 포인터를 **mbstate_t** 개체입니다.

## <a name="return-value"></a>반환 값

배열 개체에 저장 된 바이트 수가 *mbchar*, 이동 시퀀스 포함 합니다. 하는 경우 *wchar* 유효한 와이드 문자가 값 아닙니다 (**size_t**)(-1) 반환 되 면 **errno** 로 설정 되어 **EILSEQ**, 값*상태* 지정 되지 않았습니다.

## <a name="remarks"></a>설명

합니다 **c16rtomb** 함수는 utf-16 문자 변환 *wchar* 현재 로캘에서 해당 하는 멀티 바이트 반각 문자 시퀀스입니다. 하는 경우 *mbchar* 가 가리키는 배열 개체에 변환된 된 시퀀스 함수 저장소는 null 포인터가 아닌 *mbchar*합니다. 최대 **MB_CUR_MAX** 에 저장 된 바이트 *mbchar*, 및 *상태* 결과 멀티 바이트 이동 상태로 설정 됩니다.    하는 경우 *wchar* null 와이드 문자를 하는 데 필요한 시퀀스는 뒤에 null 문자가 필요한 경우에 초기 이동 상태가 저장 되는 복원 하 고 *상태* 초기 변환 상태로 설정 됩니다. 합니다 **c32rtomb** 함수는 동일 하지만, UTF-32 문자를 변환 합니다.

경우 *mbchar* 가 null 포인터인 경우 동작은 내부 버퍼에 대 한 대체 하는 함수 호출과 동일 *mbchar* 및 와이드 null 문자에 대 한 *wchar*합니다.

합니다 *상태* 변환 상태 개체를 사용 하면이 함수 및 멀티 바이트 출력 문자의 이동 상태를 유지 관리 하는 다른 다시 시작 가능 함수에 대 한 후속 호출을 수행할 수 있습니다. 다시 시작 가능 및 시작할 수 없는 함수의 사용을 혼합 하는 경우 또는 호출 하는 경우 결과가 정의 되지 않습니다 **setlocale** 다시 시작 가능 함수 호출 간에 이루어집니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
