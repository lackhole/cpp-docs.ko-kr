---
title: mbsrtowcs
ms.date: 11/04/2016
apiname:
- mbsrtowcs
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
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 2bc0c8c9e2d871b6d1748c42dc02c627244dbf69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331144"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

현재 로캘의 멀티바이트 문자열을 해당하는 와이드 문자열로 변환합니다. 이때 멀티바이트 문자의 중간에서 변환을 다시 시작할 수 있습니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [mbsrtowcs_s](mbsrtowcs-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*wcstr*<br/>
변환된 결과 와이드 문자열을 저장하는 주소입니다.

*mbstr*<br/>
변환할 멀티바이트 문자열의 위치에 대한 간접 포인터입니다.

*count*<br/>
최대 문자 (바이트 아님) 변환 하 고 저장할 *wcstr*합니다.

*mbstate*<br/>
에 대 한 포인터를 **mbstate_t** 변환 상태 개체입니다. 이 값이 null 포인터이면 정적 내부 변환 상태 개체가 사용됩니다. 때문에 내부 **mbstate_t** 개체는 스레드로부터 안전 하지 않습니다, 전달 하는 항상 고유한 것이 좋습니다 *mbstate* 매개 변수입니다.

## <a name="return-value"></a>반환 값

종결 null 문자(있는 경우)를 포함하지 않고 정상적으로 변환된 문자 수를 반환합니다. 반환 (오류가 발생 하 고 설정 하는 경우 size_t)(-1) **errno** 를 eilseq로 설정 합니다.

## <a name="remarks"></a>설명

**mbsrtowcs** 함수는 직접 가리키는 멀티 바이트 문자의 문자열로 변환 *mbstr*를 가리키는 버퍼에 저장 된 와이드 문자로 *wcstr*, 에 포함 된 변환 상태를 사용 하 여 *mbstate*합니다. 변환이 계속 됩니다 각 문자에 대 한 중 하나는 종결 null 멀티 바이트 문자가 발견 될 때까지 현재 로캘에서 유효한 문자에 해당 하지 않는 멀티 바이트 시퀀스가 발생 하는 때까지 *개수* 문자 변환 되었습니다. 하는 경우 **mbsrtowcs** 때나 그 전에 멀티 바이트 null 문자 ('\0')를 발견 *개수* 로 변환 하 고 16 비트 종결 null 문자를 중지 합니다.

따라서 와이드 문자 문자열에 *wcstr* 는 null로 끝나는 경우에 **mbsrtowcs** 멀티 바이트 null 문자를 변환 하는 동안 발생 합니다. 가리키는 시퀀스 하는 경우 *mbstr* 하 고 *wcstr* 겹치는 동작 **mbsrtowcs** 정의 되지 않습니다. **mbsrtowcs** 현재 로캘의 LC_TYPE 범주 영향입니다.

합니다 **mbsrtowcs** 함수에서 다른 [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) 해당 다시 시작할 수 있다는입니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, 응용 프로그램을 사용할지 **mbsrlen** 대신 **mbslen**경우에 대 한 후속 호출 **mbsrtowcs** 를 사용 하는 대신 **mbstowcs**.

하는 경우 *wcstr* 가 null 포인터가 아닌 가리키는 포인터 개체 *mbstr* null 종결 문자도 달했기 때문에 변환이 중지 하는 경우 null 포인터가 할당 됩니다. 그렇지 않으면 변환된 마지막 멀티바이트 문자 바로 다음의 주소(있는 경우)가 할당됩니다. 그러므로 후속 함수에서 이 호출이 중지된 변환을 다시 시작할 수 있습니다.

경우는 *wcstr* 인수가 null 포인터를 *개수* 인수는 무시 됩니다 및 **mbsrtowcs** 대상 문자열의 와이드 문자에 필요한 크기를 반환 합니다. 하는 경우 *mbstate* 가 null 포인터인 경우 함수는 스레드로부터 안전한 정적 내부 **mbstate_t** 변환 상태 개체입니다. 경우 문자 시퀀스 *mbstr* 해당 멀티 바이트 없는 문자 표시를-1이 반환 하며 **errno** 로 설정 되어 **EILSEQ**합니다.

하는 경우 *mbstr* 에 설명 된 대로 isa null 포인터인 경우 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** -1을 반환 합니다.

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

합니다 **mbsrtowcs** 현재 스레드의 함수가 호출 함수는 다중 스레드 안전 **setlocale** 이 함수가 실행 중인으로 하며 *mbstate* 인수가 null 포인터가 아닙니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
