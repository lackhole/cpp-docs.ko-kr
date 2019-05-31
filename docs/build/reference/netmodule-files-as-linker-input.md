---
title: 링커 입력 파일로 사용하는 .netmodule 파일
ms.date: 05/16/2019
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: 50a0f0a1ff5f65a7512e8372de2fe5296c866dca
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837434"
---
# <a name="netmodule-files-as-linker-input"></a>링커 입력 파일로 사용하는 .netmodule 파일

link.exe에서는 이제 MSIL .obj 및 .netmodules가 입력으로 사용됩니다. 링커에서 생성되는 출력 파일은 링커에 입력된 .obj 또는 .netmodules에 대해 런타임 종속성이 없는 .netmodule 또는 어셈블리입니다.

.netmodules은 MSVC 컴파일러에서 [/LN (Create MSIL Module)](ln-create-msil-module.md) 또는 링커에서 [/NOASSEMBLY (Create a MSIL Module)](noassembly-create-a-msil-module.md)를 통해 만들어집니다. .objs는 항상 Visual C++ 컴파일에서 생깁니다. 다른 Visual Studio 컴파일러의 경우 **/target: module** 컴파일러 옵션을 사용합니다.

.netmodule을 만든 Visual C++ 컴파일의 .obj 파일을 링커에 전달해야 합니다. .netmodule 전달은 더 이상 지원되지 않습니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않으며 Visual Studio 2017 이상에서는 지원되지 않기 때문입니다.

명령줄에서 링커를 실행하는 방법에 대한 정보는 [링커 명령줄 구문](linking.md), [명령줄에서 MSVC 도구 집합 사용](../building-on-the-command-line.md) 및 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요.

**/clr**을 사용해서 MSVC 컴파일러에서 컴파일한 링커에 .netmodule 또는 .dll 파일을 전달하면 링커 오류가 발생할 수 있습니다. 자세한 정보는 [.netmodule 입력 파일 형식 선택](choosing-the-format-of-netmodule-input-files.md)을 참조하세요.

링커는 네이티브 .obj 파일과 **/clr**로 컴파일된 MSIL .obj 파일을 모두 허용합니다. 동일한 빌드에서 혼합된 .obj를 전달할 경우, 기본적으로 결과 출력 파일의 검증 가능성은 입력 모듈의 가장 낮은 검증 가능성 수준과 동일합니다.

현재 두 개 이상의 어셈블리로 구성된 응용 프로그램이 있고 이 응용 프로그램을 하나의 어셈블리에 포함하려면 어셈블리를 다시 컴파일한 후 .objs 또는 .netmodules를 링크하여 단일 어셈블리를 생성해야 합니다.

실행 가능 이미지를 만들 때 [/ENTRY(진입점 기호)](entry-entry-point-symbol.md)를 사용하여 진입점을 지정해야 합니다.

MSIL .obj 또는 .netmodule 파일로 링크할 때는 [/LTCG(링크 타임 코드 생성)](ltcg-link-time-code-generation.md)를 사용합니다. 그렇지 않으면 링커에서 MSIL .obj 또는 .netmodule이 발견될 때 /LTCG를 사용해서 링크를 다시 시작합니다.

MSIL .obj 또는 .netmodule 파일은 cl.exe로도 전달할 수 있습니다.

입력 MSIL .obj 또는 .netmodule 파일은 포함된 리소스를 가질 수 없습니다. 다른 Visual Studio 컴파일러에서는 리소스가 [/ASSEMBLYRESOURCE(관리되는 리소스 포함)](assemblyresource-embed-a-managed-resource.md) 링커 옵션이나 **/resource** 컴파일러 옵션을 통해 출력 파일(모듈 또는 어셈블리)에 포함됩니다.

MSIL 연결을 수행하며 [/LTCG(링크 타임 코드 생성)](ltcg-link-time-code-generation.md)를 지정하지 않은 경우 링크가 다시 시작됩니다. 이 메시지는 무시할 수 있으나 MSIL 연결에서 링커 성능을 높이려면 명시적으로 **/LTCG**를 지정합니다.

## <a name="example"></a>예제

C++ 코드에서 해당 **try**의 **catch** 블록은 비 시스템 예외에 대해 호출됩니다. 그러나 기본적으로 CLR은 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>으로 비 시스템 예외를 래핑합니다. Visual C++ 및 비 Visual C++ 모듈에서 어셈블리를 만들고, **try** 블록이 비 시스템 예외를 throw하면 C++의 **catch** 블록을 해당 **try** 문에서 호출하려 할 때 비 C++ 모듈에 대한 소스 코드에 `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` 특성을 추가해야 합니다.

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

## <a name="example"></a>예제

`WrapNonExceptionThrows` 특성의 부울 값을 변경하면 Visual C++ 코드의 기능을 비 시스템 예외를 catch하게 수정합니다.

```cpp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>참고 항목

- [LINK 입력 파일](link-input-files.md)
- [MSVC 링커 옵션](linker-options.md)
