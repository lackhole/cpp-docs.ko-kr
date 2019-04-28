---
title: freopen, _wfreopen
ms.date: 11/04/2016
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
ms.openlocfilehash: 4c570837bddea1f5e986ae5f767279ab2637ea21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332990"
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen

파일 포인터를 다시 할당합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*path*<br/>
새 파일의 경로입니다.

*모드*<br/>
허용되는 액세스 형식입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

각 함수는 새로 열린 파일에 대한 포인터를 반환합니다. 오류가 발생 하 고, 원래 파일이 닫힙니다, 함수가 반환 하는 경우는 **NULL** 포인터 값입니다. 경우 *경로*를 *모드*, 또는 *stream* 가 null 포인터 이거나 *filename* 빈 문자열이 면 이러한 함수는 잘못 된 매개 변수를 호출 에 설명 된 대로 처리기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **NULL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

이러한 함수의 더 안전한 버전이 있습니다. [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md)를 참조하세요.

**freopen** 함수는 현재 연결 된 파일을 닫습니다 *스트림* 재지정 *stream* 로 지정 된 파일에 *경로*합니다. **_wfreopen** 의 와이드 문자 버전이 **_freopen**; *경로* 및 *모드* 인수 **_wfreopen** 됩니다 와이드 문자 문자열입니다. **_wfreopen** 하 고 **_freopen** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen** 는 일반적으로 리디렉션하는 데 미리 열린된 파일 **stdin**를 **stdout**, 및 **stderr** 사용자가 지정한 파일에 있습니다. 연관 된 새 파일 *스트림* 를 사용 하 여 열 *모드*는 같이 파일에 대해 요청 된 액세스 형식을 지정 하는 문자열입니다.

|*모드*|액세스|
|-|-|
| **"r"** | 읽기 위해 엽니다. 파일이 존재 하지 않거나 찾을 수 없는 경우는 **freopen** 호출이 실패 합니다. |
| **"w"** | 쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a"** | 새 데이터를 파일에 쓰기 전에 EOF(파일 끝) 표식을 제거하지 않고 파일의 끝에 쓰기(추가)하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다. |
| **"r+"** | 읽고 쓰기 위해 엽니다. 파일이 있어야 합니다. |
| **"w+"** | 읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다. |
| **"a+"** | 읽고 추가하기 위해 엽니다. 추가 작업에는 새 데이터를 파일에 쓰기 전에 EOF 표식을 제거하는 작업이 포함됩니다. 쓰기 완료 후 EOF 표식이 복원되지 않습니다. 파일이 없는 경우 파일을 만듭니다. |

사용 합니다 **"w"** 하 고 **"w +"** 기존 파일을 제거할 수 있으므로 신중 하 게 형식입니다.

사용 하 여 파일을 열면 합니다 **"a"** 또는 **"a +"** 액세스 형식을 모든 쓰기 작업이 파일 끝에 발생 합니다. 파일 포인터를 사용 하 여 변경 될 수 있지만 [fseek](fseek-fseeki64.md) 하거나 [rewind](rewind.md), 파일 포인터는 항상 다시 이동 파일의 끝에 쓰기 작업을 수행 하기 전에 합니다. 따라서 기존 데이터를 덮어쓸 수 없습니다.

합니다 **"a"** 모드 파일에 추가 하기 전에 EOF 표식을 제거 하지 않습니다. 추가 작업이 수행된 이후에는 MS-DOS TYPE 명령은 원래 EOF 표식까지만 데이터를 표시하고 파일에 추가된 데이터는 표시하지 않습니다. 합니다 **"a +"** 모드에서는 파일에 추가 하기 전에 EOF 표식을 제거 합니다. 추가 후에는 MS-DOS TYPE 명령으로 파일의 모든 데이터를 표시합니다. 합니다 **"a +"** 모드가 CTRL + Z EOF 표식으로 종료 되는 스트림 파일에 추가 해야 합니다.

경우는 **"r +"** 를 **"w +"**, 또는 **"a +"** 액세스 형식을 지정한 경우 읽기와 쓰기가 모두 허용 됩니다 (파일이 "업데이트"에 대해 열려야 하 라고 합니다). 그러나 읽기와 쓰기를 전환할 때는 먼저 [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) 또는 [rewind](rewind.md) 작업이 있어야 합니다. 에 대 한 현재 위치를 지정할 수 있습니다 합니다 [fsetpos](fsetpos.md) 하거나 [fseek](fseek-fseeki64.md) 작업을 원하는 경우. 위의 값 외에도 다음 문자 중 하나가 포함 될 수 있습니다 합니다 *모드* 새 줄에 대 한 변환 모드를 지정 하는 문자열입니다.

|*모드* 한정자|변환 모드|
|-|-|
| **t** | 텍스트(변환됨) 모드에서 엽니다. |
| **b** | 이진(변환되지 않음) 모드에서 엽니다. 캐리지 리턴 및 줄 바꿈 문자를 포함하는 변환은 표시되지 않습니다. |

텍스트 (변환 됨) 모드에서 캐리지 리턴-줄 바꿈 (CR-LF) 조합은 입력에서 단일 줄 바꿈 (LF) 문자로 변환 됩니다. LF 문자는 출력 시 CR-LF 조합으로 변환 됩니다. 또한 CTRL+Z는 입력 시 파일 끝 문자로 변환됩니다. 작성 하 고 사용 하 여 읽기 또는 읽기에 대 한 열려 있는 파일에서 **"a +"**, 런타임 라이브러리 파일의 끝에 CTRL + Z가 있는지 확인 하 고, 가능한 경우 제거 합니다. 사용 하 여 때문에 이렇게 [fseek](fseek-fseeki64.md) 하 고 [ftell](ftell-ftelli64.md) 파일 내에서 이동할 발생할 수 있습니다 [fseek](fseek-fseeki64.md) 파일 끝 가까이 제대로 동작 하려면. 합니다 **t** 옵션은 Microsoft 확장 이므로 ANSI 이식성이 필요한 곳 사용할 수 없습니다.

하는 경우 **t** 하거나 **b** 제공 되지 않습니다 *모드*, 기본 변환 모드는 전역 변수를 정의한 [_fmode](../../c-runtime-library/fmode.md)합니다. 하는 경우 **t** 하거나 **b** 맨 앞에 인수, 함수가 실패 하며 반환 **NULL**합니다.

텍스트 모드와 이진 모드에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 앱에서 지원 되지 않습니다. 콘솔을 사용 하 여 연결 된 표준 스트림 핸들 **stdin**하십시오 **stdout**, 및 **stderr**, C 런타임 함수 UWP 앱에서 사용할 수 있는 되기 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
