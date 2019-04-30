---
title: _creat, _wcreat
ms.date: 11/04/2016
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
ms.openlocfilehash: 901a95a6a9361f95f38749dacf1a5001d97b3761
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335310"
---
# <a name="creat-wcreat"></a>_creat, _wcreat

새 파일을 만듭니다. **_creat** 하 고 **_wcreat** 사용 되지 않으면 사용 [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) 대신 합니다.

## <a name="syntax"></a>구문

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
새 파일의 이름입니다.

*pmode*<br/>
권한 설정

## <a name="return-value"></a>반환 값

이러한 함수는 성공하는 경우 생성된 파일에 파일 설명자를 반환합니다. 함수는-1을 반환 하는 고, 그렇지 설정 **errno** 다음 표에 나와 있는 것 처럼 합니다.

|**errno** 설정|설명|
|---------------------|-----------------|
|**EACCES**|*filename* 기존 읽기 전용 파일을 지정 하거나 파일 대신 디렉터리를 지정 합니다.|
|**EMFILE**|사용 가능한 추가 파일 설명자가 없습니다.|
|**ENOENT**|지정된 파일을 찾을 수 없습니다.|

하는 경우 *filename* 됩니다 **NULL**의 설명 대로 잘못 된 매개 변수 처리기를 호출 하는 이러한 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 고-1을 반환 합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

합니다 **_creat** 함수 열립니다 및 기존 자릅니다 새 파일을 만듭니다. **_wcreat** 의 와이드 문자 버전이 **_creat**; *filename* 인수를 **_wcreat** 는 와이드 문자 문자열입니다. **_wcreat** 하 고 **_creat** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

파일을 지정 하 여 *filename* 존재 하지 않는 새 파일을 지정 된 권한 설정을 사용 하 여 만들어지고 작성할 수 있도록 열립니다. 파일이 이미 존재 하 고 해당 권한 설정 쓰기를 허용 하면 **_creat** 이전 내용을 제거 하는 길이가 0 인 파일을 자릅니다 및 쓰기 위해 엽니다. 권한 설정 *pmode*, 새로 만든된 파일에만 적용 됩니다. 새 파일은 처음으로 닫힌 이후 지정된 권한 설정을 받습니다. 정수 식 *pmode* 매니페스트 상수 중 하나 또는 모두 포함 **_S_IWRITE** 하 고 **_S_IREAD**SYS\Stat.h에 정의 된 합니다. 두 상수가 지정 된 비트를 사용 하 여 결합 됩니다 or 연산자 ( **&#124;** ). 합니다 *pmode* 매개 변수는 다음 값 중 하나로 설정 됩니다.

|값|정의|
|-----------|----------------|
|**_S_IWRITE**|쓰기를 허용합니다.|
|**_S_IREAD**|읽기를 허용합니다.|
|**_S_IREAD** &#124; **_S_IWRITE**|읽기 및 쓰기를 허용합니다.|

쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. 모든 파일을 항상 읽을 수 있으므로 쓰기 전용 권한을 부여할 수 없습니다. 모드 **_S_IWRITE** 하 고 **_S_IREAD** | **_S_IWRITE** 동일 합니다. 파일을 사용 하 여 연 **_creat** 는 항상 호환 모드로 열립니다 (참조 [_sopen](sopen-wsopen.md))와 **_SH_DENYNO**합니다.

**_creat** 현재 파일 권한 마스크를 적용 *pmode* 사용 권한을 설정 하기 전에 (참조 [_umask](umask.md)). **_creat** 주로 이전 라이브러리와의 호환성을 위해 제공 됩니다. 에 대 한 호출 **_open** 사용 하 여 **_O_CREAT** 및 **_O_TRUNC** 에 *oflag* 매개 변수는 **_creat**는 새 코드에 대 한 것이 좋습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> 또는 \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
