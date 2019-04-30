---
title: _query_new_handler
ms.date: 11/04/2016
apiname:
- _query_new_handler
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
- _query_new_handler
- query_new_handler
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
ms.openlocfilehash: febefbe46d95b7e5c8de026806a20d7eff74e7cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357880"
---
# <a name="querynewhandler"></a>_query_new_handler

현재 새 처리기 루틴의 주소를 반환합니다.

## <a name="syntax"></a>구문

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>반환 값

설정한 대로 현재 새 처리기 루틴의 주소를 반환 **_set_new_handler**합니다.

## <a name="remarks"></a>설명

C++ **_query_new_handler** 설정한 현재 예외 처리 함수의 주소를 반환 하는 함수는 C++ [_set_new_handler](set-new-handler.md) 함수입니다. **_set_new_handler** 경우 제어권을 얻는 예외 처리 함수를 지정 하는 데 사용 되는 **새** 연산자 메모리 할당에 실패 합니다. 자세한 내용은 C++ 언어 참조의 [new 및 delete 연산자](../../cpp/new-and-delete-operators.md)에 대한 설명을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_query_new_handler**|\<new.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
