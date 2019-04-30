---
title: _chsize_s
ms.date: 11/04/2016
apiname:
- _chsize_s
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
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: a56efe826d43c80dc2cdee295e58872e7dd3c9ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348512"
---
# <a name="chsizes"></a>_chsize_s

파일 크기를 변경합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_chsize](chsize.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

*size*<br/>
파일의 새 길이(바이트)입니다.

## <a name="return-value"></a>반환 값

**_chsize_s** 파일 크기 변경이 완료 되는 경우 값 0을 반환 합니다. 0이 아닌 반환 값은 오류를 나타냅니다: 반환 값은 **EACCES** 지정된 된 파일 액세스에 대해 잠겨 있으면 **EBADF** 지정 된 파일이 읽기 전용 이거나 설명자가 올바르지 않은 경우 **ENOSPC** 장치에 남아 있는 공간이 없는 경우 또는 **EINVAL** 크기는 0 보다 작은 경우. **errno** 동일한 값으로 설정 됩니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

합니다 **_chsize_s** 함수를 확장 또는 연결 된 파일을 자릅니다 *fd* 하 여 지정 된 길이로 *크기*합니다. 파일은 쓰기를 허용하는 모드로 열려 있어야 합니다. 파일이 확장되는 경우 Null 문자('\0')가 추가됩니다. 파일이 잘린 경우 짧아진 파일의 끝부터 파일의 원래 길이까지의 모든 데이터가 손실됩니다.

**_chsize_s** 파일 크기로 64 비트 정수를 가져오고 따라서 4GB 보다 큰 파일 크기를 처리할 수 있습니다. **_chsize** 32 비트 파일 크기로 제한 됩니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *fd* 크기나 유효한 파일 설명자가 0 보다 작거나, 아닙니다 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
