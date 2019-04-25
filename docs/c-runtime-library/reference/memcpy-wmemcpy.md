---
title: memcpy, wmemcpy
ms.date: 11/04/2016
apiname:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: afdb854bd28b55735cc6b5e26788307e2db0caa6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156592"
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy

버퍼 간에 바이트를 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [memcpy_s, wmemcpy_s](memcpy-s-wmemcpy-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
새 버퍼입니다.

*src*<br/>
복사할 버퍼입니다.

*count*<br/>
복사할 문자 수입니다.

## <a name="return-value"></a>반환 값

변수의 *dest*합니다.

## <a name="remarks"></a>설명

**memcpy** 복사본 *개수* 바이트 *src* 하 *dest*; **wmemcpy** 복사본 *개수* 와이드 문자 (2 바이트)입니다. 소스와 대상이 겹치는 경우의 동작은 **memcpy** 정의 되지 않습니다. 사용 하 여 **memmove** 겹치는 영역을 처리 하도록 합니다.

> [!IMPORTANT]
> 대상 버퍼의 크기가 소스 버퍼의 크기보다 크거나 같아야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

> [!IMPORTANT]
> 많은 버퍼 오버런와 보안 악용 가능성이 있는의 부적절 한 사용 현황 추적 하므로 **memcpy**,이 함수는 보안 개발 수명 주기 (SDL)에서 "금지 된" 함수 간의 나열 됩니다.  일부 VC + + 라이브러리 클래스 계속 사용 하는 것을 관찰할 수 있습니다 **memcpy**합니다.  VC + + 컴파일러 최적화 프로그램에 대 한 호출을 내보내는 경우도 많으며 게다가 **memcpy**합니다.  Visual C++ 제품은 SDL 프로세스에 따라 개발되었으므로 이처럼 금지된 함수의 사용이 철저하게 평가되었습니다.  라이브러리에서 이러한 함수를 사용하는 경우에는 이러한 호출을 통해 버퍼 오버런이 허용되지 않도록 호출을 면밀하게 검사했습니다.  컴파일러의 경우 경우에 따라 특정 코드 패턴은 동일한 것으로 인식 패턴 **memcpy**, 함수 호출으로 바뀌는 합니다.  이러한 경우 사용 **memcpy** 는 원본 보다 더 이상 안전 하지 않은 지침; 성능 튜닝에 대 한 호출에 최적화 된가 단순히 **memcpy** 함수입니다.  "안전한" CRT 함수를 사용한다고 해서 보안이 보장되는 것은 아니듯이(위험 가능성만 낮아질 뿐임), "금지된" 함수를 사용한다고 해서 반드시 위험한 것도 아니며 보안을 유지하려면 더욱 철저한 확인이 필요할 뿐입니다.
>
> 때문에 **memcpy** VC + + 컴파일러 및 라이브러리에서 사용 되므로 신중 하 게 방법이 필요, SDL과 호환 되는 코드 내에서 이러한 호출이 허용 됩니다.  **memcpy** 응용 프로그램 소스 코드에 도입 된 호출은 SDL과 호환 사용 하는 보안 전문가가 검토 된 경우.

합니다 **memcpy** 하 고 **wmemcpy** 함수는 경우에 중단 될 상수 **_CRT_SECURE_DEPRECATE_MEMORY** 위해에서 포함 문 이전에 정의 된 사용 되지 않는 경우, 아래 예제와 같이 함수:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

또는

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**memcpy**|\<memory.h> 또는 \<string.h>|
|**wmemcpy**|\<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

참조 [memmove](memmove-wmemmove.md) 사용 하는 방법의 예제 **memcpy**합니다.

## <a name="see-also"></a>참고자료

[버퍼 조작](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
