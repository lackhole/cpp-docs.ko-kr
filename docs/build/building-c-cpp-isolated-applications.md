---
title: C/C++ 격리된 응용 프로그램 빌드
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: 42192ad9388a8e69b70947c20c6fa7ee428a2bb9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220965"
---
# <a name="building-cc-isolated-applications"></a>C/C++ 격리된 응용 프로그램 빌드

격리 된 응용 프로그램 side-by-side-어셈블리에만 의존 하 고 매니페스트를 사용 하 여 해당 종속성을 바인딩합니다. Windows;에서 제대로 실행 하기 위해 완전히 격리 된 응용 프로그램에 필요 하지 않습니다. 그러나 완전히 격리 된 응용 프로그램을 만드는에 투자를 하 여 나중에 응용 프로그램을 서비스 하는 경우 시간을 절약할 수 있습니다. 완전히 격리 된 응용 프로그램의 이점에 자세한 내용은 참조 [격리 된 응용 프로그램](/windows/desktop/SbsCs/isolated-applications)합니다.

네이티브 C 프로그램을 작성 하는 경우 /C++ Visual Studio 프로젝트 시스템 기본적으로 Visual Studio를 사용 하 여 응용 프로그램 Visual Studio 라이브러리에 대 한 응용 프로그램의 종속성을 설명 하는 매니페스트 파일을 생성 합니다. 경우에 종속성에 응용 프로그램을 Visual Studio를 사용 하 여 다시 빌드하는 즉시는 격리 된 응용 프로그램이 됩니다. 응용 프로그램은 런타임 시 다른 라이브러리를 사용 하는 경우에 설명 된 단계를 수행 하는 side-by-side-어셈블리와 해당 라이브러리를 다시 작성 해야 할 수 있습니다 [건물 C /C++ side-by-side-어셈블리](building-c-cpp-side-by-side-assemblies.md)합니다.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램 및 side-by-side 어셈블리 개념](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
