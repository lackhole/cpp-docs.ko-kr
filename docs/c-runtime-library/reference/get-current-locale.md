---
title: _get_current_locale
ms.date: 11/04/2016
apiname:
- _get_current_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
ms.openlocfilehash: 87c30ee701d8f7d3a89a0aa61ba18a7f854bc9b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332296"
---
# <a name="getcurrentlocale"></a>_get_current_locale

현재 로캘을 나타내는 로캘 개체를 가져옵니다.

## <a name="syntax"></a>구문

```C
_locale_t _get_current_locale(void);
```

## <a name="return-value"></a>반환 값

현재 로캘을 나타내는 로캘 개체입니다.

## <a name="remarks"></a>설명

합니다 **_get_current_locale** 함수는 현재 설정 가져옵니다 스레드 로캘을 해당 로캘을 나타내는 로캘 개체를 반환 합니다.

이 함수의 이전 이름인 **__get_current_locale** (사용 하 여 선행 밑줄이 두 개)가 사용 되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_current_locale**|\<locale.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
