---
title: strerror, _strerror, _wcserror, __wcserror
ms.date: 11/04/2016
api_name:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
ms.openlocfilehash: 0b4d70687bc2f428162d035c80d6bc8525a8fb9e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958141"
---
# <a name="strerror-_strerror-_wcserror-__wcserror"></a>strerror, _strerror, _wcserror, __wcserror

시스템 오류 메시지 문자열 (**strerror**, **_wcserror**)을 가져오거나 사용자가 제공 하는 오류 메시지 문자열의 형식을 지정 합니다 ( **_strerror**, **__wcserror**). 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *strerror(
   int errnum
);
char *_strerror(
   const char *strErrMsg
);
wchar_t * _wcserror(
   int errnum
);
wchar_t * __wcserror(
   const wchar_t *strErrMsg
);
```

### <a name="parameters"></a>매개 변수

*errnum*<br/>
오류 번호입니다.

*strErrMsg*<br/>
사용자 제공 메시지

## <a name="return-value"></a>반환 값

이러한 모든 함수는 오류 메시지 문자열에 대한 포인터를 반환합니다. 후속 호출 시 문자열을 덮어쓸 수 있습니다.

## <a name="remarks"></a>설명

**Strerror** 함수는 *errnum* 을 오류 메시지 문자열로 매핑하고 해당 문자열에 대 한 포인터를 반환 합니다. **Strerror** 및 **_strerror** 는 실제로 메시지를 인쇄 하지 않습니다. 이렇게 하려면 [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)와 같은 출력 함수를 호출 해야 합니다.

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

*StrErrMsg* 가 **NULL**로 전달 되는 경우 **_strerror** 는 오류를 생성 한 마지막 라이브러리 호출에 대 한 시스템 오류 메시지가 포함 된 문자열에 대 한 포인터를 반환 합니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. *StrErrMsg* 가 **NULL**과 같지 않은 경우 **_strerror** 는 문자열 메시지, 콜론, 공백, 오류를 생성 하는 마지막 라이브러리 호출에 대 한 시스템 오류 메시지 및 줄 바꿈 문자를 포함 하는 문자열에 대 한 포인터를 반환 합니다. 자의. 문자열 메시지는 94자 이하여야 합니다.

**_Strerror** 의 실제 오류 번호는 변수 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)에 저장 됩니다. 정확한 결과를 생성 하려면 라이브러리 루틴이 오류와 함께 반환 되는 즉시 **_strerror** 를 호출 합니다. 그렇지 않으면 **strerror** 또는 **_strerror** 에 대 한 후속 호출에서 **errno** 값을 덮어쓸 수 있습니다.

**_wcserror** 및 **__wcserror** 는 각각 **strerror** 및 **_strerror**의 와이드 문자 버전입니다.

**_strerror**, **_wcserror**및 **__wcserror** 는 ANSI 정의의 일부가 아닙니다. 이러한 파일은 Microsoft 확장 이며 이식 가능한 코드를 원하는 위치에 사용 하지 않는 것이 좋습니다. ANSI 호환성을 위해 **strerror** 를 대신 사용 합니다.

오류 문자열을 얻으려면 사용 되지 않는 매크로 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 및 사용 되지 않는 내부 함수 **__sys_errlist** 및 **__sys_errlist**대신 **strerror** 또는 **_wcserror** 를 사용 하는 것이 좋습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**, **__wcserror**|\<string.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[perror](perror-wperror.md)의 예를 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
