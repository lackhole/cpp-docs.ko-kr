---
title: _filelength, _filelengthi64
ms.date: 11/04/2016
apiname:
- _filelengthi64
- _filelength
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
- _filelength
- _filelengthi64
- filelengthi64
helpviewer_keywords:
- filelengthi64 function
- lengths, file
- filelength function
- _filelength function
- files [C++], length
- _filelengthi64 function
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
ms.openlocfilehash: 5434a6ea2155b75f1c034202477a67db36da8b3d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333796"
---
# <a name="filelength-filelengthi64"></a>_filelength, _filelengthi64

파일의 길이를 가져옵니다.

## <a name="syntax"></a>구문

```C
long _filelength(
   int fd
);
__int64 _filelengthi64(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
파일 설명자를 대상으로 지정합니다.

## <a name="return-value"></a>반환 값

둘 다 **_filelength** 하 고 **_filelengthi64** 파일 길이 (바이트)와 연결 된 대상 파일의 반환 *fd*합니다. 하는 경우 *fd* 잘못 된 파일 설명자 인이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 두 함수 모두 오류가 발생 하 여 설정-1l을 반환 실행은 계속 하도록 허용 하는 경우 **errno** 하 **EBADF**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**_filelength**|\<io.h>|
|**_filelengthi64**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_chsize](chsize.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_fileno](fileno.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_stat, _wstat 함수](stat-functions.md)<br/>
[_stat, _wstat 함수](stat-functions.md)<br/>
