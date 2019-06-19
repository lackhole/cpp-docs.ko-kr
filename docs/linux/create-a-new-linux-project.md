---
title: Visual Studio에서 새로운 C++ Linux 프로젝트 만들기
ms.date: 06/07/2019
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: e39e60c906901420a4809c22b4f4e71d3b621da1
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821646"
---
# <a name="create-a-new-linux-project"></a>새 Linux 프로젝트 만들기

::: moniker range="vs-2015"

Linux 프로젝트는 Visual Studio 2017 이상에서 사용할 수 있습니다.

::: moniker-end

먼저 Visual Studio용 **Linux 개발 작업 워크로드**가 설치되어 있는지 확인합니다. 자세한 내용은 [Linux 워크로드 다운로드, 설치, 설정](download-install-and-setup-the-linux-development-workload.md)을 참조하세요.

Visual Studio에서 Linux에 대한 새로운 C++ 프로젝트를 만들 때 Visual Studio 프로젝트 또는 CMake 프로젝트를 만들도록 선택할 수 있습니다. 이 문서에서는 Visual Studio 프로젝트를 만드는 방법을 설명합니다. 기존 CMake 프로젝트로 만들고 작업하는 방법에 대한 자세한 내용은 [Linux CMake 프로젝트 구성](cmake-linux-project.md)을 참조하세요.

## <a name="to-create-a-new-linux-project"></a>새 Linux 프로젝트를 만들려면

Visual Studio에서 새 Linux 프로젝트를 만들려면 다음 단계를 따릅니다.

::: moniker range="vs-2019"

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택하거나 **Ctrl + Shift + N**을 누릅니다.
1. **언어**를 **C++** 로 설정하고 "Linux"를 검색합니다. 만들려는 프로젝트 형식을 선택한 다음, **다음**을 선택합니다. **이름** 및 **위치**를 입력하고, **만들기**를 선택합니다.

   ![새 Linux 프로젝트](media/newproject-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택하거나 **Ctrl + Shift + N**을 누릅니다.
1. **Visual C++ > 플랫폼 간 > Linux** 노드를 선택한 다음, 만들려는 프로젝트 형식을 선택합니다. **이름** 및 **위치**를 입력하고, **확인**을 선택합니다.

   ![새 Linux 프로젝트](media/newproject.png)

::: moniker-end

   | 프로젝트 형식 | 설명 |
   | ------------ | --- |
   | **깜박임(Raspberry)**           | Raspberry Pi 디바이스를 대상으로 하는 프로젝트로, LED가 깜박이는 샘플 코드가 포함되어 있습니다. |
   | **콘솔 애플리케이션(Linux)** | Linux 컴퓨터를 대상으로 하는 프로젝트로, 콘솔에 텍스트를 출력하는 샘플 코드가 포함되어 있습니다. |
   | **빈 프로젝트(Linux)**       | Linux 컴퓨터를 대상으로 하는 프로젝트로, 샘플 코드가 없습니다. |
   | **메이크파일 프로젝트(Linux)**    | Linux 컴퓨터를 대상으로 하는 프로젝트로, 표준 메이크파일 빌드 시스템을 사용하여 빌드됩니다. |

## <a name="next-steps"></a>다음 단계

[Linux 프로젝트 구성](configure-a-linux-project.md)
