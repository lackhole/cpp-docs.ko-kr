---
title: unexpected(CRT)
ms.date: 11/04/2016
apiname:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 78538c0a10e183e72c742b041b297275c0859a03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155487"
---
# <a name="unexpected-crt"></a>unexpected(CRT)

호출 **종료** 또는 함수를 사용 하 여 지정할 **set_unexpected**합니다.

## <a name="syntax"></a>구문

```C
void unexpected( void );
```

## <a name="remarks"></a>설명

합니다 **예기치 않은** 루틴의 현재 구현에서 사용 되지 않는 C++ 예외 처리 합니다. **예기치 않은** 호출 **종료** 기본적으로 합니다. 사용자 지정 종료 함수를 작성 하 고 호출 하 여이 기본 동작을 변경할 수 있습니다 **set_unexpected** 인수로 함수의 이름입니다. **예기치 않은** 인수로 주어진 마지막 함수 호출 **set_unexpected**합니다.

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
