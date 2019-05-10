---
title: _RTC_SetErrorFunc
ms.date: 11/04/2016
apiname:
- _RTC_SetErrorFunc
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
apitype: DLLExport
f1_keywords:
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
ms.openlocfilehash: 6b292d685eea8eccb9e9b2a3c3e6cd903d501005
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357211"
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc

RTC(런타임 오류 검사) 보고를 위한 처리기로 함수를 지정합니다. 이 함수는 사용 되지 않습니다. 사용 하 여 **_RTC_SetErrorFuncW** 대신 합니다.

## <a name="syntax"></a>구문

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>매개 변수

*function*<br/>
런타임 오류 검사를 처리할 함수의 주소입니다.

## <a name="return-value"></a>반환 값

이전에 정의된 오류 함수입니다. 이전에 정의 된 함수가 없는 경우 반환 **NULL**합니다.

## <a name="remarks"></a>설명

이 함수를 사용 하지 마십시오 대신 **_RTC_SetErrorFuncW**합니다. 이전 버전과의 호환성을 위해서만 유지됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)<br/>
