---
title: _get_pgmptr
ms.date: 11/04/2016
apiname:
- _get_pgmptr
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_pgmptr
- _get_pgmptr
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
ms.openlocfilehash: 2d3959a69d85fca38e4d099d3365553f88fd015f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287504"
---
# <a name="getpgmptr"></a>_get_pgmptr

현재 값을 가져옵니다 합니다 **_pgmptr** 전역 변수입니다.

## <a name="syntax"></a>구문

```C
errno_t _get_pgmptr(
   char **pValue
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
현재 값을 채울 문자열에 대 한 포인터를 **_pgmptr** 변수입니다.

## <a name="return-value"></a>반환 값

성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다. 하는 경우 *pValue* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

호출 **_get_pgmptr** 프로그램 좁은 진입점이 있으면 같은 **main ()** 하거나 **WinMain()** 합니다. 합니다 **_pgmptr** 전역 변수는 프로세스와 관련 된 실행 파일의 전체 경로 포함 합니다. 자세한 내용은 [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_get_wpgmptr](get-wpgmptr.md)<br/>
