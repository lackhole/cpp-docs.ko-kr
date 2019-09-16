---
title: _RTC_GetErrDesc
ms.date: 11/04/2016
api_name:
- _RTC_GetErrDesc
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- RTC_GetErrDesc
- _RTC_GetErrDesc
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: 7174e9242b77a904df817886df4f8c763e3e0b2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949052"
---
# <a name="_rtc_geterrdesc"></a>_RTC_GetErrDesc

RTC(런타임 오류 검사) 형식에 대한 간단한 설명을 반환합니다.

## <a name="syntax"></a>구문

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>매개 변수

*errnum*<br/>
0과 **_RTC_NumErrors**에서 반환한 값에서 1을 뺀 수 사이의 숫자를 반환합니다.

## <a name="return-value"></a>반환 값

런타임 오류 검사 시스템에서 검색된 오류 형식 중 하나에 대한 간단한 설명을 포함하는 문자열입니다. Error가 0 보다 작거나 [_RTC_NumErrors](rtc-numerrors.md)에서 반환 된 값 보다 크거나 같으면 **_RTC_GetErrDesc** 는 **NULL**을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[런타임 오류 검사](../../c-runtime-library/run-time-error-checking.md)<br/>
