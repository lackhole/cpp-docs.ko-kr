---
title: _query_new_mode
ms.date: 11/04/2016
apiname:
- _query_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 327f22c847793316bd126721b4a66846d7da84dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358075"
---
# <a name="querynewmode"></a>_query_new_mode

설정한 새 처리기 모드를 나타내는 정수를 반환 **_set_new_mode** 에 대 한 **malloc**합니다.

## <a name="syntax"></a>구문

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>반환 값

에 대 한 현재 새 처리기 모드를 0 또는 1을 반환 합니다. **malloc**합니다. 반환 값이 1 이면 메모리를 할당 하지 못했습니다 **malloc** ; 새 처리기 루틴을 호출 반환 값이 0 되지 않은 것을 나타냅니다.

## <a name="remarks"></a>설명

C++ **_query_new_mode** 함수에 의해 설정 된 새 처리기 모드를 나타내는 정수를 반환 합니다 C++ [_set_new_mode](set-new-mode.md) 함수 [malloc](malloc.md). 새 처리기 모드를 나타내는 메모리 할당을 실패 하는지를 **malloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 [_set_new_handler](set-new-handler.md)합니다. 기본적으로 **malloc** 실패 시 새 처리기 루틴을 호출 하지 않습니다. 사용할 수 있습니다 **_set_new_mode** 이므로이 동작을 재정의 하려면 실패 하는 **malloc** 과 같은 새 처리기 루틴을 호출 방식으로 **새** 연산자 않습니다 하지 못한 경우 메모리를 할당 합니다. 자세한 내용은 C++ 언어 참조의 [new 및 delete 연산자](../../cpp/new-and-delete-operators.md)에 대한 설명을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_query_new_mode**|\<new.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
