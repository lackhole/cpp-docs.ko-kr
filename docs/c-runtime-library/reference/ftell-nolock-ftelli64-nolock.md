---
title: _ftell_nolock, _ftelli64_nolock
ms.date: 11/04/2016
apiname:
- _ftelli64_nolock
- _ftell_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftelli64_nolock
- ftelli64_nolock
- ftell_nolock
- _ftell_nolock
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
ms.openlocfilehash: 58bfc8c7a8b8e820fdec09d52e24dfcb07f328f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332938"
---
# <a name="ftellnolock-ftelli64nolock"></a>_ftell_nolock, _ftelli64_nolock

스레드를 잠그지 않고 파일 포인터의 현재 위치를 가져옵니다.

## <a name="syntax"></a>구문

```C
long _ftell_nolock(
   FILE *stream
);
__int64 _ftelli64_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
대상 합니다 **파일** 구조입니다.

## <a name="return-value"></a>반환 값

동일 **ftell** 하 고 **_ftelli64**합니다. 자세한 내용은 [ftell, _ftelli64](ftell-ftelli64.md)합니다.

## <a name="remarks"></a>설명

이러한 함수는 잠기지 않은 버전의 **ftell** 하 고 **_ftelli64**, 각각. 동일 **ftell** 하 고 **_ftelli64** 는 다른 스레드의 간섭 으로부터 보호 되지 않는다는 점을 제외 하 고 있습니다. 이러한 함수는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 애플리케이션과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|선택적 헤더|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio.h>|\<errno.h>|
|**_ftelli64_nolock**|\<stdio.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
