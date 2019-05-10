---
title: /DRIVER(Windows NT 커널 모드 드라이버)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: ab7253d7e386bf385bcb3a586c5e0e1c1e860694
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293110"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER(Windows NT 커널 모드 드라이버)

>/ 드라이버 [: UPONLY |: WDM]

## <a name="remarks"></a>설명

사용 된 **/DRIVER** Windows NT 커널 모드 드라이버를 작성 하는 링커 옵션입니다.

**/DRIVER:UPONLY** 링커가 추가 하는 **IMAGE_FILE_UP_SYSTEM_ONLY** 비트 프로세서 (위쪽) 드라이버를 지정 하려면 출력 헤더의 특징을를 합니다. 운영 체제는 다중 프로세서 (MP) 시스템 UP 드라이버를 로드 하지 않습니다.

**/Driver: wdm** 링커가 설정 하는 **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** 선택적인 헤더의 DllCharacteristics 필드에 비트입니다.

하는 경우 **/DRIVER** 지정 하지 않으면 링커는 이러한 비트가 설정 되지 않습니다.

하는 경우 **/DRIVER** 지정 됩니다.

- **/Fixed: no** 적용 됩니다. 자세한 내용은 [/FIXED(고정 기준 주소)](fixed-fixed-base-address.md)를 참조하세요.

- 출력 파일의 확장명.sys로 설정 됩니다. 사용 하 여 **/출력** 기본 파일 이름 및 확장명을 변경 합니다. 자세한 내용은 [/OUT(출력 파일 이름)](out-output-file-name.md)을 참조하세요.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **시스템** 속성 페이지.

1. 수정 된 **드라이버** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 참조 [VCLinkerTool.driver 속성](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver)합니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
