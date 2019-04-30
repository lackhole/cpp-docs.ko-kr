---
title: _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
ms.date: 11/04/2016
apiname:
- _wstat64
- _stati64
- _stat32
- _stat32i64
- _stat
- _wstati64
- _wstat32
- _wstat64i32
- _wstat
- _stat64
- _stat64i32
- _wstat32i64
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tstat32
- tstat
- _tstat64i32
- tstati64
- _wstat64
- _wstat32
- wstati64
- tstat64
- _stati64
- _wstat
- wstat64i32
- stat32i64
- tstat32i64
- _tstat
- _wstati64
- _tstati64
- _wstat32i64
- wstat32
- _wstat64i32
- _stat
- _tstat32
- stat64i32
- wstat64
- stat
- _stat32i64
- _stat32
- stati64
- wstat
- _stat64i32
- stat32
- _tstat32i64
- tstat64i32
- _tstat64
- _stat64
- stat/_stat
- stat/_stat32
- stat/_stat64
- stat/_stati64
- stat/_stat32i64
- stat/_stat64i32
- stat/_wstat
- stat/_wstat32
- stat/_wstat64
- stat/_wstati64
- stat/_wstat32i64
- stat/_wstat64i32
helpviewer_keywords:
- files [C++], status information
- _stat function
- _wstat function
- _stat64i32 function
- tstat function
- _tstat64i32 function
- _stati64 function
- _stat64 function
- tstati64 function
- wstati64 function
- wstat64 function
- _wstat64i32 function
- _tstat32i64 function
- _stat32i64 function
- stat function
- status of files
- _tstat32 function
- tstat64 function
- _wstat64 function
- _tstat function
- _stat32 function
- wstat function
- _wstat32i64 function
- _tstati64 function
- _wstat32 function
- stat64 function
- stati64 function
- _wstati64 function
- _tstat64 function
- files [C++], getting status information
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
ms.openlocfilehash: d9272cd4596a54a38e1ba21ac92b038c2da0d207
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354718"
---
# <a name="stat-stat32-stat64-stati64-stat32i64-stat64i32-wstat-wstat32-wstat64-wstati64-wstat32i64-wstat64i32"></a>_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32

파일의 상태 정보를 가져옵니다.

## <a name="syntax"></a>구문

```C
int _stat(
   const char *path,
   struct _stat *buffer
);
int _stat32(
   const char *path,
   struct __stat32 *buffer
);
int _stat64(
   const char *path,
   struct __stat64 *buffer
);
int _stati64(
   const char *path,
   struct _stati64 *buffer
);
int _stat32i64(
   const char *path,
   struct _stat32i64 *buffer
);
int _stat64i32(
   const char *path,
   struct _stat64i32 *buffer
);
int _wstat(
   const wchar_t *path,
   struct _stat *buffer
);
int _wstat32(
   const wchar_t *path,
   struct __stat32 *buffer
);
int _wstat64(
   const wchar_t *path,
   struct __stat64 *buffer
);
int _wstati64(
   const wchar_t *path,
   struct _stati64 *buffer
);
int _wstat32i64(
   const wchar_t *path,
   struct _stat32i64 *buffer
);
int _wstat64i32(
   const wchar_t *path,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>매개 변수

*path*<br/>
기존 파일 또는 디렉터리의 경로가 포함된 문자열에 대한 포인터입니다.

*buffer*<br/>
결과를 저장하는 구조에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

파일 상태 정보를 가져오는 경우 이러한 함수는 각각 0을 반환합니다. 반환 값이-1 경우 오류를 나타냅니다 **errno** 로 설정 된 **ENOENT**를 나타내는 파일 이름 또는 경로 찾을 수 없습니다. 반환 값 **EINVAL** ; 잘못 된 매개 변수를 나타냅니다 **errno** 로 설정 됩니다 **EINVAL** 이 경우.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 을 참조하세요.

사용 하지 않는 경우 전과 23시 59분: 59, 3000 년 12 월 31 일을 UTC로 1970 년 1 월 1 일 자정 보다 이후인 경우 파일의 날짜 스탬프가 나타낼 수 **_stat32** 하거나 **_wstat32**, 또는 정의 해 놓은 **_ USE_32BIT_TIME_T**, 이때 23시 59분: 59 2038 년 1 월 18 일 UTC 까지만 날짜를 나타낼 수 있습니다.

## <a name="remarks"></a>설명

**_stat** 함수에서 지정한 디렉터리나 파일에 대 한 정보를 가져오는 *경로* 가리키는 구조체에 저장 합니다 *버퍼*합니다. **_stat** 에서 현재 사용 중인 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 합니다. 필요에 따라 멀티 바이트 문자열 인수를 자동으로 처리 합니다.

**_wstat** 의 와이드 문자 버전이 **_stat**; *경로* 인수 **_wstat** 는 와이드 문자 문자열입니다. **_wstat** 하 고 **_stat** 점을 제외 하면 동일 하 게 작동 **_wstat** 멀티 바이트 문자열을 처리 하지 않습니다.

이러한 함수의 변형은 32비트 또는 64비트 시간 형식 및 32비트 또는 64비트 파일 길이를 지원합니다. 첫 번째 숫자 접미사 (**32** 또는 **64**)의 크기를 나타내는 형식에 사용 되는, 두 번째 접미사 **i32** 또는 **i64**, 32 비트 또는 64 비트 정수로 파일 크기를 나타낼지 여부를 나타내는입니다.

**_stat** 같습니다 **_stat64i32**, 및 **구조체** **_stat** 는 64 비트 시간을 포함 합니다. 이 경우가 아니면 **_USE_32BIT_TIME_T** 정의이 경우 이전 동작이 적용 됩니다 **_stat** 32 비트 시간을 사용 하 고 **구조체** **_stat** 는 32 비트 시간을 포함 합니다. 같은 기준이 **_stati64**합니다.

> [!NOTE]
> **_wstat** 기호화 된 링크 Windows Vista에서는 작동 하지 않습니다. 이러한 경우 **_wstat** 는 항상 보고서 파일 크기가 0입니다. **_stat** 기호화 된 링크를 사용 하 여 올바르게 작동 합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 이면 *경로* 또는 *버퍼* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

### <a name="time-type-and-file-length-type-variations-of-stat"></a>_stat의 시간 형식 및 파일 길이 형식 변형

|함수|_USE_32BIT_TIME_T 정의 여부|시간 형식|파일 길이 형식|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|정의되지 않음|64비트|32비트|
|**_stat**, **_wstat**|정의됨|32비트|32비트|
|**_stat32**, **_wstat32**|매크로 정의의 영향을 받지 않음|32비트|32비트|
|**_stat64**, **_wstat64**|매크로 정의의 영향을 받지 않음|64비트|64비트|
|**_stati64**, **_wstati64**|정의되지 않음|64비트|64비트|
|**_stati64**, **_wstati64**|정의됨|32비트|64비트|
|**_stat32i64**, **_wstat32i64**|매크로 정의의 영향을 받지 않음|32비트|64비트|
|**_stat64i32**, **_wstat64i32**|매크로 정의의 영향을 받지 않음|64비트|32비트|

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

합니다 **_stat** SYS\STAT에 정의 된 구조입니다. H, 다음 필드를 포함 합니다.

|필드||
|-|-|
| **st_gid** | 파일(UNIX 관련)을 소유하는 그룹의 숫자 식별자입니다. 이 필드는 Windows 시스템에서 항상 0입니다. 리디렉션된 파일은 Windows 파일로 분류됩니다. |
| **st_atime** | 파일의 마지막 액세스 시간입니다. NTFS에서는 유효하지만, FAT로 포맷한 디스크 드라이브에서는 유효하지 않습니다. |
| **st_ctime** | 파일 생성 시간입니다. NTFS에서는 유효하지만, FAT로 포맷한 디스크 드라이브에서는 유효하지 않습니다. |
| **st_dev** | 파일이 포함 된 디스크 드라이브 (동일 **st_rdev**). |
| **st_ino** | 정보 노드 수 (합니다 **inode**) 파일 (UNIX 관련)입니다. UNIX 파일 시스템에는 **inode** 파일 날짜 및 타임 스탬프, 권한 및 콘텐츠를 설명 합니다. 동일한 공유 파일이 서로 하드 링크 된 경우 **inode**합니다. 합니다 **inode**, 있어 **st_ino**, FAT, HPFS 또는 NTFS 파일 시스템에서 의미가 없습니다. |
| **st_mode** | 파일 모드 정보의 비트 마스크입니다. 합니다 **_S_IFDIR** 비트가 설정 됩니다 *경로* 디렉터리를 지정; **_S_IFREG** 비트가 설정 됩니다 *경로* 일반 파일 또는 장치를 지정 합니다. 파일의 사용 권한 모드에 따라 사용자 읽기/쓰기 비트가 설정됩니다. 파일 이름 확장명에 따라 사용자 실행 비트가 설정됩니다. |
| **st_mtime** | 파일의 마지막 수정 시간입니다. |
| **st_nlink** | NTFS가 아닌 파일 시스템에서 항상 1입니다. |
| **st_rdev** | 파일이 포함 된 디스크 드라이브 (동일 **st_dev**). |
| **st_size** | 크기 (바이트)의 파일 인 변형의 64 비트 정수를 합니다 **i64** 접미사. |
| **st_uid** | 파일(UNIX 관련)을 소유하는 사용자의 숫자 식별자입니다. 이 필드는 Windows 시스템에서 항상 0입니다. 리디렉션된 파일은 Windows 파일로 분류됩니다. |

하는 경우 *경로* 장치를 참조 합니다 **st_size**, 다양 한 시간 필드 **st_dev**, 및 **st_rdev** 필드를 **_stat**  구조는 의미가 없습니다. STAT.H가 TYPES.H에 정의된 [_dev_t](../../c-runtime-library/standard-types.md) 형식을 사용하기 때문입니다. 코드에서 STAT.H 앞에 TYPES.H를 포함해야 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**_stat**, **_stat32**, **_stat64**, **_stati64**, **_stat32i64**, **_stat64i32**|\<sys/types.h> 다음에 \<sys/stat.h>|\<errno.h>|
|**_wstat**, **_wstat32**, **_wstat64**, **_wstati64**, **_wstat32i64**, **_wstat64i32**|\<sys/types.h> 다음에 \<sys/stat.h> 또는 \<wchar.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_stat.c
// This program uses the _stat function to
// report information about the file named crt_stat.c.

#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
   struct _stat buf;
   int result;
   char timebuf[26];
   char* filename = "crt_stat.c";
   errno_t err;

   // Get data associated with "crt_stat.c":
   result = _stat( filename, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      perror( "Problem getting information" );
      switch (errno)
      {
         case ENOENT:
           printf("File %s not found.\n", filename);
           break;
         case EINVAL:
           printf("Invalid parameter to _stat.\n");
           break;
         default:
           /* Should never be reached. */
           printf("Unexpected error in _stat.\n");
      }
   }
   else
   {
      // Output some of the statistics:
      printf( "File size     : %ld\n", buf.st_size );
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid arguments to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
}
```

```Output
File size     : 732
Drive         : C:
Time modified : Thu Feb 07 14:39:36 2002
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_setmbcp](setmbcp.md)<br/>
