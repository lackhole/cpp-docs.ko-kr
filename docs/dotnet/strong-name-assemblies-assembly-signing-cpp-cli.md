---
title: 강력한 이름 어셈블리(어셈블리 서명)(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: ac46d069ece3c75af93f93497169d054b45267d0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813931"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>강력한 이름 어셈블리(어셈블리 서명)(C++/CLI)

이 항목에서는 라고도 어셈블리에 강력한 이름을 지정 하 여 어셈블리를 서명할 수 하는 방법을 설명 합니다.

## <a name="remarks"></a>설명

Visual c + +를 사용 하면 서명 된 어셈블리에 대 한 CLR 특성을 관련 된 문제를 방지 하려면 어셈블리에 서명할 링커 옵션을 사용 합니다.

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

특성을 사용 하지 않는 이유는 키 이름을 파일 이름 기밀 정보를 포함 하는 경우 보안상 위험할 수 있는 어셈블리 메타 데이터에서 볼 수 있다는 사실을 포함 합니다. 또한 Visual c + + 개발 환경에서 사용 하는 빌드 프로세스는 어셈블리가 서명 되 고 CLR 특성을 사용 하 여 어셈블리에 강력한 이름을 지정 하 고 다음 어셈블리에 mt.exe 같은 사후 처리 도구를 실행 하는 경우 키를 무효화 됩니다.

명령줄에서 빌드, 링커 옵션을 사용 하 여 어셈블리를 서명 하 고 다음 후 처리 (예: mt.exe) 도구를 실행 하는 경우에 sn.exe 사용 하 여 어셈블리에 다시 서명 해야 합니다. 또는 빌드 및 어셈블리 서명을 연기 하 완료 후 처리 도구를 실행 한 후 서명 합니다.

Sn.exe를 명시적으로 호출 하 여 어셈블리를 성공적으로 서명할 수 개발 환경에서 빌드할 때 서명 특성을 사용 하는 경우 ([Sn.exe (강력한 이름 도구)](/dotnet/framework/tools/sn-exe-strong-name-tool)) 빌드 후 이벤트에서입니다. 자세한 내용은 [빌드 이벤트 지정](../build/specifying-build-events.md)을 참조하세요. 특성 및 링커 옵션을 사용 하 여 비교할 빌드 후 이벤트를 사용 하는 경우 빌드 시간 작을 수 있습니다.

다음 링커 옵션은 어셈블리 서명를 지원 합니다.

- [/DELAYSIGN(어셈블리에 부분적으로 서명)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER(어셈블리에 서명할 키 컨테이너 지정)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

강력한 이름의 어셈블리에 대 한 자세한 내용은 참조 하세요. [강력한 어셈블리 만들기 및 사용](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)합니다.

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
