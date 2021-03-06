---
title: _set_abort_behavior
ms.date: 01/02/2018
api_name:
- _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: a63d4e77a91dafa4500d5fef8e9b5e94ee28cfbd
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948663"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

프로그램이 비정상적으로 종료될 때 수행할 작업을 지정합니다.

> [!NOTE]
> 테스트 또는 디버깅 시나리오를 제외 하 고는 [abort](abort.md) 함수를 사용 하 여 Microsoft Store 앱을 종료 하지 마세요. 프로그래밍 또는 UI 방식으로 스토어 앱을 닫는 것은 [Microsoft Store 정책](/legal/windows/agreements/store-policies)에 따라 허용 되지 않습니다. 자세한 내용은 [UWP 앱 수명 주기](/windows/uwp/launch-resume/app-lifecycle)를 참조 하세요.

## <a name="syntax"></a>구문

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>매개 변수

*flags*<br/>
[Abort](abort.md) 플래그의 새 값입니다.

*mask*<br/>
설정할 [중단](abort.md) 플래그 비트의 마스크입니다.

## <a name="return-value"></a>반환 값

플래그의 이전 값입니다.

## <a name="remarks"></a>설명

두 개의 [abort](abort.md) 플래그 ( **_WRITE_ABORT_MSG** 및 **_call_reportfault**)가 있습니다. **_WRITE_ABORT_MSG** 프로그램이 비정상적으로 종료 될 때 유용한 텍스트 메시지를 인쇄할지 여부를 결정 합니다. 이 메시지는 응용 프로그램에서 [abort](abort.md) 함수를 호출 했다는 것을 알려 주는 것입니다. 기본 동작은 메시지를 인쇄하는 것입니다. **_Call_reportfault**(설정 된 경우)는 [중단](abort.md) 을 호출할 때 Watson 크래시 덤프가 생성 되 고 보고 되도록 지정 합니다. 기본적으로 DEBUG가 아닌 모드에서는 크래시 덤프 보고가 사용하도록 설정됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>참고자료

[abort](abort.md)<br/>
