---
title: __fastfail
ms.date: 11/04/2016
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: a9f75cbf3c572401ef26fb16ced221eb24d35534
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041508"
---
# <a name="fastfail"></a>__fastfail

**Microsoft 전용**

최소한의 오버헤드로 호출 프로세스를 즉시 종료합니다.

## <a name="syntax"></a>구문

```
void __fastfail(unsigned int code);
```

#### <a name="parameters"></a>매개 변수

*코드*<br/>
[in] `FAST_FAIL_<description>` winnt.h 또는 wdm.h의 프로세스 종료 이유를 나타내는 기호화 된 상수입니다.

## <a name="return-value"></a>반환 값

`__fastfail` 내장 함수는 결과를 반환하지 않습니다.

## <a name="remarks"></a>설명

합니다 `__fastfail` 내장 함수에 대 한 메커니즘을 제공을 *빠른 실패* 요청-요청 즉각적인 프로세스 종료를 잠재적으로 손상 된 프로세스에 대 한 방법입니다. 프로그램 상태와 스택을 복구할 수 없을 정도로 손상시켰을 수 있는 심각한 오류는 일반적인 예외 처리 기능을 통해 처리할 수 없습니다. 최소한의 오버헤드로 프로세스를 종료하려면 `__fastfail`을 사용합니다.

내부적으로 `__fastfail`은 다양한 아키텍처별 메커니즘을 사용하여 구현됩니다.

|아키텍처|명령|코드 인수의 위치|
|------------------|-----------------|-------------------------------|
|x86|int 0x29|ecx|
|X64|int 0x29|rcx|
|ARM|Opcode 0xDEFB|r0|
|ARM64|Opcode 0xF003|x0|

빠른 실패 요청은 독립적이며 대개 두 가지 명령만 있으면 실행할 수 있습니다. 빠른 실패 요청이 실행되면 커널이 적절한 작업을 수행합니다. 사용자 모드 코드에서는 빠른 실패 이벤트 발생 시 명령 포인터 자체 이외의 메모리 종속성이 없습니다. 따라서 메모리가 심각하게 손상되어도 안정성을 최대화할 수 있습니다.

winnt.h 또는 wdm.h의 `code` 기호화된 상수 중 하나인 `FAST_FAIL_<description>` 인수는 오류 상태 유형을 설명하며 환경별 방식으로 오류 보고서에 통합됩니다.

사용자 모드 빠른 실패 요청은 2차 비연속적 예외로 표시됩니다(예외 코드 0xC0000409, 예외 매개 변수 하나 이상 포함). 첫 번째 예외 매개 변수는 `code` 값입니다. 이 예외 코드는 프로세스가 손상되었으며 오류에 대한 응답으로 최소한의 In-Process 작업을 수행해야 함을 WER(Windows 오류 보고) 및 디버깅 인프라에 알립니다. 커널 모드 빠른 실패 요청은 전용 버그 검사 코드인 `KERNEL_SECURITY_CHECK_FAILURE`(0x139)를 사용하여 구현됩니다. 두 경우 모두 프로그램이 손상된 상태로 간주되므로 예외 처리기가 호출되지 않습니다. 디버거가 있으면 종료 전에 프로그램 상태를 검사합니다.

Windows 8부터는 빠른 실패 메커니즘이 기본적으로 지원됩니다. 빠른 실패 명령을 기본적으로 지원하지 않는 Windows 운영 체제는 보통 빠른 실패 요청을 액세스 위반 또는 `UNEXPECTED_KERNEL_MODE_TRAP` 버그 검사로 처리합니다. 이러한 경우에도 프로그램은 종료되지만 종료 속도는 느려질 수 있습니다.

`__fastfail` 만 내장 함수로 제공 됩니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__fastfail`|x86, x64, ARM, ARM64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
