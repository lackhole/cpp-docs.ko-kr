---
title: _rmtmp
ms.date: 11/04/2016
apiname:
- _rmtmp
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
- rmtmp
- _rmtmp
helpviewer_keywords:
- removing temporary files
- _rmtmp function
- files [C++], temporary
- rmtmp function
- files [C++], removing
- temporary files [C++], removing
ms.assetid: 7419501e-2587-4f2a-b469-0dca07f84736
ms.openlocfilehash: bf4f2cff48e8660682fc8a00d10d9a1fe960a6a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357425"
---
# <a name="rmtmp"></a>_rmtmp

임시 파일을 제거합니다.

## <a name="syntax"></a>구문

```C

int _rmtmp( void );
```

## <a name="return-value"></a>반환 값

**_rmtmp** 닫히고 삭제 된 임시 파일의 수를 반환 합니다.

## <a name="remarks"></a>설명

합니다 **_rmtmp** 함수는 현재 디렉터리에 있는 모든 임시 파일을 정리 합니다. 함수에서 만든 파일에만 제거 **tmpfile**; 임시 파일을 만든 동일한 디렉터리에만 사용 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_rmtmp**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

[tmpfile](tmpfile.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_flushall](flushall.md)<br/>
[tmpfile](tmpfile.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
