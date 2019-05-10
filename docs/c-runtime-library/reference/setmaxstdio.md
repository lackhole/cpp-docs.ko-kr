---
title: _setmaxstdio
ms.date: 11/04/2016
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
ms.openlocfilehash: 58cffedf673e23a69c2d8040071b2e3353ff4502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356344"
---
# <a name="setmaxstdio"></a>_setmaxstdio

동시에 열리는 파일 수에 대 한 최대값을 설정 합니다 **stdio** 수준입니다.

## <a name="syntax"></a>구문

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>매개 변수

*newmax*<br/>
동시에 열리는 파일 수에 대 한 새 최대값은 **stdio** 수준입니다.

## <a name="return-value"></a>반환 값

반환 *newmax* 성공할 경우 그렇지 않으면-1입니다.

하는 경우 *newmax* 는 보다 작은 **_IOB_ENTRIES** 에 설명 된 대로 잘못 된 매개 변수 처리기를 운영 체제에서 사용할 수 있는 핸들의 최대 수는 호출 후 큰 [ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행이 함수는-1 반환 하 고 집합을 계속 하도록 허용 된 경우 **errno** 하 **EINVAL**합니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **_setmaxstdio** 함수에서 동시에 열 수 있는 파일 수에 대 한 최대값을 변경 합니다 **stdio** 수준입니다.

C 런타임 I/O는 이제 이전 버전에 비해 Win32 플랫폼에서 훨씬 더 많은 파일을 열 수 있도록 지원합니다. 최대 2,048 파일에 동시에 열 수를 [lowio 수준](../../c-runtime-library/low-level-i-o.md) (즉, 열 및 이용 하 여 액세스를 **열기 (_o)** 를 **읽기 (_r)**, **_write**를 등의 I/O 함수 패밀리). 최대 512 파일에 동시에 열 수를 [stdio 수준](../../c-runtime-library/stream-i-o.md) (즉, 열 및 이용 하 여 액세스를 **fopen**를 **fgetc**, **fputc** 를 함수 군을 등). 512 열려 있는 파일에서 제한 합니다 **stdio** 최대 2,048 이용 하 여 수준을 올릴 수는 **_setmaxstdio** 함수입니다.

때문에 **stdio**-와 같은 함수 수준 **fopen**, 맨 위에 빌드됩니다 합니다 **lowio** 함수 최대값 2,048은 개수에 대 한 하드 상한에 동시에 C 런타임 라이브러리를 통해 액세스 되는 파일을 엽니다.

> [!NOTE]
> 이 상한은 특정 Win32 플랫폼 및 구성에서 지원하는 수를 초과할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

참조 [_getmaxstdio](getmaxstdio.md) 사용 하는 예제에 대 한 **_setmaxstdio**합니다.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
