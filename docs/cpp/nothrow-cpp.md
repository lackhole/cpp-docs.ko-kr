---
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 88041b374cc48ac31c8990aa7f867ba25b33e1d7
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345877"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft 전용**

A **__declspec** 함수 선언에서 사용할 수 있는 확장 된 특성입니다.

## <a name="syntax"></a>구문

> *return-type* __declspec(nothrow) [*call-convention*] *function-name* ([*argument-list*])

## <a name="remarks"></a>설명

모든 새 코드를 사용 하는 것이 좋습니다 합니다 [noexcept](noexcept-cpp.md) 연산자 대신 `__declspec(nothrow)`합니다.

이 특성은 컴파일러에게 선언한 함수와 이 함수가 요청한 함수들이 예외를 throw하지 않도록 명령합니다. 그러나 지시문을 적용 하지 않습니다. 즉,이 생성 하지 않습니다 [std:: terminate](../standard-library/exception-functions.md#terminate) 를 호출 하려면 달리 `noexcept`, 또는 **/std: c + + 17** 모드 (Visual Studio 2017 버전 15.5 이상), `throw()`합니다.

이제 기본값인, 동기 예외 처리 모델을 이용하여 컴파일러는 해제할 수 있는 특정 개체의 수명 추적 메커니즘을 제거할 수 있으며, 코드 크기를 크게 줄일 수 있습니다. 다음 전처리기 지시문에 지정 된, 아래 세 가지 함수 선언은 동일 **/std: c + + 14** 모드:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

**/std: c + + 17** 모드 `throw()` 사용 하는 다른 사용자에 게 동일 `__declspec(nothrow)` 발생 하기 때문에 `std::terminate` 함수에서 예외가 throw 되 면 호출할 합니다.

합니다 `void __stdcall f3() throw();` 선언에 정의한 구문을 사용 하는 C++ 표준입니다. C++17에서는 `throw()` 키워드가 사용 되지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)