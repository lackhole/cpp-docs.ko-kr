---
title: _set_printf_count_output
ms.date: 11/04/2016
apiname:
- _set_printf_count_output
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
- set_printf_count_output
- _set_printf_count_output
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
ms.openlocfilehash: 0d4847d850b39c7c03ea92a98499715b1e6a4913
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356526"
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output

지원을 설정 또는 해제 합니다 **%n** 형식의 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-패밀리 함수입니다.

## <a name="syntax"></a>구문

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>매개 변수

*enable*<br/>
사용 하도록 설정 하려면 0이 아닌 값 **%n** 를 지원 하지 않으려면 0 **%n** 지원 합니다.

## <a name="property-valuereturn-value"></a>속성 값/반환 값

상태의 **%n** 이 함수를 호출 하기 전에 지원할: 0이 아닌 경우 **%n** 지원이 활성화 된 경우 사용 하지 않도록 설정 된 경우에 0입니다.

## <a name="remarks"></a>설명

보안상의 이유로 지원 합니다 **%n** 형식 지정자에는 기본적으로 비활성화 되어 **printf** 및 모든 해당 변형 항목입니다. 하는 경우 **%n** 에서 발견 되는 **printf** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 하는 형식 지정, 기본 동작 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 호출 **_set_printf_count_output** 0이 아닌 인수를 사용 하면 **printf**-해석 패밀리 함수가 **%n** 에 설명 된 대로 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_printf_count_output**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_set_printf_count_output.c
#include <stdio.h>

int main()
{
   int e;
   int i;
   e = _set_printf_count_output( 1 );
   printf( "%%n support was %sabled.\n",
        e ? "en" : "dis" );
   printf( "%%n support is now %sabled.\n",
        _get_printf_count_output() ? "en" : "dis" );
   printf( "12345%n6789\n", &i ); // %n format should set i to 5
   printf( "i = %d\n", i );
}
```

```Output
%n support was disabled.
%n support is now enabled.
123456789
i = 5
```

## <a name="see-also"></a>참고자료

[_get_printf_count_output](get-printf-count-output.md)<br/>
