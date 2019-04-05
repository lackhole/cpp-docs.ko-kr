---
title: 문자열화 연산자 (#)
ms.date: 11/04/2016
f1_keywords:
- '#'
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
ms.openlocfilehash: 4f23eea017197ae1f984e097bb3967c1228fef09
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035717"
---
# <a name="stringizing-operator-"></a>문자열화 연산자 (#)

숫자 기호 또는 "문자열 화" 연산자 (**#**) 매크로 매개 변수를 매개 변수 정의 확장 하지 않고 문자열 리터럴로 변환 합니다. 인수를 사용하는 매크로에만 사용됩니다. 매크로 호출이 전달하는 실제 인수가 매크로 정의에서 형식 매개 변수 앞에 나오는 경우, 해당 인수는 따옴표로 묶이고 문자열 리터럴로 취급됩니다. 해당 문자열 리터럴은 매크로 정의에서 문자열화된 연산자와 형식적 매개 변수의 조합이 발생할 때마다 이를 대체합니다.

> [!NOTE]
> 예전에 확장된 매크로 형식 인수가 문자열 리터럴 및 문자 상수 내부에 표시되던 Microsoft C(6.0 및 이전 버전) ANSI C 표준 확장은 더 이상 지원되지 않습니다. 문자열 화를 사용 하 여이 확장에 의존 하는 코드를 다시 작성할 수 (**#**) 연산자.

실제 인수의 첫 번째 토큰 앞에 오는 공백 및 실제 인수의 마지막 토큰 뒤에 오는 공백은 무시됩니다. 실제 인수의 토큰 사이의 공백은 결과 문자열 리터럴에서 단일 공백으로 줄어듭니다. 따라서 실제 인수의 두 토큰 사이에 주석이 있을 경우 해당 주석은 단일 공백으로 줄어듭니다. 결과 문자열 리터럴은 공백으로만 구분된 모든 인접 문자열 리터럴을 자동으로 연결한 것입니다.

일반적으로 인수에 포함 된 문자가 문자열 리터럴을 사용 하는 경우 이스케이프 시퀀스를 필요로 하는 경우 (예를 들어, 인용 부호 (**"**) 또는 백슬래시 (**\\**) 문자), 필요한 이스케이프 백슬래시가 해당 문자 앞 자동으로 삽입 됩니다.

Visual c + + 문자열 화 연산자에 사용 되는 문자열 이스케이프 시퀀스를 포함 하는 경우 제대로 작동 하지 않습니다. 이 경우 컴파일러에서 생성 [컴파일러 오류 C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md)합니다.

## <a name="examples"></a>예제

다음 예제에서는 매크로를 호출하는 문자열화 연산자 및 main 함수 호출을 포함하는 매크로 정의를 보여 줍니다.

이러한 호출은 전처리가 수행되는 동안 확장되어 다음 코드를 만듭니다.

```cpp
int main() {
   printf_s( "In quotes in the printf function call\n" "\n" );
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );
}
```

```cpp
// stringizer.cpp
#include <stdio.h>
#define stringer( x ) printf_s( #x "\n" )
int main() {
   stringer( In quotes in the printf function call );
   stringer( "In quotes when printed to the screen" );
   stringer( "This: \"  prints an escaped double quote" );
}
```

```Output
In quotes in the printf function call
"In quotes when printed to the screen"
"This: \"  prints an escaped double quote"
```

다음 예제에서는 매크로 매개 변수를 확장하는 방법을 보여 줍니다.

```cpp
// stringizer_2.cpp
// compile with: /E
#define F abc
#define B def
#define FB(arg) #arg
#define FB1(arg) FB(arg)
FB(F B)
FB1(F B)
```

## <a name="see-also"></a>참고자료

[전처리 연산자](../preprocessor/preprocessor-operators.md)