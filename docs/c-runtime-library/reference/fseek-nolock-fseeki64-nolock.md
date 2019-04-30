---
title: _fseek_nolock, _fseeki64_nolock
ms.date: 11/04/2016
apiname:
- _fseek_nolock
- _fseeki64_nolock
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
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
ms.openlocfilehash: 57e9a57223d6af620f4f9160923675b4873ab3ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287704"
---
# <a name="fseeknolock-fseeki64nolock"></a>_fseek_nolock, _fseeki64_nolock

파일 포인터를 지정된 위치로 이동합니다.

## <a name="syntax"></a>구문

```C
int _fseek_nolock(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64_nolock(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

*offset*<br/>
*origin*부터의 바이트 수입니다.

*origin*<br/>
초기 위치입니다.

## <a name="return-value"></a>반환 값

동일 [fseek](fseek-fseeki64.md) 하 고 [_fseeki64](fseek-fseeki64.md), 각각.

## <a name="remarks"></a>설명

이러한 함수는 잠기지 않은 버전의 [fseek](fseek-fseeki64.md) 하 고 [_fseeki64](fseek-fseeki64.md), 각각. 이러한 동일 [fseek](fseek-fseeki64.md) 하 고 [_fseeki64](fseek-fseeki64.md) 는 다른 스레드의 간섭 으로부터 보호 되지 않는다는 점을 제외 하 고 있습니다. 이러한 함수는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 애플리케이션과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
