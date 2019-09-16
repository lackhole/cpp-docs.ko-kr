---
title: _mbbtype, _mbbtype_l
ms.date: 11/04/2016
api_name:
- _mbbtype
- _mbbtype_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
ms.openlocfilehash: ba4311921a0924d3f447feb1929a81ae1d816604
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952718"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype, _mbbtype_l

이전 바이트에 따라 바이트 형식을 반환합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
테스트할 문자입니다.

*type*<br/>
테스트할 바이트의 형식입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbbtype** 는 문자열의 바이트 형식을 반환 합니다. 이 결정은 컨트롤 테스트 조건을 제공 하는 *형식의*값에 지정 된 대로 상황에 맞는 것입니다. *형식은* 문자열에서 이전 바이트의 형식입니다. 다음 표의 매니페스트 상수는 Mbctype.h에 정의됩니다.

|*형식의* 값|**_mbbtype** 테스트|반환 값|*c*|
|---------------------|--------------------------|------------------|---------|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_SINGLE** (0)|싱글바이트 (0x20-0x7E, 0xA1-0Xa1)|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_LEAD** (1)|멀티 바이트 문자의 선행 바이트 (0x81-0x9F, 0xE0-0xFC)|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_ILLEGAL**<br /><br /> ( -1)|잘못 된 문자 (0x20-0x7E, 0xA1-0Xa1, 0x81-0x9F, 0xE0-0Xa1를 제외한 모든 값)|
|1|유효한 후행 바이트|**_MBC_TRAIL** (2)|멀티 바이트 문자의 후행 바이트 (0x40-0x7E, 0x80-0xFC)|
|1|유효한 후행 바이트|**_MBC_ILLEGAL**<br /><br /> ( -1)|잘못 된 문자 (0x20-0x7E, 0xA1-0Xa1, 0x81-0x9F, 0xE0-0Xa1를 제외한 모든 값)|

## <a name="remarks"></a>설명

**_Mbbtype** 함수는 멀티 바이트 문자에서 바이트 형식을 결정 합니다. *Type* 의 값이 1을 제외한 모든 값 인 경우 **_mbbtype** 는 멀티 바이트 문자의 유효한 단일 바이트 또는 선행 바이트를 테스트 합니다. *Type* 값이 1 인 경우 **_mbbtype** 는 멀티 바이트 문자의 유효한 후행 바이트를 테스트 합니다.

출력 값은 로캘의 **LC_CTYPE** 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, _wsetlocale을](setlocale-wsetlocale.md) 참조 하세요. 이 함수의 **_mbbtype** 버전은이 로캘 종속 동작에 현재 로캘을 사용 합니다. **_mbbtype_l** 버전은 전달 된 로캘 매개 변수를 대신 사용 한다는 점을 제외 하 고 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이전 버전에서 **_mbbtype** 의 이름은 **chkctype**입니다. 새 코드의 경우 대신 **_mbbtype** 를 사용 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 반환 값으로 사용되는 매니페스트 상수의 정의에 해당합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
