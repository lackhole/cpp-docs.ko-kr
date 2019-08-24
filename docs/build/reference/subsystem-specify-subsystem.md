---
title: /SUBSYSTEM(하위 시스템 지정)
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: ecda3443d0422af4d5ceec9282d86590c53af2f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318247"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM(하위 시스템 지정)

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>인수

**BOOT_APPLICATION**<br/>
Windows 부팅 환경에서 실행되는 애플리케이션입니다. 부팅 응용 프로그램에 대 한 자세한 내용은 참조 하세요. [에 대 한 BCD](/previous-versions/windows/desktop/bcd/about-bcd)합니다.

**CONSOLE**<br/>
Win32 문자 모드 응용 프로그램입니다. 운영 체제는 콘솔 애플리케이션에 콘솔을 제공합니다. 하는 경우 `main` 또는 `wmain` 네이티브 코드에 대해 정의 된 `int main(array<String ^> ^)` 관리 코드에 대해 정의 된 사용 하 여 완전히 응용 프로그램을 빌드 또는 `/clr:safe`, CONSOLE이 기본값입니다.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Extensible Firmware Interface 하위 시스템입니다. 자세한 내용은 EFI 사양을 참조 하십시오. 예를 들어 Intel 웹 사이트를 참조 하세요. 최소 버전 및 기본 버전은 1.0입니다.

**네이티브**<br/>
Windows nt 커널 모드 드라이버입니다. 이 옵션은 일반적으로 Windows 시스템 구성 요소에 대해 예약 됩니다. 하는 경우 [/driver: wdm](driver-windows-nt-kernel-mode-driver.md) 가 지정 된 네이티브 기본값입니다.

**POSIX**<br/>
Windows NT의 POSIX 하위 시스템으로 실행 되는 응용 프로그램입니다.

**WINDOWS**<br/>
사용자와 상호 작용을 위해 고유한 창을 만들기 때문에 응용 프로그램 콘솔 아마도 필요 하지 않습니다. 경우 `WinMain` 나 `wWinMain` 네이티브 코드에 대해 정의 된 또는 `WinMain(HISTANCE *, HINSTANCE *, char *, int)` 또는 `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` 정의 된 관리 코드에 대해 WINDOWS가 기본값입니다.

*주요* 고 *부*<br/>
(선택 사항) 하위 시스템의 최소 필수 버전을 지정 합니다. 인수는 0과 65535 사이의 범위 내에 10 진수 숫자입니다. 자세한 내용은 설명을 참조 하세요. 버전 번호의 상한 없음 있습니다.

## <a name="remarks"></a>설명

합니다 **/SUBSYSTEM** 옵션에는 실행 파일에 대 한 환경을 지정 합니다.

선택한 하위 시스템 진입점 기호 (또는 진입점 함수)에 영향을 줍니다 링커를 선택 하는 합니다.

(옵션) 최소값 및 기본값 *주요* 하 고 *부* 하위 시스템에 대 한 버전 번호는 다음과 같습니다.

|하위 시스템|최소|기본|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|CONSOLE|(x86) 5.01 (x64) 5.02 6.02 (ARM)|(x86, x64) 6.00 6.02 (ARM)|
|WINDOWS|(x86) 5.01 (x64) 5.02 6.02 (ARM)|(x86, x64) 6.00 6.02 (ARM)|
|(드라이버: WDM) 포함 된 네이티브 코드|(x86) 1.00 1.10 (x64, ARM)|(x86) 1.00 1.10 (x64, ARM)|
|네이티브 (/driver: wdm) 없음|(x86) 4.00 (x64) 5.02 6.02 (ARM)|(x86) 4.00 (x64) 5.02 6.02 (ARM)|
|POSIX|1.0|19.90|
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 링커 폴더를 선택 합니다.

1. 선택 된 **시스템** 속성 페이지.

1. 수정 된 `SubSystem` 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
