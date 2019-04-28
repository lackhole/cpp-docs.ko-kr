---
title: _get_printf_count_output
ms.date: 11/04/2016
apiname:
- _get_printf_count_output
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
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: 477e4a9e987f27bd70b9707e91b9ea9d84b69993
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332055"
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

나타냅니다 여부 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-패밀리 함수가 지원 합니다 **%n** 형식.

## <a name="syntax"></a>구문

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>반환 값

0이 아닌 경우 **%n** 지원 되는 경우 0 **%n** 지원 되지 않습니다.

## <a name="remarks"></a>설명

경우 **%n** 는 지원 되지 않습니다 (기본값), 발생 **%n** 의 형식 문자열에는 **printf** 함수에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 하는 경우 **%n** 지원 됩니다 (참조 [_set_printf_count_output](set-printf-count-output.md)) 한 다음 **%n** 에 설명 된 대로 동작 합니다 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_set_printf_count_output](set-printf-count-output.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[_set_printf_count_output](set-printf-count-output.md)<br/>
