---
title: Debug 클래스(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: 3a262a0d2ef429cb94f4648eb7c7180e7b130279
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393781"
---
# <a name="debug-class-ccli"></a>Debug 클래스(C++/CLI)

Visual C++ 어플리케이션에서 <xref:System.Diagnostics.Debug> 클래스를 사용하더라도, 디버그 빌드와 릴리스 빌드 모두 똑같이 동작합니다.

## <a name="remarks"></a>설명

<xref:System.Diagnostics.Trace> 클래스가 수행하는 기능은 Debug 클래스가 수행하는 기능과 동일합니다. 하지만, `#ifdef` 클래스는 TRACE 심볼의 정의 여부에 의존적입니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

아래의 샘플은 **/DDEBUG** 또는 **/DTRACE** 옵션을 사용하여 컴파일하더라도, 항상 출력문을 수행한다는것을 보여줍니다.

### <a name="code"></a>코드

```cpp
// mcpp_debug_class.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
   Trace::Unindent();

   Debug::WriteLine("test");
}
```

### <a name="output"></a>출력

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example"></a>예제

### <a name="description"></a>설명

예상했던 동작을 얻고 싶은 경우(즉, 릴리스 빌드에서 "test" 라는 결과가 출력되지 않게 하려면), `#ifdef` 지시문이나 `#endif` 지시문을 사용해야 합니다. 바로 이전의 샘플 코드가 바로 아래 예제의 해결 방법을 보여주는 예제였습니다.

### <a name="code"></a>코드

```cpp
// mcpp_debug_class2.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();

#ifdef TRACE   // checks for a debug build
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
#endif
   Trace::Unindent();

#ifdef DEBUG   // checks for a debug build
   Debug::WriteLine("test");
#endif   //ends the conditional block
}
```

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
