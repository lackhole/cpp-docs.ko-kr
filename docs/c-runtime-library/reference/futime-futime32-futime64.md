---
title: _futime, _futime32, _futime64
ms.date: 11/04/2016
api_name:
- _futime64
- _futime32
- _futime
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
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 3de638f08882e2aae4743311730afcd888c43a60
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956226"
---
# <a name="_futime-_futime32-_futime64"></a>_futime, _futime32, _futime64

열린 파일의 수정 시간을 설정합니다.

## <a name="syntax"></a>구문

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열린 파일에 대한 파일 설명자입니다.

*filetime*<br/>
새 수정 날짜를 포함하는 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

성공하면 0을 반환합니다. 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 해 서 실행 하도록 허용한 경우 함수는-1을 반환 하 고 **errno** 는 **ebadf**로 설정 되 고 잘못 된 파일 설명자를 나타내는 EINVAL 또는 잘못 된 매개 변수를 나타내는로 설정 됩니다.

## <a name="remarks"></a>설명

**_Futime** 루틴은 *fd*와 연결 된 열린 파일의 수정 날짜 및 액세스 시간을 설정 합니다. **_futime** 는 해당 인수가 파일의 이름이 나 파일의 경로가 아니라 열린 파일의 파일 설명자 인 경우를 제외 하 고 [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)과 동일 합니다. **_Ustststd** 구조체에는 새 수정 날짜 및 액세스 시간에 대 한 필드가 포함 됩니다. 두 필드 모두 유효한 값을 포함합니다. **_utimbuf32** 및 **_utimbuf64** 는 각각 32 비트 및 64 비트 시간 형식을 사용 하는 경우를 제외 하 고 **_usttbuf** 와 동일 합니다. **_futime** 및 **_utimbuf** 는 64 비트 시간 형식을 사용 하 고 **_futime** 는 **_futime64**에 대 한 동작과 동일 합니다. 이전 동작을 강제로 수행 해야 하는 경우 **_USE_32BIT_TIME_T**를 정의 합니다. 이렇게 하면 **_futime** 가 **_futime32** 에 대해 동일 하 게 작동 하 고 **_uststumstructure** 가 32 비트 시간 형식을 사용 하 여 **__utimbuf32**와 동일 하 게 만듭니다.

**__utimbuf64** 구조를 사용 하는 **_Futime64**는 23:59:59 년 12 월 31 일 3000 년 12 월 31 일까 지 파일 날짜를 읽고 수정할 수 있습니다. **_futime32** 에 대 한 호출은 파일의 날짜가 2038 년 1 월 18 일 23:59:59 보다 늦은 경우 실패 합니다. 1970년 1월 1일 자정은 이러한 함수에 대한 날짜 범위의 하한입니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|선택적 헤더|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crt_futimec_input"></a>입력: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>샘플 출력

```Output
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
