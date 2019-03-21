---
title: 순수형 및 안정형 코드(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
ms.openlocfilehash: 66f3b5a33791d20297cde6e6223ba65189a99682
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743836"
---
# <a name="pure-and-verifiable-code-ccli"></a>순수형 및 안정형 코드 (C + + /cli CLI)

.NET 프로그래밍, Visual Studio 2017에서 Visual c + +를 사용 하 여 혼합형된 어셈블리 만들기를 지원 합니다 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다. 합니다 **/clr: pure** 및 **: safe** 옵션은 Visual Studio 2015에서 더 이상 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다. 경우에 코드에 안전한 지 확인할 수 있어야 다음을 포팅하는 것이 좋습니다 C#입니다.

## <a name="mixed-clr"></a>혼합 (/ clr)

혼합형 어셈블리 (컴파일된 **/clr**), 관리 되지 않는 모두 포함 하 고.NET 기능을 사용할 수 있도록 관리 되는 파트에는 있지만 네이티브 코드가 포함 되어 있습니다. 이렇게 하면 응용 프로그램 및 구성 요소를 업데이트할 전체 프로젝트를 다시 작성 하지 않고도.NET 기능을 사용할 수 있습니다. 이 방식으로 관리 및 네이티브 코드를 혼합 하려면 Visual c + +를 사용 하 여 c + + Interop 호출 됩니다. 자세한 내용은 [혼합형 (네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 하 고 [네이티브 및.NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)합니다.

P/Invoke를 통해 네이티브 Dll로 관리 되는 어셈블리에서 호출을 컴파일되지 있지만 보안 설정에 따라 런타임에 실패할 수 있습니다.

컴파일러는 전달 하지만 결과 확인할 수 없는 어셈블리를 코딩 시나리오 중 하나는: 범위 확인 연산자를 사용 하 여 개체 인스턴스를 통해 가상 함수를 호출 합니다.  예: `MyObj -> A::VirtualFunction();`

## <a name="see-also"></a>참고자료

- [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
