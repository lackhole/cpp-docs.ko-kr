---
title: __uncaught_exception
ms.date: 11/04/2016
apiname:
- __uncaught_exception
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
- __uncaught_exception
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
ms.openlocfilehash: 19d1e18af27722d6f9da39ebaaf6c9415c281849
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268899"
---
# <a name="uncaughtexception"></a>__uncaught_exception

하나 이상의 예외가 throw 되었지만 아직 처리 되지 않은 해당 여부를 나타냅니다 **catch** 블록을 [try / catch](../../cpp/try-throw-and-catch-statements-cpp.md) 문입니다.

## <a name="syntax"></a>구문

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>반환 값

**true** 시간부터 예외가는 **시도** 일치 될 때까지 차단 **catch** 블록 초기화 되었으면이 고, 그렇지 **false**합니다.

## <a name="remarks"></a>설명

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>참고자료

[try, throw 및 catch 문(C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
