---
title: __clrcall
ms.date: 11/04/2016
f1_keywords:
- __clrcall_cpp
helpviewer_keywords:
- __clrcall keyword [C++]
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
ms.openlocfilehash: bc44feb97223de47f45734f75777ee040d0ebdd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364573"
---
# <a name="clrcall"></a>__clrcall

**Microsoft 전용**

관리 코드에서만 함수를 호출할 수 있도록 지정합니다.  사용 하 여 **__clrcall** 관리 코드에서 호출 되는 모든 가상 함수에 대 한 합니다. 그러나 네이티브 코드에서 호출되는 함수에는 이 호출 규칙을 사용할 수 없습니다.

사용 하 여 **__clrcall** 성능을 향상 시키기 위해 관리 되는 가상 함수를 관리 되는 함수 또는 관리 되는 함수 포인터를 통해 관리 되는 함수를 호출 하는 경우.

진입점은 컴파일러에서 생성된 별도의 함수입니다. 함수에 네이티브 진입점과 관리되는 진입점이 둘 다 있을 경우 둘 중 하나는 함수 구현이 포함된 실제 함수입니다. 다른 함수는 실제 함수를 호출하고 공용 언어 런타임에서 PInvoke를 수행하게 하는 별도의 함수(썽크)입니다. 함수를 표시 하는 경우 **__clrcall**에 함수 구현이 MSIL 이어야 하 여 네이티브 진입점 함수가 생성 되지 것입니다 나타냅니다.

경우에 네이티브 함수의 주소를 가져올 때 **__clrcall** 지정 하지 않으면 컴파일러가 네이티브 진입점을 사용 합니다. **__clrcall** 은 함수가 관리 되며에서 전환을 통해 이동 하지 않고도 기본 관리는 나타냅니다. 이 경우 컴파일러가 관리되는 진입점을 사용합니다.

때 `/clr` (하지 `/clr:pure` 또는 `/clr:safe`)는 및 **__clrcall** 는 네이티브 진입점 함수 주소를 반환 함수의 주소를 항상 수행 사용 되지 않습니다. 때 **__clrcall** 는 사용, 네이티브 진입점 함수는 만들어지지 않으므로 하지는 진입점 썽크 함수가 관리 되는 함수의 주소를 가져옵니다. 자세한 내용은 [이중 썽킹](../dotnet/double-thunking-cpp.md)합니다. **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

[/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 모든 함수와 함수 포인터는 의미 **__clrcall** 컴파일러 이외의표시할compiland안의함수를허용하지것입니다 **__clrcall**합니다. 때 **/clr: pure** 사용 됩니다 **__clrcall** 함수 포인터와 외부 선언에만 지정할 수 있습니다.

직접 호출할 수 있습니다 **__clrcall** 기존 계획에서 함수 C++ 를 사용 하 여 컴파일된 코드 **/clr** 함수에 MSIL 구현이 하기만 합니다. **__clrcall** 이러한 함수를 사용 하 여 컴파일되는 경우에 인라인 asm 및 예를 들어 CPU 별 intrinisics를 호출 하는 함수에서 직접 함수를 호출할 수 없습니다 `/clr`합니다.

**__clrcall** 함수 포인터는 생성 된 응용 프로그램 도메인으로 사용 하려는 합니다.  전달 하는 대신 **__clrcall** 응용 프로그램 도메인 간에 대 한 포인터를 함수를 사용 하 여 <xref:System.CrossAppDomainDelegate>입니다. 자세한 내용은 [응용 프로그램 도메인 및 시각적 개체 C++ ](../dotnet/application-domains-and-visual-cpp.md)합니다.

## <a name="example"></a>예제

함수를 사용 하 여 선언 되 면 사용자에 게 유의 **__clrcall**, 필요할 때 코드를 생성할; 함수가 호출 될 때 예를 들어 있습니다.

```cpp
// clrcall2.cpp
// compile with: /clr
using namespace System;
int __clrcall Func1() {
   Console::WriteLine("in Func1");
   return 0;
}

// Func1 hasn't been used at this point (code has not been generated),
// so runtime returns the adddress of a stub to the function
int (__clrcall *pf)() = &Func1;

// code calls the function, code generated at difference address
int i = pf();   // comment this line and comparison will pass

int main() {
   if (&Func1 == pf)
      Console::WriteLine("&Func1 == pf, comparison succeeds");
   else
      Console::WriteLine("&Func1 != pf, comparison fails");

   // even though comparison fails, stub and function call are correct
   pf();
   Func1();
}
```

```Output
in Func1
&Func1 != pf, comparison fails
in Func1
in Func1
```

## <a name="example"></a>예제

다음 샘플에서는 함수 포인터를 정의하고 관리 코드에서만 함수 포인터를 호출할 수 있도록 선언합니다. 여기서는 컴파일러가 관리되는 함수를 직접 호출하고 네이티브 진입점(이중 썽크 문제)을 방지할 수 있습니다.

```cpp
// clrcall3.cpp
// compile with: /clr
void Test() {
   System::Console::WriteLine("in Test");
}

int main() {
   void (*pTest)() = &Test;
   (*pTest)();

   void (__clrcall *pTest2)() = &Test;
   (*pTest2)();
}
```

## <a name="see-also"></a>참고자료

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)
