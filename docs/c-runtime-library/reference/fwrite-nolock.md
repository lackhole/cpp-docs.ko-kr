---
title: _fwrite_nolock
ms.date: 11/04/2016
api_name:
- _fwrite_nolock
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
- _fwrite_nolock
- fwrite_nolock
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
ms.openlocfilehash: 035ee1d958c6ea6a13481d92311733ded9ed5f2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956212"
---
# <a name="_fwrite_nolock"></a>_fwrite_nolock

스레드를 잠그지 않고 데이터를 스트림에 씁니다.

## <a name="syntax"></a>구문

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
쓰여질 데이터에 대한 포인터입니다.

*size*<br/>
항목 크기(바이트)입니다.

*count*<br/>
쓸 항목의 최대 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

[fwrite](fwrite.md)와 같습니다.

## <a name="remarks"></a>설명

이 함수는 **fwrite**의 잠기지 않은 버전입니다. 다른 스레드의 간섭 으로부터 보호 되지 않는다는 점을 제외 하 고는 **fwrite** 와 동일 합니다. 이는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 애플리케이션과 같은 스레드로부터 안전한 컨텍스트 또는 호출 범위에서 이미 스레드 격리를 처리하는 경우에만 이 함수를 사용합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fread](fread.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
