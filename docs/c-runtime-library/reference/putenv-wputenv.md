---
title: _putenv, _wputenv
ms.date: 11/04/2016
api_name:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
ms.openlocfilehash: 8fe699a476ea1dd09a6ce9922294bce398df16b2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949890"
---
# <a name="_putenv-_wputenv"></a>_putenv, _wputenv

환경 변수를 생성, 수정 또는 제거합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)를 참조하세요.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>매개 변수

*envstring*<br/>
환경 문자열 정의입니다.

## <a name="return-value"></a>반환 값

성공 하면 0을 반환 하 고, 오류 발생 시-1을 반환 합니다.

## <a name="remarks"></a>설명

**_Putenv** 함수는 새 환경 변수를 추가 하거나 기존 환경 변수의 값을 수정 합니다. 환경 변수는 프로세스가 실행되는 환경을 정의합니다(예: 프로그램에 연결할 라이브러리의 기본 검색 경로). **_wputenv** 는 **_putenv**의 와이드 문자 버전입니다. **_wputenv** 에 대 한 *envstring* 인수는 와이드 문자열입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstring* 인수는 *varname*=*value_string*형식의 문자열에 대 한 포인터 여야 합니다. 여기서 *varname* 은 추가 또는 수정할 환경 변수의 이름이 고 *value_string* 는 변수의입니다. 기본값. *Varname* 이 이미 환경의 일부 이면 해당 값이 *value_string*로 바뀝니다. 그렇지 않으면 새 *varname* 변수와 해당 *value_string* 값이 환경에 추가 됩니다. 빈 *value_string*을 지정 하 여 환경에서 변수를 제거할 수 있습니다. 즉, *varname*=만 지정 하면 됩니다.

**_putenv** 및 **_wputenv** 는 현재 프로세스에 로컬인 환경에만 영향을 줍니다. 명령 수준 환경을 수정 하는 데 사용할 수 없습니다. 즉, 이러한 함수는 운영 체제가 프로세스에 대해 만드는 환경 세그먼트가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 현재 프로세스가 종료되면 환경이 호출 프로세스의 수준(대부분의 경우 운영 체제 수준)으로 되돌아갑니다. 그러나 수정 된 환경을 _oknenv, **_exec**또는 **system**에서 만든모든 새 프로세스에 전달할 수 있으며 이러한 새 프로세스는 **_putenv** 및 **_wputenv**에 의해 추가 된 새 항목을 가져옵니다.

환경 항목을 직접 변경 하지 마십시오. 대신 **_putenv** 또는 **_wputenv** 를 사용 하 여 변경 합니다. 특히 **_environ []** 전역 배열의 요소를 직접 해제 하면 잘못 된 메모리가 처리 될 수 있습니다.

**getenv** 및 **_putenv** 전역 변수 **_environ** 을 사용 하 여 환경 테이블에 액세스 합니다. **_wgetenv** 및 **_wputenv** use **_wenviron**를 사용 합니다. **_putenv** 및 **_wputenv** 는 **_environ** 및 **_wenviron**의 값을 변경할 수 있으므로 **_envp** 인수를 **main** 로 무효화 하 고 **_wenvp** 인수를 **wmain**으로 무효화 합니다. 따라서 **_environ** 또는 **_wenviron** 를 사용 하 여 환경 정보에 액세스 하는 것이 더 안전 합니다. **_Putenv** 와 **_wputenv** 를 전역 변수와 비교 하는 방법에 대 한 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)를 참조 하세요.

> [!NOTE]
> **_Putenv** 및 **_getenv** 함수 패밀리는 스레드로부터 안전 하지 않습니다. **_putenv** 가 문자열을 수정 하는 동안 **_getenv** 가 문자열 포인터를 반환할 수 있으므로 임의 오류가 발생 합니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

**_Putenv**를 사용 하는 방법에 대 한 샘플은 [getenv, _wgetenv](getenv-wgetenv.md)를 참조 하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
