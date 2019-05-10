---
title: 예외 사양 (throw, noexcept) (C++)
ms.date: 01/18/2018
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
ms.openlocfilehash: a3d4c0446cd8dde83febb1b4269811b5dec3c477
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222111"
---
# <a name="exception-specifications-throw-noexcept-c"></a>예외 사양 (throw, noexcept) (C++)

예외 사양은 C++ 는 프로그래머의 의도 된 예외에 대 한 형식을 나타내는 언어 기능을 함수에 의해 전파 될 수 있습니다. 함수 수도 사용 하 여 예외에 의해 종료 되지 않을 수 있습니다를 지정할 수 있습니다는 *예외 사양*합니다. 컴파일러는 함수에 대 한 호출을 최적화 하기 위해이 정보를 사용할 수 하 고 예기치 않은 예외가 있으면 프로그램을 종료 하는 함수를 이스케이프 합니다.

C++17 이전 두 종류의 예외 사양이 있었습니다. 합니다 *noexcept 사양* C + + 11에서부터 였습니다. 함수를 이스케이프할 수 있는 잠재적인 예외 집합이 비어 있는지 여부를 지정 합니다. *동적 예외 사양*, 또는 `throw(optional_type_list)` 가 c++11에서 사용 되지 않는 사양과 제외한 c++17에서 제거 `throw()`에 대 한 별칭인 `noexcept(true)`합니다. 이 예외 사양 함수에서 예외를 throw 할 수 있습니다 하는 방법에 대 한 요약 정보를 제공 하도록 설계 되었습니다 하는데 실제로 문제가 될 수 있습니다. 어느 정도 유용한 것으로 입증 된 하나의 동적 예외 사양이 되었습니다를 무조건 `throw()` 사양입니다. 예를 들어, 함수 선언:

```cpp
void MyFunction(int i) throw();
```
컴파일러에 함수가 아무 예외도 throw하지 않음을 알립니다. 그러나 **/std: c + + 14** 모드가 발생할 수 있습니다 함수는 예외를 throw 하는 경우 동작이 정의 되지 않았습니다. 따라서 사용할 것을 권장 합니다 [noexcept](../cpp/noexcept-cpp.md) 대신 위의 연산자:

```cpp
void MyFunction(int i) noexcept;
```
다음 표에서 Microsoft C++ 는 예외 사양 구현 합니다.

|예외 사양|의미|
|-----------------------------|-------------|
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|이 함수는 예외를 throw하지 않습니다. [/std: c + + 14](../build/reference/std-specify-language-standard-version.md) 모드 (기본값), `noexcept` 고 `noexcept(true)` 동일 합니다. 선언 된 함수에서 예외가 throw 됩니다 때 `noexcept` 또는 `noexcept(true)`하십시오 [std:: terminate](../standard-library/exception-functions.md#terminate) 가 호출 됩니다. 로 선언 된 함수에서 예외가 throw 됩니다 때 `throw()` 에 **/std: c + + 14** 모드에서는 결과 정의 되지 않은 동작입니다. 특정 함수가 호출 됩니다. 이 컴파일러를 호출 하는 데 필요한 표준 C + + 14에서 확산 [std::unexpected](../standard-library/exception-functions.md#unexpected)합니다.  <br/> **Visual Studio 2017 버전 15.5 이상**: **/std: c + + 17** 모드 `noexcept`합니다 `noexcept(true)`, 및 `throw()` 모두 동일 합니다. **/std: c + + 17** 모드 `throw()` 별칭인 `noexcept(true)`합니다. **/std: c + + 17** 모드에서는 이러한 사양 중 하나를 사용 하 여 선언 된 함수에서 예외가 throw 되 면 [std:: terminate](../standard-library/exception-functions.md#terminate) 가 호출 c++17 표준에서 필요에 따라 합니다.|
|`noexcept(false)`<br/>`throw(...)`<br/>사양이 없는|함수는 모든 형식의 예외를 throw 할 수 있습니다.|
|`throw(type)`| (**C + + 14 및 이전 버전**) 형식의 예외를 throw 함수 `type`합니다. 컴파일러에서 구문을 허용 하지만로 해석 `noexcept(false)`합니다. **/std: c + + 17** 모드 컴파일러 경고 C5040을 실행 합니다.|

예외 처리 응용 프로그램에서 사용 하는 경우 함수에에서 있어야 함수 외부 범위를 종료 되기 전에 예외를 throw 하는 핸들 표시 된 호출 스택은 `noexcept`, `noexcept(true)`, 또는 `throw()`합니다. 예외를 throw 하 고 예외를 처리 하는 것으로 지정 된 함수 사이 호출 하는 경우 `noexcept`, `noexcept(true)` (또는 `throw()` 에서 **/std: c + + 17** 모드), 경우 프로그램이 종료 되는 noexcept 함수가 예외를 전파합니다.

함수의 예외 동작이 다음 요인에 따라 달라 집니다.

- [언어 표준 컴파일 모드](../build/reference/std-specify-language-standard-version.md) 설정 됩니다.
- C 또는 C++에서 함수를 컴파일하는지 여부

- [/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용 합니다.

- 예외 사양을 명시적으로 지정하는지 여부

C 함수에서는 명시적 예외 사양이 허용되지 않습니다. C 함수 아닌 것으로 가정에서 예외를 throw **/EHsc**, 및에서 구조화 된 예외를 throw 할 수 있습니다 **/EHs**, **/EHa**, 또는 **/EHac**합니다.

다음 표에서 여부를 C++ 함수 옵션을 처리 하는 다양 한 컴파일러 예외에서 잠재적으로 throw 할 수 있습니다.

|함수|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|예외 사양이 없는 C++ 함수|예|예|예|예|
|C++함수 `noexcept`하십시오 `noexcept(true)`, 또는 `throw()` 예외 사양|아니요|아니요|예|예|
|C++함수 `noexcept(false)`하십시오 `throw(...)`, 또는 `throw(type)` 예외 사양|예|예|예|예|

## <a name="example"></a>예제

```cpp
// exception_specification.cpp
// compile with: /EHs
#include <stdio.h>

void handler() {
   printf_s("in handler\n");
}

void f1(void) throw(int) {
   printf_s("About to throw 1\n");
   if (1)
      throw 1;
}

void f5(void) throw() {
   try {
      f1();
   }
   catch(...) {
      handler();
    }
}

// invalid, doesn't handle the int exception thrown from f1()
// void f3(void) throw() {
//   f1();
// }

void __declspec(nothrow) f2(void) {
   try {
      f1();
   }
   catch(int) {
      handler();
    }
}

// only valid if compiled without /EHc
// /EHc means assume extern "C" functions don't throw exceptions
extern "C" void f4(void);
void f4(void) {
   f1();
}

int main() {
   f2();

   try {
      f4();
   }
   catch(...) {
      printf_s("Caught exception from f4\n");
   }
   f5();
}
```

```Output
About to throw 1
in handler
About to throw 1
Caught exception from f4
About to throw 1
in handler
```

## <a name="see-also"></a>참고자료

[try, throw 및 catch 문(C++)](../cpp/try-throw-and-catch-statements-cpp.md)<br/>
[C++ 예외 처리](../cpp/cpp-exception-handling.md)