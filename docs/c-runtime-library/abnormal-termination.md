---
title: _abnormal_termination
ms.date: 11/04/2016
api_name:
- _abnormal_termination
api_location:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _abnormal_termination
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
ms.openlocfilehash: b66cf0df998b4e33a9f3425fdf0f260d163f423b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944717"
---
# <a name="_abnormal_termination"></a>_abnormal_termination

시스템이 종료 처리기의 내부 목록을 실행하는 동안 [try-finally](../cpp/try-finally-statement.md) 문의 `__finally` 블록이 입력되었는지 여부를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
int   _abnormal_termination(
   );
```

## <a name="return-value"></a>Return Value

시스템이 스택을 *해제*하면 **true**이고, 해제하지 않으면 **false**입니다.

## <a name="remarks"></a>설명

해제 예외를 관리하기 위해 사용되는 내부 함수이며 사용자 코드에서 호출할 수 없습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|_abnormal_termination|excpt.h|

## <a name="see-also"></a>참고 항목

[try-finally 문](../cpp/try-finally-statement.md)
