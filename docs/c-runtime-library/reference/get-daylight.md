---
title: _get_daylight
ms.date: 11/04/2016
apiname:
- __daylight
- _get_daylight
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
- get_daylight
- _get_daylight
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
ms.openlocfilehash: 03c3386e59379f460d3c07dc310153d990c02b05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332316"
---
# <a name="getdaylight"></a>_get_daylight

일광 절약 시간 오프셋(시간)을 검색합니다.

## <a name="syntax"></a>구문

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>매개 변수

*시간*<br/>
일관 절약 시간의 오프셋(시간)입니다.

## <a name="return-value"></a>반환 값

성공 하는 경우 또는 0 **errno** 값에 오류가 발생 합니다.

## <a name="remarks"></a>설명

합니다 **_get_daylight** 함수 정수로 일광 절약 시간의 시간 수를 검색 합니다. 일광 절약 시간이 적용 중인 경우 몇몇 지역에서 2시간 오프셋을 따르고 있더라도 기본 오프셋은 1시간입니다.

하는 경우 *시간* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EINVAL**합니다.

이 함수를 사용 하 여 매크로 대신 하는 것이 좋습니다 **_daylight** 또는 사용 되지 않는 함수 **__daylight**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_daylight**|\<time.h>|

자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
