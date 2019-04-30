---
title: setjmp
ms.date: 08/14/2018
apiname:
- setjmp
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
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 9f1a2b71a7b8fc7603c36938879348dca16288e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356422"
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

스택 환경에 저장한 후 0을 반환합니다. 경우 **setjmp** 의 결과로 반환을 `longjmp` 호출에서 반환를 *값* 인수의 `longjmp`, 또는 경우에는 *값* 인수의 `longjmp` 0 **setjmp** 1을 반환 합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

합니다 **setjmp** 함수는 나중에 복원할 수를 사용 하 여 스택 환경을 저장 `longjmp`합니다. 함께 사용 하면 **setjmp** 하 고 `longjmp` 비로컬을 실행 하는 방법을 제공 **goto**합니다. setjmp와 longjmp는 일반 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.

에 대 한 호출 **setjmp** 에서 현재 스택 환경을 저장 *env*합니다. 에 대 한 후속 호출 `longjmp` 저장된 된 환경을 복원 하 고 해당 바로 뒤 지점으로 컨트롤을 반환 합니다 **setjmp** 호출 합니다. 컨트롤을 받는 루틴에 액세스할 수 있는 모든 변수(레지스터 변수 제외)는 `longjmp`가 호출될 때 가지고 있던 값을 포함합니다.

사용 하는 것이 불가능 **setjmp** 관리 코드와 네이티브 코드에서 이동 합니다.

**Microsoft 전용**

Microsoft에서 C++ Windows에서의 코드 **longjmp** 예외 처리 코드와 동일한 스택 해제 의미 체계를 사용 합니다. 안전 하 게 사용 하 여 동일한 배치 하는 C++ 예외를 발생 시킬 수 있습니다. 그러나이 사용량 이식 가능 하며 되지 않으며 중요 한 몇 가지 주의 사항이 있습니다. 자세한 내용은 참조 하세요 [longjmp](longjmp.md)합니다.

**Microsoft 전용 종료**

> [!NOTE]
> 노트북에서 C++ 코드를 가정할 수 없습니다 `setjmp` 하 고 `longjmp` 지원 C++ 의미 체계 개체입니다. 특히를 `setjmp` / `longjmp` 쌍에 정의 되지 않은 동작이 대체 하는 경우 호출 합니다 `setjmp` 및 `longjmp` 여 **catch** 및 **throw** 호출 자동 개체에 대 한 모든 non-trivial 소멸자가 있습니다. C++ 프로그램을 사용할 권장 합니다 C++ 예외 처리 메커니즘입니다.

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
