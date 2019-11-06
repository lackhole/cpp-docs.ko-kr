---
title: C++Visual Studio 2015와 Visual Studio 2019 간의 이진 호환성
ms.date: 10/17/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 761f6187a8b30ecb4214821c7f91d1b26e9c647c
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627016"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015와 Visual Studio 2019 간의 이진 호환성

Visual Studio 2013 및 이전 버전에서는 여러 버전의 컴파일러 도구 집합 및 런타임 라이브러리를 사용하여 빌드된 개체 파일(OBJ), 정적 라이브러리(LIB), 동적 라이브러리(DLL) 및 실행 파일(EXE) 간의 이진 호환성이 보장되지 않았습니다. 

Visual Studio 2015 이상에서 C++ 도구 집합 주 번호는 14입니다(Visual Studio 2015의 경우 v140, Visual Studio 2017의 경우 v141 및 Visual Studio 2019의 경우 v142). 이는 이러한 버전의 컴파일러를 사용 하 여 컴파일된 런타임 라이브러리와 응용 프로그램 모두 이진 호환성이 있음을 나타냅니다. 즉, Visual Studio 2015로 빌드된 타사 라이브러리가 있는 경우 Visual Studio 2017 또는 Visual Studio 2019로 빌드된 애플리케이션에서 사용하기 위해 다시 컴파일하지 않아도 됩니다.

이 규칙의 유일한 예외는 정적 라이브러리 또는 `/GL` 컴파일러 스위치로 컴파일된 개체 파일이 이진 호환되지 않는다는 것입니다.

지원 되는 다른 버전의 MSVC 도구 집합으로 빌드된 이진 파일을 혼합할 경우 C++ 응용 프로그램이 실행 되는 시각적 개체는 앱을 빌드하는 데 사용 되는 도구 집합 버전 또는 응용 프로그램이 사용 하는 라이브러리 보다 이전 일 수 없습니다.

## <a name="upgrade-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 C++ 또는 2017에서 visual studio 2019로 Microsoft visual 재배포 가능 패키지 업그레이드

이진 호환성이 유지 되 고 visual Studio 2015, 2017 및 2019에 대 한 Visual C++ Studio 재배포 가능 패키지에 대 한 주 버전 (14)이 동일 하 게 유지 되므로 언제 든 C++ 지 해당 버전의 비주얼 재배포 가능 패키지를 설치할 수 있습니다. 최신 버전은 설치 된 이전 버전을 덮어씁니다. Visual Studio 2015 또는 2017 C++ 에서 visual Studio를 다시 설치 하 고 나중에 2019를 설치 하면 2019 버전이 이전 버전을 덮어씁니다. 최신 버전에 보안 픽스를 비롯 하 여 최신 기능과 버그 수정 사항이 모두 포함 되어 있으므로 항상 사용 가능한 최신 버전으로 업그레이드 하는 것이 좋습니다.

마찬가지로, 이전 버전의 Visual C++ 재배포 가능 버전이 이미 있는 컴퓨터에 설치 하는 것을 허용 하지 않습니다. 이미 2019가 C++ 있는 컴퓨터에서 visual Studio 2015 또는 2017의 시각적 재배포 가능 패키지를 설치 하면 설치 오류가 발생 합니다. 오류는 다음과 유사 하 게 표시 됩니다.

```
*0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.*.
```

이 오류는 의도적입니다. 최신 항목을 설치 하는 것이 좋습니다.

## <a name="see-also"></a>참조

* [Visual C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)
* [지원 되는 최신 C++ 시각적 재배포 가능 다운로드](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
