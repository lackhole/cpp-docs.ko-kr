---
title: 링커 입력 파일로 사용하는 .netmodule 파일
ms.date: 11/04/2016
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: fcba363cff567c69ac0fbd0a541953dfe2c8e910
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818104"
---
# <a name="netmodule-files-as-linker-input"></a>링커 입력 파일로 사용하는 .netmodule 파일

link.exe에서는 이제 MSIL .obj 및 .netmodules가 입력으로 사용됩니다. 링커에 의해 생성 된 출력 파일이 의존 하지 않는 런타임.obj 또는 링커에 입력 된.netmodules에.netmodule 또는 어셈블리.

.netmodules MSVC 컴파일러에 의해 만들어집니다 [/LN (MSIL 모듈 만들기)](ln-create-msil-module.md) 또는 사용 하 여 링커에 의해 [/NOASSEMBLY (MSIL 모듈 만들기)](noassembly-create-a-msil-module.md)합니다. 컴파일한 후.objs Visual c + + 컴파일에서 항상 만들어집니다. 다른 Visual Studio 컴파일러를 사용 합니다 **/target: module** 컴파일러 옵션입니다.

에 전달 해야 링커.obj 파일 Visual c + + 컴파일에서.netmodule를 생성 합니다. .Netmodule를 전달 하기 때문에 더 이상 지원 되지 합니다 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않는 합니다.

명령줄에서 링커를 실행 하는 방법에 대 한 자세한 내용은 [링커 명령줄 구문](linking.md)를 [명령줄에서 MSVC 도구 집합을 사용 하 여](../building-on-the-command-line.md), 및 [경로 및 환경 변수 설정 명령줄 빌드에 대 한](../setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

MSVC 컴파일러를 사용 하 여 서 컴파일된 링커에.netmodule 또는.dll 파일을 전달 **/clr** 링커 오류가 발생할 수 있습니다. 자세한 내용은 [.netmodule 입력 파일 형식 선택](choosing-the-format-of-netmodule-input-files.md)합니다.

로 컴파일된 MSIL.obj 파일 뿐만 아니라 네이티브.obj 파일을 허용 하는 링커 **/clr**합니다. 동일한 빌드에서 혼합된 컴파일한 후.objs를 전달 하는 경우 결과 출력 파일의 검증 가능성은 기본적으로 같아야 가장 낮은 수준의 검증 가능성 입력 모듈.

현재 두 개 이상의 어셈블리로 구성된 응용 프로그램이 있고 이 응용 프로그램을 하나의 어셈블리에 포함하려면 어셈블리를 다시 컴파일한 후 .objs 또는 .netmodules를 링크하여 단일 어셈블리를 생성해야 합니다.

사용 하 여 항목을 지정 해야 합니다 [/ENTRY (진입점 기호)](entry-entry-point-symbol.md) 실행 가능 이미지를 만들 때.

MSIL.obj 또는.netmodule 파일에 연결 하는 경우 사용 하 여 [/LTCG (링크 타임 코드 생성)](ltcg-link-time-code-generation.md), 그렇지 않으면 링커에서 MSIL.obj 또는.netmodule를 발견 하면, 다시 시작 됩니다 /LTCG을 사용해 서 링크 합니다.

MSIL .obj 또는 .netmodule 파일은 cl.exe로도 전달할 수 있습니다.

입력 MSIL .obj 또는 .netmodule 파일은 포함된 리소스를 가질 수 없습니다. 리소스를 사용 하 여 출력 파일 (모듈 또는 어셈블리)에 포함 된 [/ASSEMBLYRESOURCE (관리 되는 리소스 포함)](assemblyresource-embed-a-managed-resource.md) 링커 옵션 또는 합니다 **/resource** 다른 Visual Studio 컴파일러에서 컴파일러 옵션입니다.

MSIL 링크를 수행 하는 경우 및도 지정 하지 않는 경우 [/LTCG (링크 타임 코드 생성)](ltcg-link-time-code-generation.md), 링크를 다시 시작 되는 정보 메시지가 표시 됩니다. 이 메시지를 MSIL 링크를 사용 하 여 링커 성능이 향상 되지만 무시, 명시적으로 지정할 **/LTCG**합니다.

## <a name="example"></a>예제

C + + 코드에서를 **catch** 는 해당 블록 **시도** 비 시스템 예외에 대해 호출 됩니다. 그러나 기본적으로 CLR 예외를 래핑합니다 비시스템와 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>합니다. 경우 어셈블리는 Visual c + + 및 비-Visual c + + 모듈에서 생성 되 고 원하는 **catch** c + + 코드에서 해당 호출에서 차단 **시도** 절 때는 **시도**비시스템 예외를 throw 하는 블록을 추가 해야 합니다 `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` 아닌 c + + 모듈에 대 한 소스 코드에 특성입니다.

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

부울 값을 변경 하 여는 `WrapNonExceptionThrows` Visual c + + 코드의 비시스템 예외를 catch 하는 기능을 수정할 특성입니다.

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

## <a name="see-also"></a>참고자료

- [LINK 입력 파일](link-input-files.md)
- [MSVC 링커 옵션](linker-options.md)
