---
title: '방법: 64비트, x64 플랫폼을 대상으로 하는 Viausl Studio C++ 프로젝트 구성'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: a063c2f333a755ab86a4f91c9d14d0c65a6d1414
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446399"
---
# <a name="how-to-configure-visual-studio-c-projects-to-target-64-bit-x64-platforms"></a>방법: 64비트, x64 플랫폼을 대상으로 하는 Viausl Studio C++ 프로젝트 구성

설정 하기 위해 Visual Studio IDE에서 프로젝트 구성을 사용할 수 있습니다 C++ 대상 응용 프로그램을 64 비트, x64 플랫폼입니다. 또한 Win32 프로젝트 설정을 64비트 프로젝트 구성에 마이그레이션할 수 있습니다.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>64비트 플랫폼을 대상으로 하도록 C++ 애플리케이션을 설정하려면

1. 구성하려는 C++ 프로젝트를 엽니다.

1. 해당 프로젝트의 속성 페이지를 엽니다. 자세한 내용은 [Visual Studio에서 컴파일러 및 빌드 속성 설정](working-with-project-properties.md)을 참조합니다.

   > [!NOTE]
   > .NET 프로젝트에 대 한 확인 합니다 **구성 속성** 에서 노드 또는 해당 자식 노드 중 하나를 선택 합니다  **\<Projectname > 속성 페이지** 대화 상자 고, 그렇지 않으면 합니다  **Configuration Manager** 단추를 사용할 수 있습니다.

1. **구성 관리자** 단추를 선택하여 **구성 관리자** 대화 상자를 엽니다.

1. 에 **활성 솔루션 플랫폼** 드롭 다운 목록에서를  **\<새로 만들기... >** 옵션을 합니다 **새 솔루션 플랫폼** 대화 상자.

1. 에 **새 플랫폼 입력 또는 선택** 드롭 다운 목록에서 대상 플랫폼 선택 64 비트입니다.

   > [!NOTE]
   > **새 솔루션 플랫폼** 대화 상자에서 **다음에서 설정 복사** 옵션을 사용하여 기존 프로젝트 설정을 새 64비트 프로젝트 구성에 복사할 수 있습니다.

1. **확인** 단추를 선택합니다. 이전 단계에서 선택한 플랫폼이 **구성 관리자** 대화 상자의 **활성 솔루션 플랫폼** 아래에 표시됩니다.

1. 선택 합니다 **닫기** 단추를 **Configuration Manager** 대화 상자를 선택한 후는 **확인** 단추를  **\<Projectname > 속성 페이지** 대화 상자.

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Win32 프로젝트 설정을 64비트 프로젝트 구성에 복사하려면

- 64비트 플랫폼을 대상으로 하도록 프로젝트를 설정하는 동안 **새 솔루션 플랫폼** 대화 상자가 열리는 경우 **다음에서 설정 복사** 드롭다운 목록에서 **Win32**를 선택합니다. 다음 프로젝트 설정이 프로젝트 수준에서 자동으로 업데이트됩니다.

  - [/MACHINE](reference/machine-specify-target-platform.md) 링커 옵션이 **/MACHINE:X64**로 설정됩니다.

  - **출력 등록** 이 꺼집니다. 자세한 내용은 [Linker Property Pages](reference/linker-property-pages.md)을 참조하세요.

  - **대상 환경** 이 **/env x64**로 설정됩니다. 자세한 내용은 참조 하세요. [MIDL Property Pages: 일반](reference/midl-property-pages-general.md)합니다.

  - **매개 변수 유효성 검사** 가 초기화되어 기본값으로 다시 설정됩니다. 자세한 내용은 참조 하세요. [MIDL Property Pages: 고급](reference/midl-property-pages-advanced.md)합니다.

  - **디버그 정보 형식** 이 Win32 프로젝트 구성에서 **/ZI** 로 설정되면 64비트 프로젝트 구성에서는 **/Zi** 로 설정됩니다. 자세한 내용은 [/Z7, /Zi, /ZI(디버그 정보 형식)](reference/z7-zi-zi-debug-information-format.md)를 참조하세요.

  > [!NOTE]
  > 이러한 프로젝트 속성이 파일 수준에서 재정의된 경우에는 어떠한 속성도 변경되지 않습니다.

## <a name="see-also"></a>참고자료

[64비트, x64를 대상으로 하는 C++ 프로젝트 구성](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[64비트 응용 프로그램 디버그](/visualstudio/debugger/debug-64-bit-applications)
