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
ms.openlocfilehash: 49ee800bafff017c29b73c5f6fd64318009a140a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403466"
---
# <a name="raising-software-exceptions"></a>소프트웨어 예외 발생

프로그램 오류의 가장 일반적인 원인 중 몇 가지는 시스템에서 예외로 플래그가 지정되지 않습니다. 예를 들어 메모리 블록을 할당하려고 시도하지만 메모리가 부족한 경우, 런타임 또는 API 함수에서 예외를 발생시키지 않지만 오류 코드를 반환합니다.

코드에서 조건을 검색 하 고 다음 호출 하 여 보고 예외로 조건을 처리할 수는 있지만 합니다 [RaiseException](https://msdn.microsoft.com/library/windows/desktop/ms680552) 함수입니다. 이런 식으로 오류에 플래그를 지정함으로써 구조적 예외 처리의 장점을 모든 종류의 런타임 오류에 적용할 수 있습니다.

오류에 대해 구조적 예외 처리를 사용하려면

- 이벤트에 대해 고유한 예외 코드를 정의합니다.

- 호출 `RaiseException` 문제를 감지 하는 경우.

- 정의한 예외 코드를 테스트하려면 예외 처리 필터를 사용합니다.

\<winerror.h > 파일에는 예외 코드의 형식을 보여 줍니다. 기존 예외 코드와 충돌하는 코드를 정의하지 않으려면 세 번째 최상위 비트를 1로 설정합니다. 4개의 최상위 비트는 다음 표와 같이 설정되어야 합니다.

|비트|권장하는 이진 설정|설명|
|----------|--------------------------------|-----------------|
|31-30|11|이러한 두 비트는 코드의 기본 상태를 설명합니다.  11 = 오류, 00 = 성공, 01 = 정보, 10 = 경고 합니다.|
|29|1|클라이언트 비트. 사용자 정의 코드의 경우 1로 설정합니다.|
|28|0|예약된 비트. 0으로 설정된 상태로 둡니다.|

"오류" 설정이 대부분의 예외에 적합하긴 하지만, 원하는 경우 처음 두 비트를 11 이외의 이진 값으로 설정할 수 있습니다. 명심해야 할 중요한 사항은 위의 표와 같이 29 및 28 비트를 설정하는 것입니다.

결과 오류 코드는 최상위 네 비트가 16 진수 5.로 설정 해야 하므로 예를 들어, 다음 정의 모든 Windows 예외 코드를 사용 하 여 충돌 하지 않는 예외 코드를 정의 합니다. 그러나 타사 DLL에서 사용하는 코드를 확인해야 할 수 있습니다.

```cpp
#define STATUS_INSUFFICIENT_MEM       0xE0000001
#define STATUS_FILE_BAD_FORMAT        0xE0000002
```

예외 코드를 정의한 후 예외 코드를 사용하여 예외를 발생시킬 수 있습니다. 예를 들어, 다음 코드를 발생 시킵니다는 `STATUS_INSUFFICIENT_MEM` 메모리 할당 문제에 대 한 응답으로 예외:

```cpp
lpstr = _malloc( nBufferSize );
if (lpstr == NULL)
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);
```

예외를 발생시키기만 하려면 마지막 세 매개 변수를 0으로 설정하면 됩니다. 마지막 세 매개 변수는 추가 정보를 전달하고 처리기가 계속 실행되지 않도록 하는 플래그를 설정하는 데 유용합니다. 참조를 [RaiseException](https://msdn.microsoft.com/library/windows/desktop/ms680552) 자세한 내용은 Windows SDK에는 함수입니다.

이렇게 하면 예외 처리 필터에서 사용자가 정의한 코드를 테스트할 수 있습니다. 예를 들어:

```cpp
__try {
    ...
}
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )
```

## <a name="see-also"></a>참고자료

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)