---
title: _initterm, _initterm_e
ms.date: 11/04/2016
api_name:
- _initterm_e
- _initterm
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
- _initterm_e
- initterm
- _initterm
- initterm_e
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
ms.openlocfilehash: 7e85494bf6c8215d03602ee112e1ff2c0f1cf6f2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954625"
---
# <a name="_initterm-_initterm_e"></a>_initterm, _initterm_e

함수 포인터의 테이블을 실행하고 초기화하는 내부 메서드입니다.

첫 번째 포인터는 테이블의 시작 위치이고 두 번째 포인터는 끝 위치입니다.

## <a name="syntax"></a>구문

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>반환 값

초기화에 실패하면 0이 아닌 값을 반환하고 오류를 throw하고, 오류가 발생하지 않으면 0을 반환합니다.

## <a name="remarks"></a>설명

이러한 메서드는 C++ 프로그램 초기화 중 내부적으로만 호출됩니다. 프로그램에서 이러한 메서드를 호출하지 마십시오.

이러한 메서드가 함수 항목의 테이블을 탐색 하는 경우 **NULL** 항목을 건너뛰고 계속 합니다.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
