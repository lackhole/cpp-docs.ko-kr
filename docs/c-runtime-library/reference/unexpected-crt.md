---
title: unexpected(CRT)
ms.date: 11/04/2016
api_name:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 796f5ddbf8467656b5430de1d504f162d891864d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957812"
---
# <a name="unexpected-crt"></a>unexpected(CRT)

**Set_unexpected**를 사용 하 여 지정한 **종료** 또는 함수를 호출 합니다.

## <a name="syntax"></a>구문

```C
void unexpected( void );
```

## <a name="remarks"></a>설명

**예기치 않은** 루틴은 예외 처리의 C++ 현재 구현과 함께 사용 되지 않습니다. **예기치 않은** 호출이 기본적으로 **종료** 됩니다. 사용자 지정 종료 함수를 작성 하 고 함수 이름을 인수로 사용 하 여 **set_unexpected** 를 호출 하 여이 기본 동작을 변경할 수 있습니다. **set_unexpected**에 대 한 인수로 지정 된 마지막 함수를 **예기치 않게** 호출 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**unexpected**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
