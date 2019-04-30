---
title: _get_fmode
ms.date: 11/04/2016
apiname:
- _get_fmode
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
- get_fmode
- _get_fmode
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
ms.openlocfilehash: dc4740b20ab7283dd8b9f73f458eaba34e582832
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287564"
---
# <a name="getfmode"></a>_get_fmode

파일 I/O 연산에 대한 기본 파일 변환 모드를 가져옵니다.

## <a name="syntax"></a>구문

```C
errno_t _get_fmode(
   int * pmode
);
```

### <a name="parameters"></a>매개 변수

*pmode*<br/>
현재 기본 모드로 채워질 정수에 대 한 포인터: **_O_TEXT** 하거나 **_O_BINARY**합니다.

## <a name="return-value"></a>반환 값

성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다. 하는 경우 *pmode* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

이 함수는 [_fmode](../../c-runtime-library/fmode.md) 전역 변수의 값을 가져옵니다. 이 변수 하위 수준 모두에 대 한 기본 파일 변환 모드를 지정 하 고 파일 I/O 작업을 같은 스트림 **_open**를 **_pipe**를 **fopen**, 및 [ freopen](freopen-wfreopen.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_get_fmode**|\<stdlib.h>|\<fcntl.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_set_fmode](set-fmode.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[_fmode](../../c-runtime-library/fmode.md)<br/>
[_set_fmode](set-fmode.md)<br/>
[_setmode](setmode.md)<br/>
[텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
