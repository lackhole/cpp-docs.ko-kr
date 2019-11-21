---
title: 소프트웨어 예외 발생
ms.date: 11/04/2016
helpviewer_keywords:
- run-time errors, treating as exceptions
- exception handling [C++], errors as exceptions
- exceptions [C++], flagging errors as exceptions
- errors [C++], treating as exceptions
- exception handling [C++], detecting errors
- structured exception handling [C++], errors as exceptions
- exceptions [C++], software
- RaiseException function
- software exceptions [C++]
- formats [C++], exception codes
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
ms.openlocfilehash: 7c58ae2e2b6635345a162d11d2b75a9865d37751
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246402"
---
# <a name="raising-software-exceptions"></a>소프트웨어 예외 발생

프로그램 오류의 가장 일반적인 원인 중 몇 가지는 시스템에서 예외로 플래그가 지정되지 않습니다. 예를 들어 메모리 블록을 할당하려고 시도하지만 메모리가 부족한 경우, 런타임 또는 API 함수에서 예외를 발생시키지 않지만 오류 코드를 반환합니다.

However, you can treat any condition as an exception by detecting that condition in your code and then reporting it by calling the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function. 이런 식으로 오류에 플래그를 지정함으로써 구조적 예외 처리의 장점을 모든 종류의 런타임 오류에 적용할 수 있습니다.

오류에 대해 구조적 예외 처리를 사용하려면

- 이벤트에 대해 고유한 예외 코드를 정의합니다.

- Call `RaiseException` when you detect a problem.

- 정의한 예외 코드를 테스트하려면 예외 처리 필터를 사용합니다.

The \<winerror.h> file shows the format for exception codes. 기존 예외 코드와 충돌하는 코드를 정의하지 않으려면 세 번째 최상위 비트를 1로 설정합니다. 4개의 최상위 비트는 다음 표와 같이 설정되어야 합니다.

|비트|권장하는 이진 설정|설명|
|----------|--------------------------------|-----------------|
|31-30|11|이러한 두 비트는 코드의 기본 상태(11 = 오류, 00 = 성공, 01 = 정보, 10 = 경고)를 나타냅니다.|
|29|1|클라이언트 비트. 사용자 정의 코드의 경우 1로 설정합니다.|
|28|0|예약된 비트. 0으로 설정된 상태로 둡니다.|

"오류" 설정이 대부분의 예외에 적합하긴 하지만, 원하는 경우 처음 두 비트를 11 이외의 이진 값으로 설정할 수 있습니다. 명심해야 할 중요한 사항은 위의 표와 같이 29 및 28 비트를 설정하는 것입니다.

The resulting error code should therefore have the highest four bits set to hexadecimal E. For example, the following definitions define exception codes that do not conflict with any Windows exception codes. 그러나 타사 DLL에서 사용하는 코드를 확인해야 할 수 있습니다.

```cpp
#define STATUS_INSUFFICIENT_MEM       0xE0000001
#define STATUS_FILE_BAD_FORMAT        0xE0000002
```

예외 코드를 정의한 후 예외 코드를 사용하여 예외를 발생시킬 수 있습니다. For example, the following code raises the `STATUS_INSUFFICIENT_MEM` exception in response to a memory allocation problem:

```cpp
lpstr = _malloc( nBufferSize );
if (lpstr == NULL)
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);
```

예외를 발생시키기만 하려면 마지막 세 매개 변수를 0으로 설정하면 됩니다. 마지막 세 매개 변수는 추가 정보를 전달하고 처리기가 계속 실행되지 않도록 하는 플래그를 설정하는 데 유용합니다. See the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function in the Windows SDK for more information.

이렇게 하면 예외 처리 필터에서 사용자가 정의한 코드를 테스트할 수 있습니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```cpp
__try {
    ...
}
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )
```

## <a name="see-also"></a>참조

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[Structured exception handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)