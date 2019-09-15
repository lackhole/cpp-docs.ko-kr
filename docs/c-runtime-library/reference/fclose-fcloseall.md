---
title: fclose, _fcloseall
ms.date: 11/04/2016
api_name:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 215925fb16f5d51e481ae92cbb45b0270bd5ebd4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941498"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

스트림을 닫거나 (**fclose**) 열려 있는 모든 스트림 ( **_fcloseall**)을 닫습니다.

## <a name="syntax"></a>구문

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>매개 변수

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

스트림이 성공적으로 닫히면 **fclose** 는 0을 반환 합니다. **_fcloseall** 은 닫힌 스트림의 총 수를 반환 합니다. 두 함수는 모두 **EOF** 를 반환 하 여 오류를 표시 합니다.

## <a name="remarks"></a>설명

**Fclose** 함수는 *스트림을*닫습니다. *Stream* 이 **NULL**인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우 **fclose** 가 **errno** 를 **EINVAL** 로 설정 하 고 **EOF**를 반환 합니다. 이 함수를 호출 하기 전에 항상 *스트림* 포인터를 확인 하는 것이 좋습니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

**_Fcloseall** 함수는 **stdin**, **stdout**, **stderr** (그리고 MS-DOS, **_stdaux** 및 **_stdprn**)를 제외 하 고 열려 있는 모든 스트림을 닫습니다. 또한 **tmpfile**에서 만든 임시 파일도 닫고 삭제 합니다. 두 함수에서 모두 스트림과 연결된 모든 버퍼가 플러시된 후 닫힙니다. 시스템 할당 버퍼는 스트림이 닫힐 때 해제됩니다. **Setbuf** 와 **setvbuf** 를 사용 하 여 사용자가 할당 한 버퍼는 자동으로 해제 되지 않습니다.

**참고:** 이러한 함수를 사용 하 여 스트림을 닫으면 기본 파일 설명자 및 OS 파일 핸들 (또는 소켓)이 닫히고 stream도 닫힙니다. 따라서 파일이 원래 파일 핸들 또는 파일 설명자로 열리고 **fclose**를 사용 하 여 닫히면 **_ 닫기** 를 호출 하 여 파일 설명자를 닫아야 합니다. Win32 함수 **CloseHandle** 을 호출 하 여 파일 핸들을 닫아야 합니다.

**fclose** 및 **_fcloseall** 은 다른 스레드의 간섭 으로부터 보호 하는 코드를 포함 합니다. 비 잠금 버전의 **fclose**는 **_fclose_nolock**을 참조 하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fopen](fopen-wfopen.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
