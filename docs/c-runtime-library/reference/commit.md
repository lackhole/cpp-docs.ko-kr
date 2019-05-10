---
title: _commit
ms.date: 11/04/2016
apiname:
- _commit
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
- _commit
- commit
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
ms.openlocfilehash: 8408158cb3d4ef0d29d9af24d8a2acbd28e00192
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340360"
---
# <a name="commit"></a>_commit

디스크에 직접 파일을 플러시합니다.

## <a name="syntax"></a>구문

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

## <a name="return-value"></a>반환 값

**_commit** 파일을 성공적으로 되었으면 0을 반환 합니다. 디스크에 플러시되 합니다. 반환 값이-1 오류를 나타냅니다.

## <a name="remarks"></a>설명

**_commit** 함수는 연결 된 파일에 쓸 운영 체제를 강제로 *fd* 디스크. 이 호출은 지정된 파일이 운영 체제의 결정을 따르지 않고 즉시 플러시되도록 합니다.

하는 경우 *fd* 잘못 된 파일 설명자 인에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 **errno** 로 설정 된 **EBADF**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
