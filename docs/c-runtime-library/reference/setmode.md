---
title: _setmode
ms.date: 11/04/2016
apiname:
- _setmode
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
- _setmode
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
ms.openlocfilehash: 67cca27ba03a99d7e192d438a98f1bb3a93845ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356402"
---
# <a name="setmode"></a>_setmode

파일 변환 모드를 설정합니다.

## <a name="syntax"></a>구문

```C
int _setmode (
   int fd,
   int mode
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
파일 설명자입니다.

*모드*<br/>
새 변환 모드입니다.

## <a name="return-value"></a>반환 값

성공하면 이전 변환 모드를 반환합니다.

함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행이 함수는-1 반환 하 고 집합을 계속 하도록 허용 된 경우 **errno** 하나로 **EBADF**, 잘못 된 파일 설명자를 나타내는 또는 **EINVAL**는 잘못 된 나타냅니다 *모드* 인수입니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

합니다 **_setmode** 함수를 설정 *모드* 제공한 파일의 변환 모드 *fd*합니다. 전달 **_O_TEXT** 으로 *모드* 설정 텍스트 (즉, 변환 됨) 모드입니다. 캐리지 리턴-줄 바꿈된 (CR-LF) 조합은 단일 줄 바꿈 문자 입력 시로 변환 됩니다. 줄 바꿈 문자는 출력 시 CR-LF 조합으로 변환됩니다. 전달 **_O_BINARY** 집합 이진 (변환 되지 않음된) 모드는 이러한 변환은 표시 되지 않습니다.

전달할 수도 있습니다 **_O_U16TEXT**를 **_O_U8TEXT**, 또는 **_O_WTEXT** 이 문서의 뒷부분에서 두 번째 예제에서 설명한 것 처럼 유니코드 모드를 사용 하도록 설정 합니다.

> [!CAUTION]
> 유니코드 모드 와이드 인쇄 기능입니다 (예를 들어 `wprintf`) 좁은 인쇄 기능에 대 한 지원 되지 않습니다. 유니코드 모드 스트림에 좁은 print 함수가 사용 assert를 트리거합니다.

**_setmode** 의 기본 변환 모드를 수정 하려면 일반적으로 사용 됩니다 **stdin** 하 고 **stdout**, 하지만 모든 파일에 사용할 수 있습니다. 적용 하는 경우 **_setmode** 스트림에 대 한 파일 설명자 인 호출 **_setmode** 스트림에서 입력 또는 출력 작업을 수행 하기 전에 합니다.

> [!CAUTION]
> 쓰는 경우 데이터 파일 스트림 플러시 명시적으로 코드를 사용 하 여 [fflush](fflush.md) 사용 하기 전에 **_setmode** 모드를 변경 합니다. 코드를 플러시하지 않은 경우 예기치 않은 동작이 발생할 수 있습니다. 스트림에 데이터를 쓰지 않을 경우 코드를 플러시할 필요가 없습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**_setmode**|\<io.h>|\<fcntl.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_setmode.c
// This program uses _setmode to change
// stdin from text mode to binary mode.

#include <stdio.h>
#include <fcntl.h>
#include <io.h>

int main( void )
{
   int result;

   // Set "stdin" to have binary mode:
   result = _setmode( _fileno( stdin ), _O_BINARY );
   if( result == -1 )
      perror( "Cannot set mode" );
   else
      printf( "'stdin' successfully changed to binary mode\n" );
}
```

```Output
'stdin' successfully changed to binary mode
```

## <a name="example"></a>예제

```C
// crt_setmodeunicode.c
// This program uses _setmode to change
// stdout to Unicode. Cyrillic and Ideographic
// characters will appear on the console (if
// your console font supports those character sets).

#include <fcntl.h>
#include <io.h>
#include <stdio.h>

int main(void) {
    _setmode(_fileno(stdout), _O_U16TEXT);
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");
    return 0;
}
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_set_fmode](set-fmode.md)<br/>
