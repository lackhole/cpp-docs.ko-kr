---
title: MFC ActiveX 컨트롤 마법사, 컨트롤 이름
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: 17c1b30811fa1d9c3f3bc04a46553c617eff966b
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708151"
---
# <a name="control-names-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사, 컨트롤 이름

컨트롤 클래스 및 속성 페이지 클래스를 형식 이름에 대 한 이름을 지정 하 고 컨트롤에 대 한 식별자를 입력 합니다. 경우는 예외 **약식 이름**, 다른 모든 필드 독립적으로 편집할 수 있습니다. 에 대 한 텍스트를 변경 하면 **약식 이름**,이 페이지의 다른 모든 필드의 이름에는 변경 내용이 반영 됩니다. 이 명명 문제는 모든 이름을 쉽게 식별할 수 있도록 하기 컨트롤을 개발할 때 설계 되었습니다.

- **짧은 이름**

   컨트롤에 대 한 약식된 이름을 제공 합니다. 기본적으로이 이름은에 제공 된 프로젝트 이름에 기반 합니다 **새 프로젝트** 대화 상자. 사용자가 제공한 이름을 해당 필드를 개별적으로 변경 하지 않는 한 클래스 이름, 형식 이름 및 형식 식별자를 결정 합니다.

- **컨트롤 클래스 이름**

   기본적으로 컨트롤 클래스의 이름을 기반 짧은 이름을 사용 하 여 `C` 접두사로 및 `Ctrl` 접미사로 합니다. 예를 들어, 컨트롤의 약식 이름 인지 `Price`에서 컨트롤 클래스 이름은 `CPriceCtrl`합니다.

- **컨트롤.h 파일**

   기본적으로 헤더 파일의 이름을 기반 짧은 이름을 사용 하 여 `Ctrl` 접미사로 및 `.h` 파일 확장명으로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 헤더 파일 이름은 `PriceCtrl.h`합니다. 이 필드의 이름은 컨트롤 클래스 이름과 일치 해야 합니다.

- **컨트롤.cpp 파일**

   기본적으로 헤더 파일의 이름을 기반 짧은 이름을 사용 하 여 `Ctrl` 접미사로 및 `.cpp` 파일 확장명으로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 헤더 파일 이름은 `PriceCtrl.cpp`합니다. 이 필드에 이름을 헤더 이름과 일치 해야 합니다.

- **컨트롤 형식 이름**

   기본적으로 컨트롤 형식의 이름은 짧은 이름 뒤에 기반 `Control`입니다. 예를 들어, 컨트롤의 약식 이름 인지 `Price`에서 컨트롤 클래스 유형 이름이 `Price Control`합니다. 이 필드의 값을 변경한 경우 이름을 상속 나타나는지 확인 합니다.

- **컨트롤 형식 ID**

   컨트롤 클래스의 컨트롤 형식 ID를 설정합니다. 컨트롤은 프로젝트에 추가 될 때 레지스트리에이 문자열을 씁니다. 컨테이너 응용 프로그램에서는이 문자열을 사용 하 여 컨트롤의 인스턴스를 만듭니다.

   기본적으로 컨트롤 형식 ID에서 지정한 프로젝트 이름에 기반 합니다 **새 프로젝트** 대화 상자 및 짧은 이름입니다. 이 이름은 형식 이름과 일치 해야 합니다.

   기본적으로 컨트롤 형식 ID는 다음과 같이 나타납니다.

   *ProjectName.ShortName*Ctrl.1

   이 대화 상자에서 짧은 이름을 변경 하면 컨트롤 형식 ID는 다음과 같이 나타납니다.

   *ProjectName.NewShortName*Ctrl.1

- **속성 페이지 클래스 이름**

   기본적으로 속성 페이지 클래스의 이름을 기반 짧은 이름을 사용 하 여 `C` 접두사로 및 `PropPage` 접미사로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 클래스 이름이 `CPricePropPage`합니다. 이 이름을 사용 하 여 추가 컨트롤 클래스 이름에 일치 해야 `PropPage`합니다.

- **속성 페이지.h 파일**

   기본적으로 페이지 헤더 속성 파일의 이름을에 따라 짧은 이름을 사용 하 여는 `PropPage` 접미사로 및 `.h` 파일 확장명으로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 헤더 파일 이름이 `PricePropPage.h`합니다. 이 이름은 클래스 이름과 일치 해야 합니다.

- **PropPage .cpp file**

   기본적으로 속성 페이지 구현 파일의 이름을에 따라 짧은 이름을 사용 하 여는 `PropPage` 접미사로 및 `.cpp` 파일 확장명으로 합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 헤더 파일 이름이 `PricePropPage.cpp`합니다. 이 이름에는 헤더 파일 이름을 일치 해야 합니다.

- **속성 페이지 형식 이름**

   기본적으로 속성 페이지 형식 이름은 짧은 이름 뒤에 더해서 `Property Page`합니다. 예를 들어, 컨트롤의 약식 이름인 `Price`, 속성 페이지 형식 이름이 `Price Property Page`합니다. 이 필드의 값을 변경한 경우 이름은 컨트롤 클래스를 나타냅니다. 있는지 확인 합니다.

- **속성 페이지 형식 ID**

   속성 페이지 클래스의 ID를 설정 합니다. 컨트롤은 프로젝트에 적용 되는 경우 레지스트리에서이 문자열을 씁니다. 컨테이너 응용 프로그램을이 문자열을 사용 하 여 컨트롤의 속성 페이지의 인스턴스를 만듭니다.

   기본적으로 속성 페이지 형식 ID에서 지정한 프로젝트 이름에 기반 합니다 **새 프로젝트** 대화 상자 및 짧은 이름입니다. 이 이름은 형식 이름과 일치 해야 합니다.

   기본적으로 속성 페이지 형식 ID는 다음과 같이 나타납니다.

   *ProjectName.ShortName*PropPage.1

   이 대화 상자에서 짧은 이름을 변경 하면 속성 페이지 형식 ID는 다음과 같이 나타납니다.

   *ProjectName.NewShortName*PropPage.1

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤 마법사](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[애플리케이션 설정, MFC ActiveX 컨트롤 마법사](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[MFC ActiveX 컨트롤 마법사, 컨트롤 설정](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Visual Studio 용으로 만들어지는 형식 파일 C++ 프로젝트](../../build/reference/file-types-created-for-visual-cpp-projects.md)

