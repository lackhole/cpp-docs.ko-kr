---
title: longjmp
ms.date: 08/14/2018
apiname:
- longjmp
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
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: e5189ff7cb850acd9c9a1280f47fc9a1270f8b68
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157411"
---
# <a name="longjmp"></a>longjmp

설정한 스택 환경 및 실행 로캘을 복원 된 `setjmp` 호출 합니다.

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

*값*<br/>
`setjmp` 호출에 대해 반환되는 값입니다.

## <a name="remarks"></a>설명

합니다 **longjmp** 함수에서 이전에 저장 된 스택 환경 및 실행 로캘을 복원 *env* 여 `setjmp`입니다. `setjmp` 및 **longjmp** 는 로캘이 아닌을 실행 하는 방법을 제공 **goto**; 일반 호출을 사용 하지 않고 전에 호출된 된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달 되는 일반적으로 및 규칙을 반환 합니다.

에 대 한 호출 `setjmp` 현재 스택 환경을 저장 될 때 발생 *env*합니다. 에 대 한 후속 호출 **longjmp** 저장된 된 환경을 복원 하 고 바로 다음에 해당 지점에 컨트롤을 반환 합니다. `setjmp` 호출 합니다. *value*가 `setjmp` 호출에 의해 반환된 것처럼 실행이 다시 시작됩니다. 될 때가지고 있던 값을 포함 하는 컨트롤을 받는 루틴에 액세스할 수 있는 모든 변수 (레지스터 변수 제외) 값 **longjmp** 호출 되었습니다. 레지스터 변수 값은 예측할 수 없습니다. `setjmp`에서 반환되는 값은 0이 아니어야 합니다. *value*가 0으로 전달되는 경우 값 1은 실제 반환에서 대체됩니다.

**Microsoft 전용**

Microsoft에서 C++ Windows에서의 코드 **longjmp** 예외 처리 코드와 동일한 스택 해제 의미 체계를 사용 합니다. 안전 하 게 사용 하 여 동일한 배치 하는 C++ 예외를 발생 시킬 수 있습니다. 그러나이 사용량 이식 가능 하며 되지 않으며 중요 한 몇 가지 주의 사항이 있습니다.

호출 **longjmp** 호출한 함수 앞에 `setjmp` 반환 합니다; 그렇지 않으면 결과 예측할 수 없습니다.

사용 하는 경우 다음 제한 사항을 관찰 **longjmp**:

- 레지스터 변수 값이 그대로 유지된다고 가정하지 마십시오. 호출 하는 루틴의 레지스터 변수 값 `setjmp` 한 후 적절 한 값을 복원할 수 있습니다 **longjmp** 실행 됩니다.

- 사용 하지 마세요 **longjmp** 인터럽트를 부동 소수점 예외를 발생 하지 않는 한 인터럽트 처리 루틴을 밖으로 제어를 전송 합니다. 이 경우 프로그램을 통해 인터럽트 처리기에서 반환할 수 있습니다 **longjmp** 하는 경우이 먼저 다시 초기화 부동 소수점 수학 패키지를 호출 하 여 [_fpreset](fpreset.md)합니다.

- 사용 하지 마세요 **longjmp** Windows 코드에서 직접 또는 간접적으로 호출 하는 콜백 루틴에서 제어를 전송 합니다.

- 코드를 사용 하 여 컴파일된 경우 **/EHs** 또는 **/EHsc** 포함 하는 함수를 **longjmp** 호출은 **noexcept** 다음 로컬 개체 함수 스택 해제 중 소멸 되지 않을 수 있습니다.

**Microsoft 전용 종료**

> [!NOTE]
> 노트북에서 C++ 코드를 가정할 수 없습니다 `setjmp` 하 고 `longjmp` 지원 C++ 의미 체계 개체입니다. 특히를 `setjmp` / `longjmp` 쌍에 정의 되지 않은 동작이 대체 하는 경우 호출 합니다 `setjmp` 및 `longjmp` 여 **catch** 및 **throw** 호출 자동 개체에 대 한 모든 non-trivial 소멸자가 있습니다. C++ 프로그램을 사용할 권장 합니다 C++ 예외 처리 메커니즘입니다.

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
