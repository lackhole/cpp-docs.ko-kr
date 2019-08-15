---
title: C/C++ 프로그램의 매니페스트 생성 이해
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: 16d5efc5c5f7ce81b4b60269b0c666fd5d24266e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492521"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ 프로그램의 매니페스트 생성 이해

[매니페스트](/windows/win32/sbscs/manifests) 는 외부 xml 파일이 나 응용 프로그램 또는 어셈블리 내에 포함 된 리소스가 될 수 있는 xml 문서입니다. [격리 된 응용 프로그램](/windows/win32/SbsCs/isolated-applications) 의 매니페스트는 런타임에 응용 프로그램을 바인딩해야 하는 공유 side-by-side 어셈블리의 이름과 버전을 관리 하는 데 사용 됩니다. Side-by-side 어셈블리의 매니페스트는 이름, 버전, 리소스 및 기타 어셈블리에 대 한 종속성을 지정 합니다.

격리 된 응용 프로그램 또는 side-by-side 어셈블리에 대 한 매니페스트를 만드는 방법에는 두 가지가 있습니다. 먼저 어셈블리 작성자는 규칙 및 명명 요구 사항에 따라 매니페스트 파일을 수동으로 만들 수 있습니다. 또는 CRT, MFC, ATL 등의 시각적 C++ 어셈블리에만 프로그램이 종속 되는 경우 링커가 자동으로 매니페스트를 생성할 수 있습니다.

시각적 C++ 라이브러리의 헤더에는 어셈블리 정보가 포함 되어 있으며, 라이브러리가 응용 프로그램 코드에 포함 되어 있으면 링커가 최종 이진 파일에 대 한 매니페스트를 구성 하는 데 사용 됩니다. 링커는 매니페스트 파일을 이진 파일 안에 포함 하지 않고 매니페스트를 외부 파일로만 생성할 수 있습니다. 매니페스트를 외부 파일로 사용 하는 경우 일부 시나리오에서는 작동 하지 않을 수 있습니다. 예를 들어, 전용 어셈블리에는 매니페스트를 포함 하는 것이 좋습니다. Nmake를 사용 하 여 코드를 작성 하는 명령줄 빌드에서는 매니페스트 도구를 사용 하 여 매니페스트를 포함할 수 있습니다. 자세한 내용은 [명령줄에서 매니페스트 생성](manifest-generation-at-the-command-line.md)을 참조 하세요. Visual Studio에서 빌드할 때 **프로젝트 속성** 대화 상자에서 매니페스트 도구의 속성을 설정 하 여 매니페스트를 포함할 수 있습니다. [Visual Studio의 매니페스트 생성을](manifest-generation-in-visual-studio.md)참조 하세요.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램 및 side-by-side 어셈블리 개념](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
