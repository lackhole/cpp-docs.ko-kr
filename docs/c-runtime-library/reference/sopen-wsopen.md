---
title: _sopen, _wsopen
ms.date: 11/04/2016
apiname:
- _sopen
- _wsopen
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
- _wsopen
- wsopen
- _sopen
- _tsopen
helpviewer_keywords:
- sopen function
- sharing files
- opening files, for sharing
- _sopen function
- wsopen function
- files [C++], opening
- files [C++], sharing
- _wsopen function
ms.assetid: a9d4cccf-06e9-414d-96fa-453fca88cc1f
ms.openlocfilehash: b3773550fd32df75f0a3819767de1171daebaf0f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355395"
---
# <a name="sopen-wsopen"></a>_sopen, _wsopen

공유할 파일을 엽니다. 이러한 함수의 더 안전한 버전을 사용할 수: 참조 [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md)합니다.

## <a name="syntax"></a>구문

```C
int _sopen(
   const char *filename,
   int oflag,
   int shflag [,
   int pmode ]
);
int _wsopen(
   const wchar_t *filename,
   int oflag,
   int shflag [,
   int pmode ]
);
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
파일 이름.

*oflag*<br/>
허용되는 연산의 종류

*shflag*<br/>
허용되는 공유의 종류

*pmode*<br/>
권한 설정

## <a name="return-value"></a>반환 값

이러한 각 함수는 열린 파일에 대한 파일 설명자를 반환합니다.

경우 *filename* 또는 *oflag* 됩니다는 **NULL** 포인터 이거나 *oflag* 또는 *shflag* 유효한 내에 있지 않습니다 범위 값을 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수가-1를 반환 하는 설정 **errno** 에 다음 값 중 하나입니다.

|errno 값|조건|
|-|-|
| **EACCES** | 지정된 경로가 디렉터리거나 파일이 읽기 전용인데 쓰기 위한 열기 작업을 시도했습니다. |
| **EEXIST** | **_O_CREAT** 하 고 **_O_EXCL** 플래그를 지정 하지만 *filename* 이미 있습니다. |
| **EINVAL** | 잘못 된 *oflag* 하거나 *shflag* 인수입니다. |
| **EMFILE** | 사용 가능한 추가 파일 설명자가 없습니다. |
| **ENOENT** | 파일 또는 경로를 찾을 수 없습니다. |

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

**_sopen** 함수에서 지정한 파일을 열고 *filename* 정의한 대로 공유 읽기 또는 쓰기를 위해 해당 파일을 준비 하 고 *oflag* 고 *shflag* . **_wsopen** 의 와이드 문자 버전이 **_sopen**; *filename* 인수를 **_wsopen** 는 와이드 문자 문자열입니다. **_wsopen** 하 고 **_sopen** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

정수 식 *oflag* 에 정의 된 다음 매니페스트 상수 중 한 개 이상을 결합 하 여 형성 됩니다 \<t l. h >입니다. 두 개 이상의 상수 인수를 형성 하는 경우 *oflag*에 비트 OR 연산자와 결합 됩니다 ( **&#124;** ).

|*oflag* constant|동작|
|-|-|
| **_O_APPEND** | 모든 쓰기 작업 전에 파일 끝으로 파일 포인터를 이동합니다. |
| **_O_BINARY** | 파일을 이진(변환되지 않음) 모드에서 엽니다. 이진 모드에 대한 설명은 [fopen](fopen-wfopen.md)을 참조하세요. |
| **_O_CREAT** | 파일을 만든 다음 쓰기 위해 엽니다. 파일을 지정 하면 아무 효과가 *filename* 존재 합니다. 합니다 *pmode* 인수는 필수 **_O_CREAT** 지정 됩니다. |
| **_O_CREAT** &#124; **_O_SHORT_LIVED** | 파일을 임시로 만든 다음 가능한 경우 디스크로 플러시하지 않습니다. 합니다 *pmode* 인수는 필수 **_O_CREAT** 지정 됩니다. |
| **_O_CREAT** &#124; **_O_TEMPORARY** | 파일을 임시로 만듭니다. 마지막 파일 설명자가 닫히면 파일이 삭제됩니다. 합니다 *pmode* 인수는 필수 **_O_CREAT** 지정 됩니다. |
| **_O_CREAT** &#124; ` _O_EXCL` | 지정 된 파일이 있으면 오류 값을 반환 *filename* 존재 합니다. 사용 하는 경우에 적용 됩니다 **_O_CREAT**합니다. |
| **_O_NOINHERIT** | 공유 파일 설명자의 생성을 방지합니다. |
| **_O_RANDOM** | 캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다. |
| **_O_RDONLY** | 읽으려는 경우에만 파일을 엽니다. 사용 하 여 지정할 수 없습니다 **_O_RDWR** 하거나 **_O_WRONLY**합니다. |
| **_O_RDWR** | 읽고 쓰기 위해 파일을 엽니다. 사용 하 여 지정할 수 없습니다 **_O_RDONLY** 하거나 **_O_WRONLY**합니다. |
| **_O_SEQUENTIAL** | 캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다. |
| **_O_TEXT** | 파일을 텍스트(변환됨) 모드에서 엽니다. 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [fopen](fopen-wfopen.md)을 참조하세요. |
| **_O_TRUNC** | 파일을 열고 길이가 0이 되도록 자릅니다. 이 파일에는 쓰기 권한이 있어야 합니다. 사용 하 여 지정할 수 없습니다 **_O_RDONLY**합니다. **_O_TRUNC** 사용한 **_O_CREAT** 기존 파일을 열거나 파일을 만듭니다. **참고:** 합니다 **_O_TRUNC** 플래그 지정된 된 파일의 내용을 제거 합니다. |
| **_O_WRONLY** | 쓰려는 경우에만 파일을 엽니다. 사용 하 여 지정할 수 없습니다 **_O_RDONLY** 하거나 **_O_RDWR**합니다. |
| **_O_U16TEXT** | 유니코드 UTF-16 모드에서 파일을 엽니다. |
| **_O_U8TEXT** | 유니코드 UTF-8 모드에서 파일을 엽니다. |
| **_O_WTEXT** | 유니코드 모드에서 파일을 엽니다. |

파일 액세스 모드를 지정 하려면 지정 해야 **_O_RDONLY**하십시오 **_O_RDWR**, 또는 **_O_WRONLY**합니다. 액세스 모드의 기본값은 없습니다.

사용 하 여 파일을 유니코드 모드에서 열 때 **_O_WTEXT**를 **_O_U8TEXT**, 또는 **_O_U16TEXT**입력 함수는 utf-16 데이터 파일에서 읽은 데이터를 변환 형식으로 저장 **wchar_t**합니다. 유니코드 모드에서 연 파일에 쓰는 함수는 형식으로 저장 하는 utf-16 데이터가 포함 된 버퍼를 예상 **wchar_t**합니다. 이 파일이 UTF-8로 인코딩되면 UTF-16 데이터는 쓸 때 UTF-8로 변환되고 이 파일의 UTF-8로 인코딩된 내용은 읽을 때 UTF-16으로 변환됩니다. 유니코드 모드에서 홀수 바이트를 읽거나 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다. 프로그램에 UTF-8로 저장된 데이터를 읽거나 쓰려는 경우 유니코드 모드 대신 텍스트 또는 이진 파일 모드를 사용합니다. 필수 인코딩은 사용자가 변환해야 합니다.

하는 경우 **_sopen** 사용 하 여 라고 **_O_WRONLY** | **_O_APPEND** (추가 모드) 및 **_O_WTEXT**, **_O_ U16TEXT**, 또는 **_O_U8TEXT**쓰려는 경우에 다시 차례로 BOM을 읽은 먼저 읽고 쓰기에 대 한 파일을 열려고 시도 합니다. 읽고 쓰기 위해 파일을 여는데 실패하면 쓰기 위해서만 파일을 열고 유니코드 모드 설정에 기본값을 사용합니다.

인수 *shflag* 에 정의 된 다음 매니페스트 상수 중 하나로 구성 된 상수 식 \<share.h >.

|*shflag* constant|동작|
|-|-|
| **_SH_DENYRW** | 파일에 대한 읽기 및 쓰기 액세스를 거부합니다. |
| **_SH_DENYWR** | 파일에 대한 쓰기 액세스를 거부합니다. |
| **_SH_DENYRD** | 파일에 대한 읽기 액세스를 거부합니다. |
| **_SH_DENYNO** | 읽기 및 쓰기 액세스 권한을 허용합니다. |

합니다 *pmode* 인수가 필요한 경우에만 **_O_CREAT** 지정 됩니다. 파일이 없으면 *pmode* 새 파일이 처음 닫힐 때 설정 되는 파일의 권한 설정을 지정 합니다. 그렇지 않으면 *pmode* 무시 됩니다. *pmode* 는 매니페스트 상수 중 하나 또는 모두를 포함 하는 정수 식 **_S_IWRITE** 하 고 **_S_IREAD**에 정의 된 \<sys\stat.h >. 두 상수가 지정된 경우 비트 OR 연산자를 사용하여 결합합니다. 의미 *pmode* 는 다음과 같습니다.

|*pmode*|의미|
|-|-|
| **_S_IREAD** | 읽기만 허용합니다. |
| **_S_IWRITE** | 쓰기를 허용합니다. 실제로는 읽기 및 쓰기를 모두 허용합니다. |
| **_S_IREAD** &#124; **_S_IWRITE** | 읽기 및 쓰기를 허용합니다. |

쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다. Windows 운영 체제에서 모든 파일을 읽을 수 있지만 쓰기 전용 권한을 부여할 수는 없습니다. 따라서 **_S_IWRITE** 하 고 **_S_IREAD** | **_S_IWRITE** 동일 합니다.

**_sopen** 현재 파일 권한 마스크를 적용 *pmode* 전에 권한이 설정 됩니다. [_umask](umask.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_sopen**|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|
|**_wsopen**|\<io.h> 또는 \<wchar.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>, \<share.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_locking](locking.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fsopen, _wfsopen](fsopen-wfsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
