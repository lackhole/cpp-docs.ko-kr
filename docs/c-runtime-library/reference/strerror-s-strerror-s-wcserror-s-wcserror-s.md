---
title: strerror_s, _strerror_s, _wcserror_s, __wcserror_s
ms.date: 11/04/2016
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
ms.openlocfilehash: 00ff9d0df1a78d07eaa509201fb998b30396cc4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353824"
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s

시스템 오류 메시지를 가져옵니다 (**strerror_s**를 **_wcserror_s**) 사용자가 제공한 오류 메시지를 인쇄 하거나 (**_strerror_s**를 **__wcserror_s** ). 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t strerror_s(
   char *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t _strerror_s(
   char *buffer,
   size_t numberOfElements,
   const char *strErrMsg
);
errno_t _wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   int errnum
);
errno_t __wcserror_s(
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *strErrMsg
);
template <size_t size>
errno_t strerror_s(
   char (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t _strerror_s(
   char (&buffer)[size],
   const char *strErrMsg
); // C++ only
template <size_t size>
errno_t _wcserror_s(
   wchar_t (&buffer)[size],
   int errnum
); // C++ only
template <size_t size>
errno_t __wcserror_s(
   wchar_t (&buffer)[size],
   const wchar_t *strErrMsg
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
오류 문자열을 저장할 버퍼입니다.

*numberOfElements*<br/>
버퍼의 크기입니다.

*errnum*<br/>
오류 번호

*strErrMsg*<br/>
사용자 제공 메시지

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드.

### <a name="error-condtions"></a>오류 조건

|*buffer*|*numberOfElements*|*strErrMsg*|내용을 *버퍼*|
|--------------|------------------------|-----------------|--------------------------|
|**NULL**|any|any|N/A|
|any|0|any|수정 안 됨|

## <a name="remarks"></a>설명

합니다 **strerror_s** 맵 함수 *errnum* 오류 메시지 문자열로 문자열을 반환 *버퍼*합니다. **_strerror_s** 오류 번호를;를 사용 하지 않습니다의 현재 값을 사용 하 여 **errno** 적절 한 메시지를 확인 하려면. 모두 **strerror_s** 도 **_strerror_s** 실제로 메시지를 출력 합니다. 이 위해 같은 출력 함수를 호출 해야 [fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
{
   _strerror_s(buffer, 80);
   fprintf( stderr, buffer );
}
```

경우 *strErrMsg* 은 **NULL**, **_strerror_s** 에서 문자열을 반환 합니다 *버퍼* 마지막 라이브러리 호출에 대 한 시스템 오류 메시지를 포함 합니다. 오류가 발생 했습니다. 오류 메시지 문자열은 줄 바꿈 문자('\n')로 종료됩니다. 경우 *strErrMsg* 같지 **NULL**, 한 다음 **_strerror_s** 에서 문자열을 반환 합니다 *버퍼* 문자열 메시지를 순서 대로 포함 하는 콜론, 공백, 오류가 발생 하 고 줄 바꿈 문자를 생성 한 마지막 라이브러리 호출에 대 한 시스템 오류 메시지입니다. 문자열 메시지는 94자 이하여야 합니다.

이러한 함수는 해당 길이 초과 하는 경우 오류 메시지 truncate *numberOfElements* -1입니다. 결과 문자열 *버퍼* 은 항상 null로 종료 합니다.

에 대 한 실제 오류 번호 **_strerror_s** 변수에 저장 됩니다 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 시스템 오류 메시지에 액세스합니다. 이 변수는 오류 번호순으로 정렬된 메시지 배열입니다. **_strerror_s** 적절 한 오류 메시지를 사용 하 여 액세스 합니다 **errno** 변수에 인덱스로 값 **_sys_errlist**합니다. 변수 값 [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 에 있는 요소의 최대 수로 정의 됩니다 합니다 **_sys_errlist** 배열입니다. 정확한 결과 얻으려면 호출 **_strerror_s** 라이브러리 루틴이 오류와 함께 반환 된 직후입니다. 그렇지 않으면, 후속 호출 **strerror_s** 또는 **_strerror_s** 덮어쓸 수는 **errno** 값입니다.

**_wcserror_s** 하 고 **__wcserror_s** 와이드 문자 버전입니다 **strerror_s** 하 고 **_strerror_s**, 각각.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 버퍼가 **NULL** 의 size 매개 변수에 0 인 경우 또는에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 실행을 계속 하도록 허용 된 경우이 함수는 반환 **EINVAL** 설정 **errno** 하 **EINVAL**합니다.

**_strerror_s**, **_wcserror_s**, 및 **__wcserror_s** ANSI 정의의 일부가 아니지만 Microsoft 확장 되도록 합니다. 사용 하지 않는 이식성이 필요한 곳입니다. ANSI 호환성을 위해 사용 하 여 **strerror_s** 대신 합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror_s**|**strerror_s**|**strerror_s**|**_wcserror_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strerror_s**, **_strerror_s**|\<string.h>|
|**_wcserror_s**, **__wcserror_s**|\<string.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[perror](perror-wperror.md)의 예를 참조하세요.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
