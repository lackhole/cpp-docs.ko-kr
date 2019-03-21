---
title: Visual Studio에서 새로운 C++ Linux 프로젝트 만들기
ms.date: 09/12/2018
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: bd5ab1d2bc1077f366082bf8767f8f690173ac8b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745166"
---
# <a name="create-a-new-linux-project"></a>새 Linux 프로젝트 만들기

먼저 Visual Studio용 **Linux 개발 작업 워크로드**가 설치되어 있는지 확인합니다. 자세한 내용은 [Linux 워크로드 다운로드, 설치, 설정](download-install-and-setup-the-linux-development-workload.md)을 참조하세요.

Linux용 Visual Studio에서 새 C++ 프로젝트를 만들 때 Visual Studio 프로젝트 또는 CMake 프로젝트를 만들도록 선택할 수 있습니다. 이 항목에서는 Visual Studio 프로젝트를 만드는 방법을 설명합니다. 기존 CMake 프로젝트로 만들어 작업하는 것에 대한 자세한 내용은 [Linux CMake 프로젝트 구성](cmake-linux-project.md)을 참조하세요.

Visual Studio에서 새 Linux 프로젝트를 만들려면 다음을 수행합니다.

1. Visual Studio에서 **파일 > 새 프로젝트**를 선택하거나 **Ctrl + Shift + N**을 누릅니다.
1. **[Visual C++] > [플랫폼 간] > [Linux]** 노드를 선택한 후 만들려는 프로젝트 형식을 선택하고, 이름/위치를 입력하고, [확인]을 클릭합니다.

   ![새 Linux 프로젝트](media/newproject.png)

   | 프로젝트 형식 | 설명
   | ------------ | ---
   | **깜박임(Raspberry)**           | Raspberry Pi 디바이스를 대상으로 하는 프로젝트로, LED가 깜박이도록 작성한 샘플 코드가 포함되어 있습니다.
   | **콘솔 애플리케이션(Linux)** | Linux 컴퓨터를 대상으로 하는 프로젝트로, 콘솔에 텍스트를 출력하도록 작성한 샘플 코드가 포함되어 있습니다.
   | **빈 프로젝트(Linux)**       | Linux 컴퓨터를 대상으로 하는 프로젝트로, 작성한 샘플 코드가 없습니다.
   | **메이크파일 프로젝트(Linux)**    | Linux 컴퓨터를 대상으로 하는 프로젝트로, 표준 메이크파일 빌드 시스템을 사용하여 빌드됩니다.
