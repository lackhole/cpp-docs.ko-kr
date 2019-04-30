---
title: srand
ms.date: 1/02/2018
apiname:
- srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- srand
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.openlocfilehash: 6545d4eba6c17fd55bb2b8cf23fb0319d1c96bee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354888"
---
# <a name="srand"></a>srand

사용 하는 난수 생성기에 대 한 시작 시드 값을 설정 합니다 **rand** 함수입니다.

## <a name="syntax"></a>구문

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>매개 변수

*seed*<br/>
의사 난수 생성을 위한 시드

## <a name="remarks"></a>설명

합니다 **srand** 함수는 현재 스레드에서 일련의 의사 난수 정수 생성을 위한 시작 지점을 설정 합니다. 호출 결과의 순서를 만들도록 생성기를 다시 초기화 해야 합니다 **srand** 함수를 사용한 것과 동일한 *초기값* 인수를 다시 합니다. 에 대 한 다른 모든 값 *시드* 생성기 의사 난수 시퀀스에서 다른 시작 지점으로 설정 합니다. **rand** 생성 된 난수를 검색 합니다. 호출 **rand** 호출 하기 전에 **srand** 호출 하는 것 같은 시퀀스를 생성 **srand** 사용 하 여 *초기값* 1로 전달 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[rand](rand.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[rand](rand.md)<br/>
