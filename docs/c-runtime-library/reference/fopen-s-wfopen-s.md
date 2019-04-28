---
title: fopen_s, _wfopen_s
ms.date: 11/04/2016
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 1309f991b8251bde7d614aa274d8d2e9da7a8ed3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333328"
---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s

파일을 엽니다. 이러한 버전의 [fopen, _wfopen](fopen-wfopen.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
열린 파일에 대한 포인터를 수신할 파일 포인터에 대한 포인터입니다.

*filename*<br/>
파일 이름입니다.

*모드*<br/>
허용되는 액세스 형식입니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다. 이러한 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*pFile*|*filename*|*모드*|반환 값|내용을 *pFile*|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|any|any|**EINVAL**|변경 안 됨|
|any|**NULL**|any|**EINVAL**|변경 안 됨|
|any|any|**NULL**|**EINVAL**|변경 안 됨|

## <a name="remarks"></a>설명

파일에서 열리는 **fopen_s** 하 고 **_wfopen_s** 공유할 수 없는 합니다. 파일을 공유할 수는 필요한 경우 사용 하 여 [_fsopen, _wfsopen](fsopen-wfsopen.md) 적절 한 공유 모드 상수와-예를 들어 **_SH_DENYNO** 읽기/쓰기 공유 합니다.

합니다 **fopen_s** 함수에 지정 된 파일을 엽니다 *filename*합니다. **_wfopen_s** 의 와이드 문자 버전이 **fopen_s**;에 대 한 인수 **_wfopen_s** 는 와이드 문자 문자열입니다. **_wfopen_s** 하 고 **fopen_s** 동일 하 게 작동 합니다.

**fopen_s** 실행 시점에 파일 시스템에 유효한 경로 허용 합니다. 매핑된 네트워크 드라이브를 포함 하는 경로 및 UNC 경로 허용할 **fopen_s** 시스템 코드를 실행 하는 공유에 대 한 액세스 권한이 있거나 매핑된 네트워크 드라이브는 실행 시간입니다. 에 대 한 경로 생성할 때 **fopen_s**실행 환경에서 네트워크 공유, 드라이브, 경로, 가용성에 대 한 가정을 확인 하지 않습니다. 슬래시(/) 또는 백슬래시(\\)를 경로의 디렉터리 구분 기호로 사용할 수 있습니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 하는 경우 *pFile*를 *filename*, 또는 *모드* 가 null 포인터인 경우 이러한 함수에 설명 된 대로 잘못 된 매개 변수 예외를 생성할 [매개 변수 유효성 검사 ](../../c-runtime-library/parameter-validation.md).

파일에서 다른 작업을 수행하기 전에 항상 반환 값을 검사하여 함수가 성공했는지를 확인하세요. 오류가 발생 하는 경우 오류 코드가 반환 됩니다 및 전역 변수 **errno** 설정 됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="unicode-support"></a>유니코드 지원

**fopen_s** 은 유니코드 파일 스트림을 지원 합니다. 새 또는 기존 유니코드 파일을 열려면 전달 된 *ccs* 원하는 인코딩을 지정 하는 플래그 **fopen_s**:

**fopen_s(&fp, "newfile.txt", "rw, ccs=**_encoding_**");**

값이 허용 *인코딩* 됩니다 **유니코드**를 **u t F-8**, 및 **u t F-16LE**합니다. 에 대 한 지정 된 값 있는 경우 *인코딩*를 **fopen_s** ANSI 인코딩을 사용 합니다.

파일이 이미 있고 읽기 또는 추가용으로 열려 있는 경우 BOM(바이트 순서 표시)(파일에 있는 경우)에 따라 인코딩이 결정됩니다. BOM 인코딩이 우선 인코딩을 통해 지정 된 된 *ccs* 플래그입니다. 합니다 *ccs* 인코딩은 BOM이 없거나 파일이 새 파일을 인지 하는 경우 사용만 됩니다.

> [!NOTE]
> BOM 검색 유니코드 모드로 열려 있는 파일에만 적용 됩니다. 즉, 전달 하는 *ccs* 플래그입니다.

다음 표에서 다양 한 모드를 간단히 설명 *ccs* 에 지정 된 플래그 **fopen_s** 및 파일에 바이트 순서 표시 합니다.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs 플래그 및 BOM을 기반으로 사용되는 인코딩

|ccs 플래그|BOM이 없거나 새 파일|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

유니코드 모드에서 쓰도록 파일을 열면 BOM이 파일에 자동으로 기록됩니다.

하는 경우 *모드* 됩니다 **"을 ccs =**_인코딩_**"** 를 **fopen_s** 먼저 읽기를 사용 하 여 파일을 열려고 시도 액세스 및 쓰기 액세스 합니다. 성공하면 함수가 BOM을 읽어서 파일에 대한 인코딩을 결정하고, 실패하면 함수가 파일에 대한 기본 인코딩을 사용합니다. 두 경우 모두 **fopen_s** 쓰기 전용 액세스를 사용 하 여 해당 파일을 다시 엽니다. (이에 적용 됩니다 **는** 모드 에서만 not **+**.)

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

문자열 *모드* 다음과 같이 파일에 대해 요청 되는 액세스의 종류를 지정 합니다.

|*모드*|액세스|
|-|-|
| **"r"** | 읽기 위해 엽니다. 파일이 존재 하지 않거나 찾을 수 없는 경우는 **fopen_s** 호출이 실패 합니다. |
| **"w"** | 쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a"** | 새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다. |
| **"r+"** | 읽고 쓰기 위해 엽니다. 파일이 있어야 합니다. |
| **"w+"** | 읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a+"** | 읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다. |

사용 하 여 파일을 열면 합니다 **"a"** 또는 **"a +"** 액세스 형식을 모든 쓰기 작업이 파일 끝에 발생 합니다. 사용 하 여 파일 포인터 위치를 변경할 수 [fseek](fseek-fseeki64.md) 또는 [rewind](rewind.md), 하지만는 항상 파일의 끝에 쓰기 전에 다시 이동 모든 기존 데이터를 덮어쓸 수 없습니다 있도록 작업을 수행 합니다.

합니다 **"a"** 모드 파일에 추가 하기 전에 EOF 표식을 제거 하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. 합니다 **"a +"** 모드에서는 파일에 추가 하기 전에 EOF 표식을 제거 합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. 합니다 **"a +"** 모드가 CTRL + Z EOF 표식을 사용 하 여 종료 되는 스트림 파일에 추가 해야 합니다.

경우는 **"r +"** 를 **"w +"**, 또는 **"a +"** 액세스 형식을 지정한 경우 읽기와 쓰기가 모두 허용 됩니다. 즉, 파일이 "업데이트"용으로 열립니다. 하지만 읽기에서 쓰기로 전환할 경우 입력 작업 시 EOF 표식이 필요합니다. EOF가 없는 경우 사이에 파일 위치 지정 함수를 호출해야 합니다. 파일 위치 지정 함수를 사용 하는 **fsetpos**하십시오 [fseek](fseek-fseeki64.md), 및 [rewind](rewind.md)합니다. 쓰기에서 읽기로 전환 하면 대 한 중간 호출을 사용 해야 합니다 **fflush** 또는 파일 위치 지정 함수입니다.

위의 값 외에도 문자가 포함 될 수 있습니다 *모드* 줄 바꿈 문자에 대 한 변환 모드를 지정 하려면:

|*모드* 한정자|변환 모드|
|-|-|
| **t** | 텍스트(변환됨) 모드에서 엽니다. |
| **b** | 이진(변환되지 않음) 모드에서 엽니다. 캐리지 리턴 및 줄 바꿈 문자를 포함하는 변환은 표시되지 않습니다. |

텍스트 (변환 됨) 모드에서 CTRL + Z는 입력 시 파일 끝 문자로 해석 됩니다. 읽기/쓰기용으로 열려 있는 파일의 **"a +"** 를 **fopen_s** 파일의 끝에 CTRL + Z가 있는지 확인 하 고, 가능한 경우 제거 합니다. 사용 때문에 이렇게 [fseek](fseek-fseeki64.md) 하 고 **ftell** 는 CTRL + Z로 끝나는 파일 내에서 이동할 [fseek](fseek-fseeki64.md) 파일 끝 가까이 제대로 동작 하려면.

또한 텍스트 모드에서 캐리지 리턴-줄 바꿈 조합은 입력 시 단일 줄 바꿈으로 변환 되 고 줄 바꿈 문자는 출력에서 캐리지 리턴-줄 바꿈 조합으로 변환 됩니다. 유니코드 스트림 I/O 함수가 텍스트 모드에서 작동할 경우(기본값) 소스 또는 대상 스트림은 멀티바이트 문자 시퀀스로 간주됩니다. 따라서 유니코드 스트림 입력 함수는 **mbtowc** 함수 호출과 마찬가지로 멀티바이트 문자를 와이드 문자로 변환합니다. 동일한 이유로 유니코드 스트림 출력 함수는 **wctomb** 함수 호출과 마찬가지로 와이드 문자를 멀티바이트 문자로 변환합니다.

하는 경우 **t** 하거나 **b** 제공 되지 않습니다 *모드*, 기본 변환 모드는 전역 변수를 정의한 [_fmode](../../c-runtime-library/fmode.md)합니다. 하는 경우 **t** 하거나 **b** 맨 앞에 인수, 함수가 실패 하며 반환 **NULL**합니다.

텍스트 및 이진 모드를 유니코드 및 멀티바이트 스트림 I/O에서 사용하는 방법에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [텍스트 및 이진 모드의 유니코드 스트림 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)를 참조하세요.

|*모드* 한정자|동작|
|-|-|
| **c** | 연결 된 커밋 플래그를 사용 *filename* 파일 버퍼의 내용을 디스크에 직접 기록 되도록 **fflush** 하거나 **_flushall** 라고 합니다. |
| **n** | 연결 된 커밋 플래그를 재설정 *filename* "커밋 안 함."를 이 값이 기본값입니다. 또한 프로그램을 COMMODE.OBJ와 연결할 경우 전역 커밋 플래그를 재정의합니다. 프로그램을 COMMODE.OBJ와 명시적으로 연결하지 않을 경우 전역 커밋 플래그 기본값은 "커밋 안 함"입니다( [Link Options](../../c-runtime-library/link-options.md)참조). |
| **N** | 자식 프로세스에서 파일을 상속하지 않도록 지정합니다. |
| **S** | 캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다. |
| **R** | 캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다. |
| **T** | 파일을 임시 파일로 지정합니다. 가능하면 디스크에 플러시되지 않습니다. |
| **D** | 파일을 임시 파일로 지정합니다. 마지막 파일 포인터를 닫을 때 삭제됩니다. |
| **ccs=**_encoding_ | 사용 하도록 설정 하는 인코딩된 문자를 지정 합니다 (중 하나 **u t F-8**를 **u t F-16LE**, 또는 **유니코드**)이이 파일에 대 한 합니다. ANSI 인코딩을 원할 경우 지정되지 않은 상태로 둡니다. |

에 유효한 문자는 *모드* 에서 사용 되는 문자열 **fopen_s** 하 고 [_fdopen](fdopen-wfdopen.md) 에 해당 하 *oflag* 에서 사용 되는 인수 [_ 엽니다](open-wopen.md) 하 고 [_sopen](sopen-wsopen.md)다음과 같이 합니다.

|문자 *모드* 문자열|동등한 *oflag* 열기 (_o) / _sopen 값|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_APPEND**)|
|**a+**|**_O_RDWR** &#124; **_O_APPEND** (usually **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r+**|**_O_RDWR**|
|**w**|**_O_WRONLY** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC**)|
|**w+**|**_O_RDWR** (usually **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**c**|없음|
|**n**|없음|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs=UNICODE**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**ccs=UTF-16LE**|**_O_UTF16**|

사용 중인 경우 **rb** 모드는 많은 파일을 읽어야 하 고 코드 포트 하지 않아도 네트워크 성능에 신경, 메모리 매핑된 Win32 파일을 옵션으로 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

합니다 **c**를 **n**, 및 **t** *모드* 옵션에 대 한 Microsoft 확장은 **fopen_s** 및[_fdopen](fdopen-wfdopen.md) ANSI 이식성이 필요한 곳 사용할 수 없습니다.

## <a name="example"></a>예제

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it is not NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
