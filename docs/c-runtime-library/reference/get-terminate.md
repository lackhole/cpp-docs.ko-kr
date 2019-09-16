---
title: _get_terminate
ms.date: 11/04/2016
api_name:
- _get_terminate
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
- get_terminate
- _get_terminate
- __get_terminate
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
ms.openlocfilehash: 7a9bfb6f8be1c990b349f14055eb2fe5c409e0d5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955688"
---
# <a name="_get_terminate"></a>_get_terminate

**Terminate**에서 호출할 종료 루틴을 반환 합니다.

## <a name="syntax"></a>구문

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>반환 값

[set_terminate](set-terminate-crt.md)로 등록된 함수에 대한 포인터를 반환합니다. 함수가 설정 되지 않은 경우 반환 값을 사용 하 여 기본 동작을 복원할 수 있습니다. 이 값은 **NULL**일 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
