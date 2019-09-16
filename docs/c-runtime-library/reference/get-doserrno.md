---
title: _get_doserrno
ms.date: 11/04/2016
api_name:
- _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 2810ead8bdd7d6c77cb2b55f4f97371bfc9751e6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956033"
---
# <a name="_get_doserrno"></a>_get_doserrno

**Errno** 값으로 변환 되기 전에 운영 체제에서 반환 하는 오류 값을 가져옵니다.

## <a name="syntax"></a>구문

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
**_Doserrno** global 매크로의 현재 값으로 채워질 정수에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

**_Get_doserrno** 성공 하면 0을 반환 합니다. 실패 하면 오류 코드를 반환 합니다. *Pvalue* 가 **NULL**인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 **EINVAL**를 반환 합니다.

## <a name="remarks"></a>설명

**_Doserrno** global 매크로는 CRT를 초기화 하는 동안 프로세스 실행이 시작 되기 전에 0으로 설정 됩니다. 운영 체제 오류를 반환하는 시스템 수준 함수 호출에 의해 반환되는 운영 체제 오류 값으로 설정되며, 실행 중 0으로 다시 설정되지 않습니다. 함수에서 반환 하는 오류 값을 확인 하는 코드를 작성 하는 경우 함수를 호출 하기 전에 [_set_doserrno](set-doserrno.md) 를 사용 하 여 항상 **_doserrno** 를 지워야 합니다. 다른 함수 호출이 **_doserrno**을 덮어쓸 수 있으므로 함수 호출 직후 **_get_doserrno** 를 사용 하 여 값을 확인 합니다.

이식 가능한 오류 코드에 **_get_doserrno** 대신 [_get_errno](get-errno.md) 를 권장 합니다.

**_Doserrno** 의 가능한 값은 errno > \<에 정의 되어 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib>(C++)|\<errno.h>, \<cerrno>(C++)|

**_get_doserrno** 는 Microsoft 확장입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
