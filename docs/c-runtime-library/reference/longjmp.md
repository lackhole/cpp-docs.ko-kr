---
title: longjmp
ms.date: 08/14/2018
api_name:
- longjmp
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
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: b4527a29475f9e393dc5abf19b866d926bec2ccc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953136"
---
# <a name="longjmp"></a>longjmp

`setjmp` 호출로 설정 된 스택 환경 및 실행 로캘을 복원 합니다.

## <a name="syntax"></a>구문

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>매개 변수

*env*<br/>
환경이 저장되는 변수입니다.

*value*<br/>
`setjmp` 호출에 대해 반환되는 값입니다.

## <a name="remarks"></a>설명

이 **함수는** *이전에* `setjmp`에 저장 된 스택 환경 및 실행 로캘을 복원 합니다. `setjmp`및 이상으로는 비로컬 **goto**를 **실행 하는** 방법을 제공 합니다. 일반적으로 일반 호출 및 반환 규칙을 사용 하지 않고 이전에 호출 된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달 하는 데 사용 됩니다.

를 `setjmp` 호출 하면 현재 스택 환경이 *env*에 저장 됩니다. 이상 값에 대 한 후속 호출에서는 저장 된 환경을 **복원 하 고** 컨트롤을 해당 `setjmp` 호출 바로 다음 지점으로 반환 합니다. *value*가 `setjmp` 호출에 의해 반환된 것처럼 실행이 다시 시작됩니다. 컨트롤을 받는 루틴에 액세스할 수 있는 모든 변수 (레지스터 변수 제외)의 값에는가 중이 호출 되었을 **때의 값이 포함** 됩니다. 레지스터 변수 값은 예측할 수 없습니다. `setjmp`에서 반환되는 값은 0이 아니어야 합니다. *value*가 0으로 전달되는 경우 값 1은 실제 반환에서 대체됩니다.

**Microsoft 전용**

Windows의 C++ Microsoft 코드에서, 명령줄은 예외 처리 코드와 동일한 스택 해제 의미 **체계를 사용** 합니다. 예외를 발생 시킬 수 있는 C++ 것과 동일한 위치에서를 사용 하는 것이 안전 합니다. 그러나이 사용은 이식할 수 없으며 몇 가지 중요 한 주의 사항이 있습니다.

를 `setjmp` 호출한 **함수가 반환 되기 전에** 는 이상 값만 호출 합니다. 그렇지 않으면 결과를 예측할 수 없습니다.

을 사용 하는 경우 다음 **제한 사항을 준수**합니다.

- 레지스터 변수 값이 그대로 유지된다고 가정하지 마십시오. 을 호출 `setjmp` 하는 루틴의 레지스터 변수 값은가 중 **jmp** 를 실행 한 후 적절 한 값으로 복원 되지 않을 수 있습니다.

- 부동 소수점 예외로 인해 인터럽트가 발생 하지 않는 한 **제어를 인터럽트** 처리 루틴 외부로 전달 하지 마십시오. 이 경우, 프로그램은 [_fpreset](fpreset.md)를 호출 하 여 부동 소수점 수학 패키지를 먼저 다시 초기화 하는 경우에는 **prjmp** 를 통해 인터럽트 처리기에서 반환 될 수 있습니다.

- Windows 코드를 **사용 하** 여 직접 또는 간접적으로 호출 하는 콜백 루틴에서 제어를 전송 하는 데 사용 하지 마십시오.

- **/EHs** 또는 **/ehsc** 를 사용 하 여 코드를 컴파일하고, **noexcept** **를 포함** 하는 함수를 사용 하는 경우에는 스택 해제 중에 해당 함수의 로컬 개체를 소멸 수 없습니다.

**Microsoft 전용 종료**

> [!NOTE]
> 이식 가능한 C++ 코드에서는 개체 의미 체계 `setjmp` 를 `longjmp` 가정 C++ 하 고 지원할 수 없습니다. `setjmp` 특히 및 / `longjmp` **를 catch** 하 여 throw 하면 자동 개체에 대 한 특수 한 소멸자를 호출 하는 경우 호출 쌍은 정의 되지 않은 동작을 발생 시킵니다. `setjmp` `longjmp` 프로그램 C++ 에서 예외 처리 메커니즘을 사용 하 C++ 는 것이 좋습니다.

자세한 내용은 [setjmp 및 longjmp 사용](../../cpp/using-setjmp-longjmp.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_fpreset](fpreset.md)에 대한 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
