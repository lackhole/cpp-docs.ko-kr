---
title: _get_osfhandle
ms.date: 05/29/2018
apiname:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: cc3b50e3d3f65bee83b8df83aa0adb5c8694e35a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821660"
---
# <a name="getosfhandle"></a>_get_osfhandle

지정된 파일 설명자와 연결된 운영 체제 파일 핸들을 검색합니다.

## <a name="syntax"></a>구문

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
기존 파일 설명자입니다.

## <a name="return-value"></a>반환 값

경우에 운영 체제 파일 핸들을 반환 합니다 *fd* 유효 합니다. 그렇지 않으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 반환 **INVALID_HANDLE_VALUE** (-1). 또한 설정 **errno** 하 **EBADF**, 잘못 된 파일 핸들을 나타내는입니다. 경고 Win32 파일 핸들을으로 결과 사용 하는 경우를 방지 하려면 캐스팅 하는 **처리** 형식입니다.

> [!NOTE]
> 때 **stdin**를 **stdout**, 및 **stderr** 되지 스트림 (예를 들어 Windows 응용 프로그램을 콘솔 창이 없는)를 사용 하 여 연결 된 파일 설명자 값 반환 되는 이러한 스트림을 [_fileno](fileno.md) 특수도-2 값입니다. 마찬가지로, 파일 설명자에 대 한 호출의 결과가 아닌 매개 변수로 0, 1 또는 2를 사용 하는 경우 **_fileno**하십시오 **_get_osfhandle** 파일 설명자를 연결한 경우에 특수 값-2를 반환 합니다 스트림, 설정 하지 않습니다 **errno**합니다. 그러나이 유효한 파일 핸들 값을 되며 사용 하려고 하는 후속 호출은 실패할 수 있습니다.

에 대 한 자세한 내용은 **EBADF** 다른 오류 코드를 살펴보고 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.

## <a name="remarks"></a>설명

운영 체제 (OS) 파일 핸들이 여 가져온 파일을 닫으려면 **_get_osfhandle**를 호출 [_close](close.md) 파일 설명자에 *fd*합니다. 호출 하지 않습니다 **CloseHandle** 이 함수의 반환 값입니다. 기본 OS 파일 핸들이 소유 합니다 *fd* 설명자 파일과 면 연결이 닫힙니다 [_close](close.md) 라고 하 *fd*. 파일 설명자가 소유 하는 경우는 `FILE *` 호출한 스트림에 [fclose](fclose-fcloseall.md) 에 `FILE *` 스트림의 파일 설명자와 기본 OS 파일 핸들을 닫습니다. 이 경우 호출 하지 마세요 [_close](close.md) 파일 설명자에 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
