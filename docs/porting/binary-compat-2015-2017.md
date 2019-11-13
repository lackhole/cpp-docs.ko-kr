---
title: C++Visual Studio 2015, 2017 및 2019 간의 이진 호환성
description: Visual Studio 2015, 2017 및 2019 C++ 의 컴파일된 파일 간에 이진 호환성이 작동 하는 방식에 대해 설명 합니다. Microsoft Visual C++ 재배포 가능 패키지 하나는 세 가지 버전 모두에 대해 작동 합니다.
ms.date: 11/11/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 118ad0a32d5dc8c344967f9a67f2d5b05aa806c0
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965559"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-2017-and-2019"></a>C++Visual Studio 2015, 2017 및 2019 간의 이진 호환성

Visual Studio 2013 및 C++ 이전 버전의 Microsoft (MSVC) 컴파일러 도구 집합은 버전 간의 이진 호환성을 보장 하지 않습니다. 서로 다른 버전으로 작성 된 개체 파일, 정적 라이브러리, 동적 라이브러리 및 실행 파일은 연결할 수 없습니다. ABIs, 개체 형식 및 런타임 라이브러리가 호환 되지 않습니다.

Visual Studio 2015, 2017 및 2019에서이 동작을 변경 했습니다. 이러한 버전의 컴파일러에서 컴파일된 런타임 라이브러리와 앱은 이진 호환성이 있습니다. 이는 세 버전 모두 C++ 에 대해 14 인 도구 집합 주 번호에 반영 됩니다. 도구 집합 버전은 Visual Studio 2015, v141 for 2017 및 v142 for 2019에 대 한 v140입니다. Visual Studio 2015에서 빌드된 타사 라이브러리를 포함 하 고 있다고 가정 합니다. Visual Studio 2017 또는 2019에서 빌드된 응용 프로그램에서 계속 사용할 수 있습니다. 일치 하는 도구 집합을 사용 하 여 다시 컴파일할 필요가 없습니다. 최신 버전의 Microsoft Visual C++ 재배포 가능 패키지 (재배포 가능 패키지)는 모든 작업에 대해 작동 합니다.

이 규칙에 대 한 예외는 예외입니다. 정적 라이브러리나 `/GL` 컴파일러 스위치를 사용 하 여 컴파일된 개체 파일은 버전 간에 이진 호환 *되지 않습니다* .

앱에서 사용 하는 재배포 가능 패키지에는 중요 한 이진 호환성 제한이 있습니다. 지원 되는 다른 버전의 도구 집합을 사용 하 여 빌드된 이진 파일을 혼합할 때 적용 됩니다. 재배포 가능 버전은 최소한 앱 구성 요소에서 사용 하는 최신 도구 집합과 동일 해야 합니다.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 또는 C++ 2017에서 visual studio 2019로 Microsoft visual 재배포 가능 패키지 업그레이드

Microsoft는 Visual Studio 2015, C++ 2017 및 2019에 대해 Microsoft visual 재배포 가능 주 버전 번호를 동일 하 게 유지 했습니다. 즉, 한 번에 재배포 가능의 인스턴스를 하나만 설치할 수 있습니다. 최신 버전은 이미 설치 된 이전 버전을 덮어씁니다. 예를 들어 하나의 앱이 Visual Studio 2015에서 재배포 가능 패키지를 설치할 수 있습니다. 그런 다음 다른 앱이 Visual Studio 2019에서 재배포 가능 패키지를 설치 합니다. 2019 버전은 이전 버전을 덮어쓰므로 이진 호환 되기 때문에 이전 앱은 여전히 제대로 작동 합니다. 최신 버전의 재배포 가능 패키지에 최신 기능, 보안 업데이트 및 버그 수정이 모두 포함 되어 있는지 확인 합니다. 따라서 항상 사용 가능한 최신 버전으로 업그레이드 하는 것이 좋습니다.

마찬가지로 최신 버전이 이미 설치 되어 있는 경우에는 이전 재배포 가능 패키지를 설치할 수 없습니다. 시도 하는 경우 설치 관리자에서 오류를 보고 합니다. 2019 버전이 이미 설치 된 컴퓨터에 2015 또는 2017 재배포 가능 패키지를 설치 하는 경우 다음과 같은 오류가 표시 됩니다.

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

이 오류는 의도적입니다. 최신 버전을 설치 하는 것이 좋습니다. 설치 관리자가이 오류를 자동으로 복구할 수 있는지 확인 합니다.

## <a name="see-also"></a>참조

[시각적 C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)\
[지원 되는 최신 C++ 시각적 재배포 가능 다운로드](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
