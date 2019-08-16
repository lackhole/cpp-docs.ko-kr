---
title: C/C++ 격리된 애플리케이션 빌드
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: fbb553e3514ac3c32ee1e1f276dcb3e43d3a192e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493340"
---
# <a name="building-cc-isolated-applications"></a>C/C++ 격리된 애플리케이션 빌드

격리 된 응용 프로그램은 side-by-side 어셈블리에만 종속 되며 매니페스트를 사용 하 여 해당 종속성에 바인딩합니다. Windows에서 제대로 실행 하기 위해 응용 프로그램을 완전히 격리 하는 것은 필요 하지 않습니다. 그러나 응용 프로그램을 완벽 하 게 격리 하는 데 투자 하 여 나중에 응용 프로그램을 서비스 해야 하는 경우 시간을 절약할 수 있습니다. 응용 프로그램을 완벽 하 게 격리 하는 이점에 대 한 자세한 내용은 [격리 된 응용 프로그램](/windows/win32/SbsCs/isolated-applications)을 참조 하세요.

Visual Studio를 사용 하 여 네이티브C++ C/응용 프로그램을 빌드하는 경우 기본적으로 visual studio 프로젝트 시스템은 visual studio 라이브러리에 대 한 응용 프로그램의 종속성을 설명 하는 매니페스트 파일을 생성 합니다. 이러한 종속성이 응용 프로그램의 유일한 종속성 인 경우 Visual Studio를 사용 하 여 다시 작성 하는 즉시 격리 된 응용 프로그램이 됩니다. 응용 프로그램에서 런타임에 다른 라이브러리를 사용 하는 경우 [C/C++ side-by-side 어셈블리 빌드](building-c-cpp-side-by-side-assemblies.md)에 설명 된 단계에 따라 이러한 라이브러리를 side-by-side 어셈블리로 다시 빌드해야 할 수 있습니다.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램 및 side-by-side 어셈블리 개념](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
