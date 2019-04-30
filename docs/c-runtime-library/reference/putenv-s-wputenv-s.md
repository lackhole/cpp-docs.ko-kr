---
title: _putenv_s, _wputenv_s
ms.date: 11/04/2016
apiname:
- _wputenv_s
- _putenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
ms.openlocfilehash: f675c2c0a2b12db3cce841dd0db9fa722393f1b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357865"
---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s

환경 변수를 생성, 수정 또는 제거합니다. 이러한 버전의 [_putenv, _wputenv](putenv-wputenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _putenv_s(
   const char *varname,
   const char *value_string
);
errno_t _wputenv_s(
   const wchar_t *varname,
   const wchar_t *value_string
);
```

### <a name="parameters"></a>매개 변수

*varname*<br/>
환경 변수 이름입니다.

*value_string*<br/>
환경 변수를 설정할 값입니다.

## <a name="return-value"></a>반환 값

성공하면 0을 반환하고, 그렇지 않으면 오류 코드를 반환합니다.

### <a name="error-conditions"></a>오류 조건

|*varname*|*value_string*|반환 값|
|------------|-------------|------------------|
|**NULL**|any|**EINVAL**|
|any|**NULL**|**EINVAL**|

오류 조건 중 하나가 발생할 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속 하도록 허용 된 경우 이러한 함수는 반환 **EINVAL** 설정 **errno** 하 **EINVAL**합니다.

## <a name="remarks"></a>설명

합니다 **_putenv_s** 함수 새 환경 변수를 추가 하거나 기존 환경 변수의 값을 수정 합니다. 환경 변수는 프로세스가 실행되는 환경을 정의합니다(예: 프로그램에 연결할 라이브러리의 기본 검색 경로). **_wputenv_s** 의 와이드 문자 버전이 **_putenv_s**; *envstring* 인수 **_wputenv_s** 는 와이드 문자 문자열입니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname* 은 추가 또는 수정할 환경 변수의 이름 및 *value_string* 은 변수의 값입니다. 하는 경우 *varname* 환경의 일부인 이미 해당 값으로 대체 됩니다 *value_string*이 고, 그렇지 않으면 새 *varname* 변수 및 해당 *value_string*  환경에 추가 됩니다. 빈 문자열을 지정 하 여 환경에서 변수를 제거할 수 있습니다 (즉, "")에 대 한 *value_string*합니다.

**_putenv_s** 하 고 **_wputenv_s** 현재 프로세스에 로컬인 환경에만 적용 되며, 명령 수준 환경을 수정에 사용할 수 없습니다. 이러한 함수는 운영 체제가 프로세스에 대해 만드는 환경 "세그먼트"가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 현재 프로세스가 종료되면 환경이 호출 프로세스의 수준(대부분의 경우 운영 체제 수준)으로 되돌아갑니다. 만든 모든 새로운 프로세스에 수정 된 환경을 전달할 수 있지만 **_spawn**를 **_exec**, 또는 **시스템**, 이러한 새 프로세스는 새 항목을 가져오고 추가 **_putenv_s** 하 고 **_wputenv_s**합니다.

환경 항목을 직접 변경 하지 마세요 대신 **_putenv_s** 하거나 **_wputenv_s** 를 변경 합니다. 특히의 요소를 직접 해제 합니다 **_environ** 전역 배열에 잘못 된 메모리가 처리 될 발생할 수 있습니다.

**getenv** 하 고 **_putenv_s** 전역 변수를 사용 하 여 **_environ** 환경 테이블에 액세스 하려면 **_wgetenv** 하 고 **_wputenv_s** 사용 하 여 **_wenviron**합니다. **_putenv_s** 하 고 **_wputenv_s** 의 값을 변경할 수 있습니다 **_environ** 및 **_wenviron**를 무효화 하므로 *envp*인수 **주** 하며 **_wenvp** 인수 **wmain**합니다. 따라서 것이 안전 **_environ** 또는 **_wenviron** 환경 정보에 액세스할 수 있습니다. 관계에 대 한 자세한 내용은 **_putenv_s** 하 고 **_wputenv_s** 전역 변수를 참조 하세요 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)합니다.

> [!NOTE]
> 합니다 **_putenv_s** 하 고 **_getenv_s** 함수 패밀리는 스레드로부터 안전 하지 않습니다. **_getenv_s** 하는 동안 문자열 포인터를 반환할 수 있습니다 **_putenv_s** 문자열을 수정 하 고 있으므로 임의의 오류를 발생 됩니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

사용 하는 방법을 보여 주는 샘플에 대 한 **_putenv_s**를 참조 하십시오 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)합니다.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
