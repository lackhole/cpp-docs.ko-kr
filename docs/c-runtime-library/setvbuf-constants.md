---
title: setvbuf 상수
ms.date: 11/04/2016
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
ms.openlocfilehash: 28c9debf7e51d06cb9a625bb0a52d578ce3142c6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742648"
---
# <a name="setvbuf-constants"></a>setvbuf 상수

## <a name="syntax"></a>구문

```
#include <stdio.h>
```

## <a name="remarks"></a>주의

이러한 상수는 `setvbuf`에 대한 버퍼의 형식을 나타냅니다.

가능한 값은 다음 매니페스트 상수에 의해 제공됩니다.

|상수|의미|
|--------------|-------------|
|`_IOFBF`|전체 버퍼링: `setvbuf` 호출에서 지정된 버퍼가 사용되고 크기는 `setvbuf` 호출에서 지정됩니다. 버퍼 포인터가 **NULL**이면 지정된 크기의 할당된 버퍼가 자동으로 사용됩니다.|
|`_IOLBF`|`_IOFBF`와 동일합니다.|
|`_IONBF`|`setvbuf` 호출 인수에 관계없이 버퍼는 사용되지 않습니다.|

## <a name="see-also"></a>참고 항목

[setbuf](../c-runtime-library/reference/setbuf.md)<br/>
[전역 상수](../c-runtime-library/global-constants.md)
