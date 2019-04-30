---
title: _ecvt_s
ms.date: 04/05/2018
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
ms.openlocfilehash: 0123c618eb5ba614bd8e5b5b3f1f4b0aff539c4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288257"
---
# <a name="ecvts"></a>_ecvt_s

변환 된 **이중** 숫자를 문자열로 합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_ecvt](ecvt.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _ecvt_s(
   char * _Buffer,
   size_t _SizeInBytes,
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
);
template <size_t size>
errno_t _ecvt_s(
   char (&_Buffer)[size],
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
); // C++ only
```

### <a name="parameters"></a>매개 변수

*_Buffer*<br/>
변환의 결과인 숫자 문자열에 대한 포인터로 채워집니다.

*_SizeInBytes*<br/>
버퍼의 크기(바이트)입니다.

*_Value*<br/>
변환할 숫자입니다.

*_Count*<br/>
저장된 자릿수입니다.

*_Dec*<br/>
저장된 소수점 위치입니다.

*_Sign*<br/>
변환된 숫자의 부호입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

다음 표에 나와 있는 잘못된 매개 변수의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EINVAL**합니다.

### <a name="error-conditions"></a>오류 조건

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|반환 값|값 *버퍼*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|any|any|any|any|any|**EINVAL**|수정되지 않습니다.|
|되지 **NULL** (유효한 메모리를 가리킴)|<=0|any|any|any|any|**EINVAL**|수정되지 않습니다.|
|any|any|any|any|**NULL**|any|**EINVAL**|수정되지 않습니다.|
|any|any|any|any|any|**NULL**|**EINVAL**|수정되지 않습니다.|

## <a name="security-issues"></a>보안 문제

**_ecvt_s** 하는 경우 액세스 위반이 발생할 *버퍼* 유효한 메모리를 가리키지 아니며 **NULL**합니다.

## <a name="remarks"></a>설명

합니다 **_ecvt_s** 함수는 부동 소수점 숫자를 문자열로 변환 합니다. 합니다 *이름이 _Value* 매개 변수는 변환할 부동 소수점 숫자입니다. 이 함수를 저장 *개수* 자릿수 *이름이 _Value* 문자열로 고 null 문자 ('\0')를 추가 합니다. 경우에 자릿수 *이름이 _Value* 초과 *_Count*, 낮은 자리 숫자가 반올림 됩니다. 개 보다 적으면 *개수* 숫자, 문자열은 0으로 채워집니다.

숫자만 문자열에 저장됩니다. 소수점 및 부호의 위치 *이름이 _Value* 에서 얻을 수 있습니다 *_Dec* 하 고 *(_s)* 호출 후 합니다. 합니다 *_Dec* 매개 변수는 문자열의 시작을 기준으로 소수점의 위치를 제공 하는 정수 값을 가리킵니다. 0 또는 음의 정수 값은 소수점이 첫 번째 숫자의 왼쪽에 있다는 것을 나타냅니다. 합니다 *(_s)* 매개 변수 변환 된 숫자의 부호를 나타내는 정수를 가리킵니다. 정수 값이 0이면 숫자가 양수입니다. 그렇지 않으면 숫자가 음수입니다.

길이의 버퍼로 **_CVTBUFSIZE** 임의의 부동 소수점 값이 부족 합니다.

차이점 **_ecvt_s** 하 고 **_fcvt_s** 의 해석를 *_Count* 매개 변수입니다. **_ecvt_s** 해석 *_Count* 출력 문자열에 전체 자릿수와 반면 **_fcvt_s** 해석 *_Count* 뒤의 자릿수로 숫자로 소수점입니다.

C++에서는 템플릿 오버로드로 인해 이 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|선택적 헤더|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// ecvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( )
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_ecvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 12000
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
