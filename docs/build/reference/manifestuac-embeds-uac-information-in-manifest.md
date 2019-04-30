---
title: /MANIFESTUAC(매니페스트에 UAC 정보 포함)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
ms.openlocfilehash: ecc30baabdcb60a030418e9643e2fcffe5ba8281
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321373"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC(매니페스트에 UAC 정보 포함)

UAC(사용자 계정 컨트롤) 정보를 program 매니페스트에 포함할지 여부를 지정합니다.

## <a name="syntax"></a>구문

```
/MANIFESTUAC
/MANIFESTUAC:NO
/MANIFESTUAC:fragment
/MANIFESTUAC:level=_level
/MANIFESTUAC:uiAccess=_uiAccess
```

### <a name="parameters"></a>매개 변수

*fragment*<br/>
포함 된 문자열을 `level` 및 `uiAccess` 값입니다. 자세한 내용은이 항목의 뒷부분에 나오는 주의 섹션을 참조 하세요.

*_level*<br/>
중 하나 *asInvoker*하십시오 *highestAvailable*, 또는 *requireAdministrator*합니다. AsInvoker 기본값은입니다. 자세한 내용은이 항목의 뒷부분에 나오는 주의 섹션을 참조 하세요.

*_uiAccess*<br/>
**true 이면** 응용 프로그램 사용자 인터페이스 보호 수준을 무시 하 고, 그렇지 않으면 데스크톱에서 상위 권한 창에 대 한 입력을 원하면 **false**합니다. 기본값으로 **false**합니다. 로 **true** 사용자 인터페이스 접근성 응용 프로그램에 대해서만 합니다.

## <a name="remarks"></a>설명

명령줄에서 여러 /MANIFESTUAC 옵션을 지정 하는 경우 입력 한 개가 우선적으로 적용 합니다.

/MANIFESTUAC:level에 대 한 선택 항목은 다음과 같습니다.

- `asInvoker`: 응용 프로그램을 시작한 프로세스와 동일한 권한으로 실행 됩니다. 응용 프로그램을 선택 하 여 높은 권한 수준으로 승격할 수도 있습니다 **관리자 권한으로 실행**합니다.

- highestAvailable: 응용 프로그램은 가능한 가장 높은 권한 수준을 사용 하 여 실행 됩니다. 응용 프로그램을 시작한 사용자가 Administrators 그룹의 멤버인 경우이 옵션은 requireAdministrator 동일 합니다. 가장 높은 사용 가능한 사용 권한 수준이 열기 프로세스의 수준 보다 높은 경우 시스템 자격 증명을 묻는 됩니다.

- requireAdministrator: 응용 프로그램은 관리자 권한으로 실행 됩니다. 응용 프로그램을 시작 하는 사용자는 Administrators 그룹의 구성원 이어야 합니다. 열기 프로세스를 관리자 권한으로 실행 하지 않는 경우 시스템 자격 증명을 묻는 됩니다.

/MANIFESTUAC:fragment 옵션을 사용 하 여 한 번에 수준 및 uiAccess 값을 지정할 수 있습니다. 조각 다음 형식 이어야 합니다.

```
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** 노드를 확장합니다.

1. 확장 된 **링커** 노드.

1. 선택 된 **매니페스트 파일** 속성 페이지.

1. 수정 된 **사용 사용자 계정 컨트롤 (UAC)** 를 **UAC 실행 수준**, 및 **UAC UI 보호 건너뛰기** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. See <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>을 참조하십시오.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
