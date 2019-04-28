---
title: C/C++ 격리된 응용 프로그램 빌드
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: e02fec4115d328dd8230d68ddb65b380ec743dc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274709"
---
# <a name="building-cc-isolated-applications"></a>C/C++ 격리된 응용 프로그램 빌드

격리 된 응용 프로그램 side-by-side-어셈블리에만 의존 하 고 매니페스트를 사용 하 여 해당 종속성을 바인딩합니다. Windows;에서 제대로 실행 하기 위해 완전히 격리 된 응용 프로그램에 필요 하지 않습니다. 그러나 완전히 격리 된 응용 프로그램을 만드는에 투자를 하 여 나중에 응용 프로그램을 서비스 하는 경우 시간을 절약할 수 있습니다. 완전히 격리 된 응용 프로그램의 이점에 자세한 내용은 참조 [격리 된 응용 프로그램](/windows/desktop/SbsCs/isolated-applications)합니다.

네이티브 C 프로그램을 작성 하는 경우 /C++ 시각적 개체를 사용 하 여 응용 프로그램 C++를 기본적으로 Visual Studio 프로젝트 시스템 응용 프로그램의 종속성을 시각적 개체에서 설명 하는 매니페스트 파일을 생성 C++ 라이브러리입니다. 경우에 종속성에 응용 프로그램을 Visual Studio를 사용 하 여 다시 빌드하는 즉시는 격리 된 응용 프로그램이 됩니다. 응용 프로그램은 런타임 시 다른 라이브러리를 사용 하는 경우에 설명 된 단계를 수행 하는 side-by-side-어셈블리와 해당 라이브러리를 다시 작성 해야 할 수 있습니다 [건물 C /C++ side-by-side-어셈블리](building-c-cpp-side-by-side-assemblies.md)합니다.

## <a name="see-also"></a>참고자료

[격리된 응용 프로그램 및 side-by-side 어셈블리 개념](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
