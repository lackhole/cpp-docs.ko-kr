---
title: C/C++ 프로그램의 매니페스트 생성 이해
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: ff8d9f214b4fe4d004691c54474dcdabf2c0af85
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807353"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>C/C++ 프로그램의 매니페스트 생성 이해

A [매니페스트](/windows/desktop/sbscs/manifests) 외부 XML 파일 또는 리소스를 지정할 수 있는 XML 문서에 포함 된 응용 프로그램 또는 어셈블리입니다. 매니페스트를 [격리 된 응용 프로그램](/windows/desktop/SbsCs/isolated-applications) 이름과는 응용 프로그램이 런타임에 바인딩해야 하는 공유 side-by-side-어셈블리의 버전을 관리 하는 데 사용 됩니다. Side-by-side-어셈블리의 매니페스트는 이름, 버전, 리소스 및 다른 어셈블리에서 해당 종속성을 지정합니다.

격리 된 응용 프로그램 또는 side-by-side-어셈블리에 대 한 매니페스트를 만드는 두 가지가 있습니다. 먼저 어셈블리의 작성자는 규칙 및 명명 요구 사항에 매니페스트 파일을 수동으로 만들 수 있습니다. 또는 에서만 프로그램이 CRT, MFC, ATL 또는 다른 사용자와 같은 Visual c + + 어셈블리에 종속 하는 경우 다음 매니페스트를 생성할 수 있습니다 자동으로 링커에 의해.

어셈블리 정보를 포함 하는 Visual c + + 라이브러리의 헤더 및 라이브러리는 응용 프로그램 코드에 포함 되어,이 어셈블리 정보는 링커에서 사용 하는 최종 이진에 대 한 매니페스트를 합니다. 링커에서 매니페스트 파일 이진을 포함 하지 않습니다 하 고 외부 파일로 매니페스트를 생성할 수 있습니다. 외부 파일로 매니페스트를 가진 모든 시나리오에 대해 작동 하지 않습니다. 예를 들어, 전용 어셈블리 매니페스트를 포함 하는 것이 좋습니다. Nmake를 사용 하 여 코드를 작성 하는 것과 같은 명령줄 빌드에서 매니페스트 포함 될 수 있습니다; 매니페스트 도구를 사용 하 여 자세한 내용은 참조 [명령줄에서 매니페스트 생성](manifest-generation-at-the-command-line.md)합니다. 매니페스트 도구에 대 한 속성을 설정 하 여 매니페스트를 포함할 수을 Visual Studio에서 빌드하는 경우는 **프로젝트 속성** 대화 상자, 참조 [Visual Studio에서 매니페스트 생성](manifest-generation-in-visual-studio.md)합니다.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램 및 side-by-side 어셈블리 개념](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
