---
title: _fread_nolock_s2
ms.date: 11/04/2016
api_name:
- _fread_nolock_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fread_nolock_s
- stdio/_fread_nolock_s
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
ms.openlocfilehash: e7fded9860b7a1364841d5f9b8a7e3aa478a8420
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956901"
---
# <a name="_fread_nolock_s"></a>_fread_nolock_s

다른 스레드를 잠그지 않고 스트림에서 데이터를 읽습니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 이 버전의 [fread_nolock](fread-nolock.md)에 대한 보안 기능이 향상되었습니다.

## <a name="syntax"></a>구문

```C
size_t _fread_nolock_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t elementCount,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
데이터의 스토리지 위치입니다.

*bufferSize*<br/>
출력 버퍼의 바이트 크기입니다.

*elementSize*<br/>
읽을 항목의 크기(바이트)입니다.

*elementCount*<br/>
읽힐 항목의 최대 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

[fread_s](fread-s.md)를 참조하세요.

## <a name="remarks"></a>설명

이 함수는 **fread_s**의 잠기지 않은 버전입니다. 다른 스레드의 간섭 으로부터 보호 되지 않는다는 점을 제외 하 고 **fread_s** 와 동일 합니다. 이는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 애플리케이션과 같은 스레드로부터 안전한 컨텍스트 또는 호출 범위에서 이미 스레드 격리를 처리하는 경우에만 이 함수를 사용합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio.h>; C++: \<cstdio> 또는 \<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
