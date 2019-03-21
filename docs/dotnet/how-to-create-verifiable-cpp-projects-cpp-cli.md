---
title: '방법: 안정형 c + + 프로젝트 만들기 (C + + /cli CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
ms.openlocfilehash: de3742717bf55c53ab4007aaed18b6ce687fbede
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817381"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>방법: 안정형 c + + 프로젝트 만들기 (C + + /cli CLI)

Visual c + + 응용 프로그램 마법사에서 확인할 수 있는 프로젝트를 만들지 마십시오.

> [!IMPORTANT]
> 사용 되지 않는 visual Studio 2015 및 Visual Studio 2017을 지원 하지 않습니다 합니다 **/clr: pure** 및 **/clr: safe** 검증할 수 있는 프로젝트를 만들 합니다. 검증할 수 있는 코드를 필요로 하는 경우에 C# 코드를 변환 하는 것이 좋습니다.

그러나 지 원하는 Visual c + + 컴파일러 도구 집합의 이전 버전을 사용 하는 경우 **/clr: pure** 및 **/clr: safe**, 프로젝트를 확인할 수로 변환할 수입니다. 이 항목에서는 프로젝트 속성을 설정 하 여 Visual c + + 프로젝트를 확인할 수 있는 응용 프로그램 생성에 변환할 프로젝트 소스 파일을 수정 하는 방법을 설명 합니다.

## <a name="compiler-and-linker-settings"></a>컴파일러 및 링커 설정

기본적으로.NET 프로젝트는 /clr 컴파일러 플래그를 사용 하 고 x86 대상 하드웨어에 링커를 구성 합니다. 안정형 코드 /clr: safe 플래그를 사용 해야 하며 네이티브 기계어 명령 대신 MSIL을 생성 하도록 링커에 지시 해야 합니다.

### <a name="to-change-the-compiler-and-linker-settings"></a>컴파일러 및 링커 설정을 변경 하려면

1. 프로젝트 속성 페이지를 표시 합니다. 자세한 내용은 [컴파일러를 설정 하 고 빌드 속성](../build/working-with-project-properties.md)합니다.

1. 에 **일반** 페이지를 **구성 속성** 노드를 설정 합니다 **공용 언어 런타임 지원** 속성을 **안전 MSIL 공용 언어 런타임 지원 (/: safe)** 합니다.

1. 에 **고급** 페이지의 **링커** 노드를 설정 합니다 **CLR 이미지 형식을** 속성을 **안전 IL 이미지 강제 (/ /clrimagetype: safe)** 합니다.

## <a name="removing-native-data-types"></a>네이티브 데이터 형식을 제거합니다.

이기 때문에 네이티브 데이터 형식을 비안정형 실제로 사용 되지 않는 경우에 네이티브 형식이 포함 된 모든 헤더 파일을 제거 해야 합니다.

> [!NOTE]
> 다음 절차는 Windows Forms 응용 프로그램 (.NET) 및 콘솔 응용 프로그램 (.NET) 프로젝트에 적용 됩니다.

### <a name="to-remove-references-to-native-data-types"></a>네이티브 데이터 형식에 대 한 참조를 제거 하려면

1. Stdafx.h 파일에 모든 항목 주석 처리 합니다.

## <a name="configuring-an-entry-point"></a>구성 진입점

확인할 수 있는 응용 프로그램에서 C 런타임 라이브러리 (CRT)를 사용할 수 없는 때문에 표준 진입점으로 main 함수를 호출 하는 데 CRT 종속 수 없습니다. 즉, 제공 해야 하는 명시적으로 링커를 처음 호출할 함수의 이름입니다. (이 경우 main ()는 CRT 되지 않은 진입점을 나타내는 데 main () 또는 _tmain 대신 사용 됩니다 있지만이 이름은 임의의 있으므로 진입점을 명시적으로 지정 해야 합니다.)

> [!NOTE]
> 다음 절차는 콘솔 응용 프로그램 (.NET) 프로젝트에 적용 합니다.

#### <a name="to-configure-an-entry-point"></a>진입점을 구성 하려면

1. _Tmain 프로젝트의 주.cpp 파일에서 main ()를 변경 합니다.

1. 프로젝트 속성 페이지를 표시 합니다. 자세한 내용은 [컴파일러를 설정 하 고 빌드 속성](../build/working-with-project-properties.md)합니다.

1. 에 **고급** 페이지를 **링커** 노드를 입력 `Main` 으로 **진입점** 속성 값입니다.

## <a name="see-also"></a>참고자료

- [순수형 및 안정형 코드(C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
