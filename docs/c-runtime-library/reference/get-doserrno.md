---
title: _get_doserrno
ms.date: 11/04/2016
apiname:
- _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 700f710e6d94f48b03697325bb720dbc539fe04e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287748"
---
# <a name="getdoserrno"></a>_get_doserrno

으로 변환 되기 전에 운영 체제에서 반환 된 오류 값을 가져옵니다는 **errno** 값입니다.

## <a name="syntax"></a>구문

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
현재 값으로 채워지는 정수에 대 한 포인터를 **_doserrno** 전역 매크로입니다.

## <a name="return-value"></a>반환 값

하는 경우 **_get_doserrno** 성공 하면 0을 반환 합니다; 실패 하면 오류 코드를 반환 합니다. 하는 경우 *pValue* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

합니다 **_doserrno** 전역 매크로 CRT 초기화 하는 동안 0으로 설정 됩니다, 프로세스 실행을 시작 합니다. 운영 체제 오류를 반환하는 시스템 수준 함수 호출에 의해 반환되는 운영 체제 오류 값으로 설정되며, 실행 중 0으로 다시 설정되지 않습니다. 항상 함수에서 반환 된 오류 값을 확인 하는 코드를 작성 하는 경우 **_doserrno** 사용 하 여 [_set_doserrno](set-doserrno.md) 함수 호출 전에 합니다. 다른 함수 호출 덮어쓸 수 있으므로 **_doserrno**를 사용 하 여 값을 확인 합니다. **_get_doserrno** 함수 호출 후 바로.

것이 좋습니다 [_get_errno](get-errno.md) of **_get_doserrno** 이식 가능한 오류 코드에 대 한 합니다.

가능한 값 **_doserrno** 에 정의 된 \<errno.h >.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib>(C++)|\<errno.h>, \<cerrno>(C++)|

**_get_doserrno** Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
