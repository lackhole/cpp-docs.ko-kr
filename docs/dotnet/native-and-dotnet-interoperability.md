---
title: 네이티브 및 .NET 상호 운용성
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++]
- .NET Framework [C++], interoperability with Visual C++
- interoperability [C++], about .NET interoperability
- interop [C++], about .NET interoperability
- managed code [C++], interoperability
- native code [C++]
- interoperability [C++]
- MFC [C++], .NET integration
- unmanaged code interoperability [C++]
- Visual C++, interoperability
- native code [C++], .NET interoperatibility
ms.assetid: f3ec6c99-c745-4256-b95b-f1d12ba17a5a
ms.openlocfilehash: 486796e404ad1aee39fbeb85251d26cc078b1160
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237148"
---
# <a name="native-and-net-interoperability"></a>네이티브 및 .NET 상호 운용성

Visual C++에서는 동일한 어셈블리 및 동일한 파일 내에서 관리되는 구문과 관리되지 않는 구문이 공존하고 상호 운용될 수 있도록 하는 상호 운용성 기능을 지원합니다. 이 기능의 작은 부분 집합인 P/Invoke와 같은 기능은 다른 .NET 언어에서도 지원되지만, Visual C++에서 제공하는 상호 운용성 지원의 대부분은 다른 언어에서 사용할 수 없습니다.

## <a name="in-this-section"></a>섹션 내용

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
관리되는 기능과 관리되지 않는 기능을 모두 포함하는 [/clr(공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 사용하여 생성한 어셈블리에 대해 설명합니다.

[MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
MFC Windows Forms 지원 클래스를 사용하여 MFC 응용 프로그램 내에서 Windows Forms 컨트롤을 호스팅하는 방법에 대해 설명합니다.

[관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)<br/>
.NET 응용 프로그램에서 CLR가 아닌 DLL을 사용하는 방법에 대해 설명합니다.
