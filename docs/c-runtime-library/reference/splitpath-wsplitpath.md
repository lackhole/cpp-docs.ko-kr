---
title: _splitpath, _wsplitpath
ms.date: 11/04/2016
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
ms.openlocfilehash: d079bd17912c0711a4e1fbadadf12430520f2c96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62355005"
---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath

경로 이름을 구성 요소로 분해합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext
);
void _wsplitpath(
   const wchar_t *path,
   wchar_t *drive,
   wchar_t *dir,
   wchar_t *fname,
   wchar_t *ext
);
```

### <a name="parameters"></a>매개 변수

*path*<br/>
전체 경로입니다.

*drive*<br/>
드라이브 문자를 뒤에 콜론 (**:**). 전달할 수 있습니다 **NULL** 드라이브 문자 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*dir*<br/>
후행 슬래시를 포함한 디렉터리 경로입니다. 슬래시 ( **/** ), 백슬래시 ( **\\** ), 또는 둘 다 사용할 수 있습니다. 전달할 수 있습니다 **NULL** 디렉터리 경로 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*fname*<br/>
기본 파일 이름(확장명 없음)입니다. 전달할 수 있습니다 **NULL** 파일 이름이 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

*ext*<br/>
선행 마침표를 포함 하 여 파일 확장명 (**.**). 전달할 수 있습니다 **NULL** 파일 이름 확장명이 필요 하지 않은 경우이 매개 변수에 대 한 합니다.

## <a name="remarks"></a>설명

합니다 **_splitpath** 함수를 네 가지 구성 요소로 경로 중단 합니다. **_splitpath** 에서 현재 사용 중인 멀티 바이트 코드 페이지에 따라 멀티 바이트 문자 시퀀스를 인식 합니다. 필요에 따라 멀티 바이트 문자열 인수를 자동으로 처리 합니다. **_wsplitpath** 의 와이드 문자 버전이 **_splitpath**;에 대 한 인수 **_wsplitpath** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

**보안 정보** 이러한 함수는 버퍼 오버런 문제로 인해 발생하는 잠재적인 위협을 일으킵니다. 버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

전체 경로의 각 구성 요소를 별도 버퍼에 저장 됩니다. 매니페스트 상수 **_MAX_DRIVE**, **_MAX_DIR**하십시오 **_MAX_FNAME**, 및 **_MAX_EXT** (STDLIB에 정의 합니다. H) 각 파일 구성 요소에 대 한 최대 크기를 지정 합니다. 해당 매니페스트 상수보다 큰 파일 구성 요소가 있으면 힙이 손상됩니다.

버퍼 오버런 가능성을 방지하려면 각 버퍼가 해당하는 매니페스트 상수만큼 커야 합니다.

다음 표에는 매니페스트 상수의 값이 나와 있습니다.

|이름|값|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

전체 경로 구성 요소 (예: filename), 없으면 **_splitpath** 빈 문자열을 해당 버퍼를 할당 합니다.

전달할 수 있습니다 **NULL** 하 **_splitpath** 이외의 매개 변수에 대해 *경로* 필요 하지 않습니다.

하는 경우 *경로* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_makepath](makepath-wmakepath.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
