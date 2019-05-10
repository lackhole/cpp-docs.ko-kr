---
title: _set_error_mode
ms.date: 11/04/2016
apiname:
- _set_error_mode
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 8c95ed45423b791a688f05ea30f48e188826a797
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356656"
---
# <a name="seterrormode"></a>_set_error_mode

수정 **__error_mode** C 런타임은 프로그램을 끝낼 수 있는 오류에 대 한 오류 메시지를 기록 하는 위치를 기본이 아닌 위치를 결정 합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _set_error_mode(
   int mode_val
);
```

### <a name="parameters"></a>매개 변수

*mode_val*<br/>
오류 메시지의 대상입니다.

## <a name="return-value"></a>반환 값

오류가 발생하면 이전 설정 또는 -1을 반환합니다.

## <a name="remarks"></a>설명

값을 설정 하 여 오류 출력 싱크를 제어 **__error_mode**합니다. 표준 오류 출력을 직접 사용할 수는 예를 들어 합니다 **MessageBox** API.

합니다 *mode_val* 매개 변수는 다음 값 중 하나로 설정할 수 있습니다.

|매개 변수|설명|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|오류 싱크가 도달한 **__app_type**합니다.|
|**_OUT_TO_STDERR**|오류 싱크가 표준 오류입니다.|
|**_OUT_TO_MSGBOX**|오류 싱크가 메시지 상자입니다.|
|**_REPORT_ERRMODE**|현재 보고서 **__error_mode** 값입니다.|

나열된 값 이외의 값이 전달되면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 **_set_error_mode** 설정 **errno** 하 **EINVAL** -1을 반환 합니다.

사용 하 여 사용 하는 경우는 [assert](assert-macro-assert-wassert.md)를 **_set_error_mode** 대화 상자에서 실패 한 문을 표시 하 고 선택 하는 옵션을 사용 하면 합니다 **무시** 수 있도록 단추 프로그램 실행을 계속 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_error_mode**|\<stdlib.h>|

## <a name="example"></a>예제

```C
// crt_set_error_mode.c
// compile with: /c
#include <stdlib.h>
#include <assert.h>

int main()
{
   _set_error_mode(_OUT_TO_STDERR);
   assert(2+2==5);
}
```

```Output
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>참고자료

[assert Macro, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
