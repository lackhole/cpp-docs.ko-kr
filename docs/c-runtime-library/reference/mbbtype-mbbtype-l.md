---
title: _mbbtype, _mbbtype_l
ms.date: 11/04/2016
apiname:
- _mbbtype
- _mbbtype_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: a6d17b99e4314c2ab836a16129ab8a0e6ac7720e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156891"
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l

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

**_mbbtype** 문자열에서 바이트 형식을 반환 합니다. 이 결정은 값으로 지정 된 대로 상황에 맞는 *형식*, 컨트롤 테스트 조건을 제공 합니다. *형식* 문자열의 이전 바이트의 형식입니다. 다음 표의 매니페스트 상수는 Mbctype.h에 정의됩니다.

|값 *형식*|**_mbbtype** 테스트|반환 값|*c*|
|---------------------|--------------------------|------------------|---------|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_SINGLE** (0)|단일 바이트 (0x20-0x7E, 0xA1 – 0xDF)|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_LEAD** (1)|선행 바이트 멀티 바이트 문자의 (0x81 – 0x9F, 0xE0 – 0xFC)|
|1 제외한 모든 값|유효한 단일 바이트 또는 선행 바이트|**_MBC_ILLEGAL**<br /><br /> ( -1)|잘못 된 문자 (모든 제외한 값 0x20-0x7E, 0xA1 – 0xDF, 0x81 – 0x9F, 0xE0 – 0xFC|
|1|유효한 후행 바이트|**_MBC_TRAIL** (2)|바이트 멀티 바이트 문자의 후행 (0x40-0x7E, 0x80-0xFC)|
|1|유효한 후행 바이트|**_MBC_ILLEGAL**<br /><br /> ( -1)|잘못 된 문자 (모든 제외한 값 0x20-0x7E, 0xA1 – 0xDF, 0x81 – 0x9F, 0xE0 – 0xFC|

## <a name="remarks"></a>설명

합니다 **_mbbtype** 함수는 멀티 바이트 문자에서 바이트 형식을 결정 합니다. 경우 값 *형식* 1 제외한 모든 값인 **_mbbtype** 멀티 바이트 문자의 유효한 단일 바이트 또는 선행 바이트에 대 한 테스트 합니다. 경우 값 *형식* 가 1 이면 **_mbbtype** 멀티 바이트 문자의 유효한 후행 바이트에 대 한 테스트 합니다.

출력 값의 설정이 적용 됩니다는 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 자세한 내용은 합니다. **_mbbtype** 버전의이 함수가 로캘 종속 동작에 현재 로캘을 사용 합니다 **_mbbtype_l** 제외 하 고 대신 전달 된 로캘 매개 변수를 사용 하 여 버전 동일 합니다. . 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

이전 버전에서는 **_mbbtype** 이름이 **chkctype**합니다. 새 코드를 사용 하 여 **_mbbtype** 대신 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* 반환 값으로 사용되는 매니페스트 상수의 정의에 해당합니다.

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[바이트 분류](../../c-runtime-library/byte-classification.md)<br/>
