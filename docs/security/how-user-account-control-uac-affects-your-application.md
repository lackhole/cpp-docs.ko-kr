---
title: UAC(사용자 계정 컨트롤)가 애플리케이션에 주는 영향
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 3818b0ff7d4e4c551c41726dd44935beb5d32842
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448481"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>UAC(사용자 계정 컨트롤)가 애플리케이션에 주는 영향

UAC(사용자 계정 컨트롤)는 사용자 계정의 권한을 제한하는 Windows Vista의 기능입니다. UAC에 대한 자세한 정보는 다음 사이트에서 찾아볼 수 있습니다.

- [Developer Best Practices and Guidelines for Applications 최소 권한 환경에서](/windows/desktop/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>UAC를 사용하도록 설정한 후에 프로젝트 빌드

Visual Studio를 작성 하는 경우 C++ 프로젝트 UAC 사용 하 여 Windows Vista에서 사용 하지 않도록 설정 하 고 나중에 UAC를 사용 하면, 정리 하 고 올바르게 작동 하기 위해 프로젝트를 다시 작성 해야 합니다.

## <a name="applications-that-require-administrative-privileges"></a>관리 권한이 필요한 응용 프로그램

기본적으로 시각적 개체 C++ 링커 실행 수준으로 응용 프로그램 매니페스트에 UAC 조각을 포함 `asInvoker`합니다. 관리 권한이 있어야 응용 프로그램이 제대로 실행되는 경우(예: 레지스트리의 HKLM 노드를 수정하거나 Windows 디렉터리와 같은 디스크의 보호된 영역에 쓰는 경우) 응용 프로그램을 수정해야 합니다.

첫 번째 옵션은 수정 하 여 실행 수준을 변경 하려면 매니페스트의 UAC 조각을 *requireAdministrator*합니다. 그러면 응용 프로그램이 실행되기 전에 사용자에게 관리자 자격 증명을 요구합니다. 이 작업을 수행 하는 방법에 대 한 정보를 참조 하세요 [/MANIFESTUAC (매니페스트에 UAC 포함 정보)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md)합니다.

두 번째 옵션은 `/MANIFESTUAC:NO` 링커 옵션을 지정하여 UAC 조각을 매니페스트에 포함하지 않는 것입니다. 이 경우에는 응용 프로그램이 가상화되어 실행됩니다. 레지스트리 또는 파일 시스템의 변경 사항은 응용 프로그램이 종료된 후에 유지되지 않습니다.

다음 순서도는 UAC의 사용 여부와 응용 프로그램에 UAC 매니페스트가 있는지 여부에 따라 응용 프로그램이 어떻게 실행되는지를 설명합니다.

![Windows 로더 동작](media/uacflowchart.png "Windows 로더 동작")

## <a name="see-also"></a>참고자료

[보안 모범 사례](security-best-practices-for-cpp.md)
