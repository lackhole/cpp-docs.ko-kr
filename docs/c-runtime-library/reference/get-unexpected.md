---
title: _get_unexpected
ms.date: 11/04/2016
api_name:
- _get_unexpected
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
- __get_unexpected
- _get_unexpected
- get_unexpected
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
ms.openlocfilehash: 896313aba62a42b54e8920eafa46d85714404b1c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956434"
---
# <a name="_get_unexpected"></a>_get_unexpected

**예기치 않게**호출할 종료 루틴을 반환 합니다.

## <a name="syntax"></a>구문

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>반환 값

[set_unexpected](set-unexpected-crt.md)로 등록된 함수에 대한 포인터를 반환합니다. 함수가 설정 되지 않은 경우 반환 값을 사용 하 여 기본 동작을 복원할 수 있습니다. 이 값은 **NULL**일 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_unexpected**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
