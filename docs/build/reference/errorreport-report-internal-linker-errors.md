---
title: /ERRORREPORT(내부 링커 오류 보고)
ms.date: 12/28/2017
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 26cc157cb7247a3a2ea7c10b415df1160540c9ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818026"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT(내부 링커 오류 보고)

> **/errorreport:**[ **none** | **prompt** | **queue** | **send** ]

## <a name="arguments"></a>인수

**none**<br/>
내부 컴파일러 오류에 대한 보고서를 수집하거나 Microsoft로 보내지 않습니다.

**prompt**<br/>
내부 컴파일러 오류가 발생하면 보고서를 보낼지 묻는 메시지를 표시합니다. **프롬프트** 는 개발 환경에서 응용 프로그램을 컴파일할 때 기본값입니다.

**queue**<br/>
오류 보고서를 큐에 넣습니다. 관리자 권한으로 로그인 하면 기록 된 마지막 시간 이후 발생 한 모든 오류를 보고할 수 있도록 창이 표시 됩니다 (하지 묻는 3 일 마다 한 번에 오류에 대 한 보고서를 보내도록). **큐** 는 명령 프롬프트에서 응용 프로그램을 컴파일할 때 기본값입니다.

**send**<br/>
Windows 오류 보고 서비스 설정에 따라 보고를 사용 하는 경우 Microsoft에 내부 컴파일러 오류 보고서를 자동으로 보냅니다.

## <a name="remarks"></a>설명

합니다 **/ERRORREPORT** 옵션을 사용 하면 Microsoft에 내부 컴파일러 오류 (ICE) 정보를 제공 합니다.

옵션 **/errorreport: send** Windows 오류 보고 서비스 설정으로 사용 하도록 설정 하는 경우 오류 정보를 Microsoft에 자동으로 보냅니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 엽니다는 **구성 속성** > **링커** > **고급** 속성 페이지.

1. 수정 된 **오류 보고** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/errorReport(내부 컴파일러 오류 보고)](errorreport-report-internal-compiler-errors.md)<br/>
[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
