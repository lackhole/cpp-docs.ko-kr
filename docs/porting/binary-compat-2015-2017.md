---
title: C++Visual Studio 2015와 Visual Studio 2019 간의 이진 호환성
description: Visual Studio 2015, 2017 및 2019 C++ 의 컴파일된 파일 간에 이진 호환성이 작동 하는 방식에 대해 설명 합니다. Microsoft Visual C++ 재배포 가능 패키지 하나는 세 가지 버전 모두에 대해 작동 합니다.
ms.date: 11/07/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: e41c34abe25deefe100f525044faeac0b0c3054a
ms.sourcegitcommit: eb254b4462a58d219376ff501bf768bd1adc07ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2019
ms.locfileid: "73912884"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015와 Visual Studio 2019 간의 이진 호환성

Microsoft Visual Studio 2013 이전 버전에서는 서로 다른 버전의 컴파일러 도구 집합을 사용 하 여 빌드된 개체 파일 (Obj), 정적 라이브러리 (Dll), Dll (동적 연결 라이브러리) 및 실행 파일 (Exe) 간에 이진 호환성이 보장 되지 않습니다. 및 런타임 라이브러리.

Visual Studio 2015 이상에서 C++ 도구 집합 주 번호는 14입니다(Visual Studio 2015의 경우 v140, Visual Studio 2017의 경우 v141 및 Visual Studio 2019의 경우 v142). 이 번호 매기기는 이러한 버전의 컴파일러로 컴파일된 런타임 라이브러리와 응용 프로그램 모두 이진 호환성이 있음을 나타냅니다. 따라서 visual Studio 2015을 사용 하 여 빌드한 타사 라이브러리를 사용 하는 경우 Visual Studio 2017 또는 Visual Studio 2019를 사용 하 여 빌드한 응용 프로그램에서 사용 하기 위해 다시 컴파일할 필요가 없습니다.

이 규칙의 유일한 예외는 `/GL` 컴파일러 스위치를 사용 하 여 컴파일된 정적 라이브러리나 개체 파일이 이진 호환성이 *아닌* 것입니다.

지원 되는 다른 버전의 Microsoft C++ (MSVC) 도구 집합으로 빌드된 이진 파일을 혼합할 경우 C++ 응용 프로그램이 실행 되는 시각적 재배포 가능 패키지는 앱을 빌드하는 데 사용 되는 도구 집합 버전 또는 앱이 사용 하는 라이브러리 보다 이전 일 수 없습니다.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 또는 C++ 2017에서 visual studio 2019로 Microsoft visual 재배포 가능 패키지 업그레이드

이진 호환성을 유지 하 고 주 버전 (14)을 Visual Studio 2015, 2017 및 2019 용 C++ Microsoft visual Studio에서 동일 하 게 유지 했기 때문에 한 번에 하나의 시각적 C++ 재배포 가능 버전만 설치할 수 있습니다. 최신 버전은 이미 설치 된 이전 버전을 덮어씁니다. Visual Studio 2015 또는 2017 C++ 에서 visual studio를 재배포 가능 하 게 한 후 나중에 visual studio 2019를 설치 하면 2019 버전이 이전 버전을 덮어씁니다. 최신 버전에 최신 기능과 버그 수정 (보안 픽스 포함)이 모두 포함 되어 있는지 확인 하기 때문에 항상 사용 가능한 최신 버전으로 업그레이드 하는 것이 좋습니다.

마찬가지로 최신 버전이 이미 설치 되어 있는 컴퓨터에 이전 버전의 Visual C++ 재배포 가능 패키지를 설치할 수 없습니다. 이미 2019 버전이 C++ 있는 컴퓨터에서 visual Studio 2015 또는 2017의 시각적 재배포 가능 패키지를 설치 하면 설치 오류가 트리거됩니다. 오류는 다음과 유사 합니다.

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

이 오류는 의도적입니다. 최신 버전을 설치 된 상태로 유지 하는 것이 좋습니다.

## <a name="see-also"></a>참조

* [Visual C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)
* [지원 되는 최신 C++ 시각적 재배포 가능 다운로드](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
