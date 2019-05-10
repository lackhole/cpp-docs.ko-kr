---
title: 혼합형(네이티브 및 관리) 어셈블리
ms.date: 09/18/2018
helpviewer_keywords:
- interop [C++], mixed assemblies
- /clr compiler option [C++], mixed assemblies
- managed code [C++], interoperability
- interoperability [C++], mixed assemblies
- mixed DLL loading [C++]
- mixed assemblies [C++], about mixed assemblies
- assemblies [C++], mixed
- mixed assemblies [C++]
- native code [C++], .NET interoperatibility
ms.assetid: 4299dfce-392f-4933-8bf0-5da2f0d1c282
ms.openlocfilehash: 043390a2ebefcadac300b7fb0b05ae7f5ed411f3
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447294"
---
# <a name="mixed-native-and-managed-assemblies"></a>혼합형된 (네이티브 및 관리) 어셈블리

혼합형된 어셈블리는 관리 되지 않는 컴퓨터 지침과 MSIL 명령이 포함 될 수 있습니다. 호출 하 여 네이티브를 사용 하 여 호환성을 유지 하면서.NET 구성 요소에서 호출할 수 있도록 C++ 라이브러리입니다. 혼합형된 어셈블리를 사용 하 여, 작성 하는.NET 및 네이티브 혼합을 사용 하 여 응용 프로그램 C++ 코드입니다.

네이티브 완전히 구성 된 기존 라이브러리 예를 들어, C++ 코드 제공 될 수 있습니다.NET 플랫폼을 사용 하 여 하나의 모듈을 다시 컴파일하여 합니다 **/clr** 컴파일러 스위치입니다. 이 모듈 다음.NET 기능을 사용할 수 있지만 나머지 응용 프로그램의 호환성이 유지 됩니다. 동일한 파일 내에서 함수에서 함수 별로 관리 및 네이티브 컴파일을 선택할 수도 (참조 [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md)).

Visual C++ 만 사용 하 여 혼합 된 관리 되는 어셈블리의 생성을 지원 합니다 **/clr** 컴파일러 옵션입니다. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 지원 중단 예정이고 Visual Studio 2017에서는 지원되지 않습니다. 순수 이미지나 검증할 수 있는 관리 되는 어셈블리를 필요로 하는 경우에 C#을 사용 하 여 만든 것이 좋습니다.

이전 버전의 Microsoft C++ 컴파일러 도구 집합 세 가지 유형의 관리 되는 어셈블리의 생성을 지원 합니다: 혼합형, 순수형 및 안정형 합니다. 후자의 두에 설명 되어 [순수형 및 안정형 코드 (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.

## <a name="in-this-section"></a>단원 내용

[방법: /Clr으로 마이그레이션](../dotnet/how-to-migrate-to-clr.md)<br/>
도입 하거나 응용 프로그램에서.NET 기능을 업그레이드 하는 권장된 단계를 설명 합니다.

[방법: MFC 및 ATL 코드 사용 하 여 /clr 컴파일](../dotnet/how-to-compile-mfc-and-atl-code-by-using-clr.md)<br/>
공용 언어 런타임을 대상으로 기존 MFC 및 ATL 프로그램을 컴파일하는 방법에 설명 합니다.

[혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)<br/>
"로더 잠금" 문제 및 해결 방법에 설명합니다.

[혼합형 어셈블리에 대한 라이브러리 지원](../dotnet/library-support-for-mixed-assemblies.md)<br/>
네이티브 라이브러리를 사용 하는 방법에 설명 **/clr** 컴파일.

[성능 고려 사항](../dotnet/performance-considerations-for-interop-cpp.md)<br/>
혼합형된 어셈블리와 데이터 마샬링을의 성능에 미치는 영향을 설명합니다.

[애플리케이션 도메인 및 Visual C++](../dotnet/application-domains-and-visual-cpp.md)<br/>
시각적 개체에 설명 C++ 응용 프로그램 도메인에 대 한 지원.

[이중 썽킹](../dotnet/double-thunking-cpp.md)<br/>
관리 되는 함수에 대 한 기본 진입점의 성능에 미치는 영향에 설명 합니다.

[/Clr을 사용한 CLR 종료 하면 사용 빌드한 COM 개체에서 예외를 방지](../dotnet/avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr.md)<br/>
사용 하 여 컴파일된 COM 개체를 사용 하는 관리 되는 응용 프로그램을 올바르게 종료 하는 방법에 설명 **/clr**합니다.

[방법: CRT 라이브러리 DLL에 대한 종속성을 제거하여 부분적으로 신뢰할 수 있는 애플리케이션 만들기](../dotnet/create-a-partially-trusted-application.md)<br/>
시각적 개체를 사용 하 여 부분적으로 신뢰할 수 있는 공용 언어 런타임 응용 프로그램을 만드는 방법에 설명 C++ msvcm90.dll에 대 한 종속성을 제거 하 여 합니다.

혼합형된 어셈블리에 대 한 지침을 코딩 하는 방법에 대 한 자세한 내용은 MSDN 문서를 참조 하세요 [An 개요의 관리/비관리 코드 상호 운용성](https://msdn.microsoft.com/library/ms973872.aspx)합니다.

## <a name="see-also"></a>참고자료

- [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)
