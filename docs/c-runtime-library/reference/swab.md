---
title: _swab
ms.date: 11/04/2016
apiname:
- _swab
- stdlib/_swab
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
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: 64753383bcb94947e6b413b5f55ac6e2d9c7dbca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245509"
---
# <a name="swab"></a>_swab

바이트를 교환합니다.

## <a name="syntax"></a>구문

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>매개 변수

*src*<br/>
복사하고 교환할 데이터입니다.

*dest*<br/>
교환된 데이터에 대한 스토리지 위치입니다.

*n*<br/>
복사되고 교환될 바이트 수입니다.

## <a name="return-value"></a>반환 값

합니다 **swab** 함수 값을 반환 하지 않습니다. 함수 집합 **errno** 하 **EINVAL** 경우는 *src* 또는 *dest* 포인터가 null 또는 *n* 작습니다. 0와 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

경우 *n* 가 짝수인 합니다 **_swab** 복사본 함수 *n* 바이트 *src*, 각 바이트 쌍에 인접 한 교환 및 에서결과저장합니다.*dest*합니다. 하는 경우 *n* 홀수 이면 **_swab** 복사 하 고 첫 번째 교환 *n*-1 바이트 *src*, 최종 바이트가 복사 되지 않습니다. 합니다 **_swab** 함수는 일반적으로 다른 바이트 순서를 사용 하는 컴퓨터에 전송할 이진 데이터를 준비 하는 데 사용 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> 또는 \<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>참고자료

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
