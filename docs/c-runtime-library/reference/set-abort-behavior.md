---
title: _set_abort_behavior
ms.date: 1/02/2018
apiname:
- _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: 8b36a771a3694c6d01573d619990743c7ddc0f3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356695"
---
# <a name="setabortbehavior"></a>_set_abort_behavior

프로그램이 비정상적으로 종료될 때 수행할 작업을 지정합니다.

> [!NOTE]
> 사용 하지 않는 합니다 [중단](abort.md) 함수를 테스트 또는 디버깅 시나리오에서 Microsoft Store 앱을 제외 하 고 종료 합니다. 스토어 앱을 닫으려면 프로그래밍 또는 UI 방식으로에 따라 허용 되지 않습니다 합니다 [Microsoft Store 정책](/legal/windows/agreements/store-policies)합니다. 자세한 내용은 [UWP 앱 수명 주기](/windows/uwp/launch-resume/app-lifecycle)합니다.

## <a name="syntax"></a>구문

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>매개 변수

*flags*<br/>
새 값을 [중단](abort.md) 플래그입니다.

*mask*<br/>
에 대 한 마스크를 [중단](abort.md) 설정 하는 비트 플래그입니다.

## <a name="return-value"></a>반환 값

플래그의 이전 값입니다.

## <a name="remarks"></a>설명

두 개의 [중단](abort.md) 플래그: **_WRITE_ABORT_MSG** 하 고 **_CALL_REPORTFAULT**합니다. **_WRITE_ABORT_MSG** 프로그램이 비정상적으로 종료 될 때 유용한 텍스트 메시지를 인쇄할지 여부를 결정 합니다. 메시지 상태는 응용 프로그램에 호출 된 [중단](abort.md) 함수입니다. 기본 동작은 메시지를 인쇄하는 것입니다. **_CALL_REPORTFAULT**이면 설정 Watson 크래시 덤프가 생성 되 고 보고 하는 경우를 지정 하 고, [중단](abort.md) 라고 합니다. 기본적으로 DEBUG가 아닌 모드에서는 크래시 덤프 보고가 사용하도록 설정됩니다.

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
