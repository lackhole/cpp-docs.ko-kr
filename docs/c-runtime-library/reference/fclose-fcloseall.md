---
title: fclose, _fcloseall
ms.date: 11/04/2016
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 4713ffb7ecdf8da73e5f949bbef7be124dfaf28a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334881"
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall

스트림을 닫습니다 (**fclose**) 또는 모든 열린 스트림을 닫습니다 (**_fcloseall**).

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

**fclose** 스트림에 성공적으로 종료 하는 경우 0을 반환 합니다. **_fcloseall** 닫힌 스트림의 총 수를 반환 합니다. 두 함수 모두 반환 **EOF** 는 오류를 나타냅니다.

## <a name="remarks"></a>설명

합니다 **fclose** 닫히는 함수 *스트림*합니다. 하는 경우 *스트림을* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **fclose** 설정 **errno** 하 **EINVAL** 반환 **EOF**합니다. 것이 좋습니다 합니다 *스트림을* 포인터가이 함수를 호출 하기 전에 항상 확인 합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

합니다 **_fcloseall** 함수를 제외 하 고 모든 열린 스트림을 닫습니다 **stdin**를 **stdout**를 **stderr** (및 MS-DOS **_stdaux**  하 고 **_stdprn**). 또한 닫히고 하 여 만들어진 모든 임시 파일을 삭제 **tmpfile**합니다. 두 함수에서 모두 스트림과 연결된 모든 버퍼가 플러시된 후 닫힙니다. 시스템 할당 버퍼는 스트림이 닫힐 때 해제됩니다. 사용 하 여 사용자가 할당 한 버퍼 **setbuf** 하 고 **setvbuf** 자동으로 해제 되지 않습니다.

**참고:** 이러한 함수는 스트림 사용 하는 경우의 기본 파일 설명자와 OS 파일 핸들 (또는 소켓) 닫혀 스트림도 있습니다. 따라서 파일을 처음 연 경우 파일을 처리할 파일 설명자 및 사용 하 여 닫혀 **fclose**, 하지 마세요. 또한 호출 **_close** 에 파일 설명자를 닫기; Win32 함수를 호출 하지 마십시오  **CloseHandle** 파일 핸들을 닫습니다.

**fclose** 하 고 **_fcloseall** 다른 스레드의 간섭 으로부터 보호 하기 위해 코드를 포함 합니다. 잠기지 않은 버전의 **fclose**를 참조 하세요 **_fclose_nolock**합니다.

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
