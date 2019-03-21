---
title: /TSAWARE(터미널 서버 인식 응용 프로그램 만들기)
ms.date: 11/04/2016
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
ms.openlocfilehash: f6ed6184f8ae4b3a0f9db3c1f962a2918a185138
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816947"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE(터미널 서버 인식 응용 프로그램 만들기)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>설명

/TSAWARE 옵션은 프로그램 이미지 선택적 헤더의 IMAGE_OPTIONAL_HEADER DllCharacteristics 필드에서 플래그를 설정합니다. 이 플래그를 설정하면 터미널 서버가 애플리케이션에서 특정 변경 작업을 수행할 수 없습니다.

터미널 서버 인식 (레거시 응용 프로그램이 라고도 함) 응용 프로그램이 없는 경우 터미널 서버에서는 레거시 응용 프로그램이 다중 사용자 환경에서 제대로 작동 하도록 특정 사항을 수정 합니다. 예를 들어 터미널 서버는 각 사용자가 시스템의 Windows 디렉터리를 가져오는 대신 Windows 폴더에는 가상 Windows 폴더에 만들어집니다. 그러면 사용자가 액세스할 자신의 INI 파일에 있습니다. 또한 터미널 서버에는 레거시 응용 프로그램에 대 한 레지스트리를 일부 조정을 합니다. 이러한 수정 사항을 느린 터미널 서버에서 레거시 응용 프로그램을 로드 합니다.

터미널 서버 인식 응용 프로그램을 사용 하는 경우이 해야 INI 파일 의존 아니고 쓸 합니다 **HKEY_CURRENT_USER** 설치 하는 동안 레지스트리입니다.

/TSAWARE 사용 응용 프로그램은 여전히 INI 파일을 사용 하는 경우 파일 시스템의 모든 사용자가 공유할 수 됩니다. 허용 되는 경우 /TSAWARE;를 사용 하 여 응용 프로그램 계속 연결할 수 있습니다. 그렇지 않으면 /tsaware: no를 사용 해야 합니다.

/TSAWARE 옵션은 Windows 및 콘솔 응용 프로그램에 대 한 기본적으로 활성화 됩니다. 참조 [/SUBSYSTEM](subsystem-specify-subsystem.md) 하 고 [/VERSION](version-version-information.md) 정보에 대 한 합니다.

/TSAWARE는 드라이버, Vxd, 또는 Dll에 대해 올바르지 않습니다.

/TSAWARE, DUMPBIN 사용 하 여 응용 프로그램 연결 된 경우 [/HEADERS](headers.md) 그 결과 정보가 표시 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **시스템** 속성 페이지.

1. 수정 된 **터미널 서버** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[사용자 관련 정보를 저장합니다.](/windows/desktop/TermServ/storing-user-specific-information)<br/>
[터미널 서비스 환경에서 레거시 응용 프로그램](https://msdn.microsoft.com/library/aa382957.aspx)
