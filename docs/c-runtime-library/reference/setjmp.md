---
title: setjmp
ms.date: 08/14/2018
api_name:
- setjmp
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 4a88467f5b94ceae4281a35f1486380a877be2e5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948234"
---
# <a name="setjmp"></a>setjmp

프로그램의 현재 상태를 저장합니다.

## <a name="syntax"></a>구문

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>매개 변수

*env*<br/>
환경이 저장되는 변수입니다.

## <a name="return-value"></a>반환 값

스택 환경에 저장한 후 0을 반환합니다. **Setjmp** 가 `longjmp` 호출의 결과로 반환 `longjmp`되는 경우의 *value* 인수를 반환 하거나 `longjmp` 의 *값* 인수가 0 이면 **setjmp** 는 1을 반환 합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

**Setjmp** 함수는를 사용 하 여 `longjmp`나중에 복원할 수 있는 스택 환경을 저장 합니다. 함께 사용 하는 경우 setjmp `longjmp` 를 사용 하 여 로컬이 아닌 **goto**를 실행 하는 방법을 제공 합니다. setjmp와 longjmp는 일반 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.

**Setjmp** 에 대 한 호출은 현재 스택 환경을 *env*에 저장 합니다. 에 대 `longjmp` 한 후속 호출은 저장 된 환경을 복원 하 고 컨트롤을 해당 **setjmp** 호출 바로 다음의 지점으로 반환 합니다. 컨트롤을 받는 루틴에 액세스할 수 있는 모든 변수(레지스터 변수 제외)는 `longjmp`가 호출될 때 가지고 있던 값을 포함합니다.

**Setjmp** 를 사용 하 여 네이티브 코드에서 관리 코드로 이동할 수는 없습니다.

**Microsoft 전용**

Windows의 C++ Microsoft 코드에서, 명령줄은 예외 처리 코드와 동일한 스택 해제 의미 **체계를 사용** 합니다. 예외를 발생 시킬 수 있는 C++ 것과 동일한 위치에서를 사용 하는 것이 안전 합니다. 그러나이 사용은 이식할 수 없으며 몇 가지 중요 한 주의 사항이 있습니다. 자세한 내용은 다음을 [참조 하세요](longjmp.md).

**Microsoft 전용 종료**

> [!NOTE]
> 이식 가능한 C++ 코드에서는 개체 의미 체계 `setjmp` 를 `longjmp` 가정 C++ 하 고 지원할 수 없습니다. `setjmp` 특히 및 / `longjmp` **를 catch** 하 여 throw 하면 자동 개체에 대 한 특수 한 소멸자를 호출 하는 경우 호출 쌍은 정의 되지 않은 동작을 발생 시킵니다. `setjmp` `longjmp` 프로그램 C++ 에서 예외 처리 메커니즘을 사용 하 C++ 는 것이 좋습니다.

자세한 내용은 [setjmp 및 longjmp 사용](../../cpp/using-setjmp-longjmp.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_fpreset](fpreset.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)
