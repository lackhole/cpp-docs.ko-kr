---
title: /DELAYSIGN(어셈블리에 부분적으로 서명)
ms.date: 11/04/2016
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
ms.openlocfilehash: 65585b856627ad9fda5a8f8bfad6ad81fef0f81c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293838"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN(어셈블리에 부분적으로 서명)

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>인수

**NO**<br/>
어셈블리가 부분적으로 서명 되지 해야 지정 합니다.

## <a name="remarks"></a>설명

사용 하 여 **/DELAYSIGN** 어셈블리의 공개 키를 저장 하려는 경우. 기본값은 **/delaysign: no**합니다.

합니다 **/DELAYSIGN** 옵션은 사용 하지 않는 한 효과가 없습니다 [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 하거나 [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)합니다.

완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 프라이빗 키로 해당 해시에 서명합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기 되 면 링커 계산 하거나 나중에 서명을 추가할 수 있도록 파일에 서명 하지만 공간을 예약을 저장 하지 않습니다.

예를 들어,를 사용 하 여 **/DELAYSIGN** 테스터가 어셈블리를 전역 캐시에 넣을 수 있습니다. 테스트를 마친 후에 어셈블리의 개인 키를 배치 하 여 어셈블리에 완전히 서명할 수 있습니다.

참조 [강력한 이름 어셈블리 (어셈블리 서명) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 하 고 [어셈블리 서명 연기](/dotnet/framework/app-domains/delay-sign-assembly) 어셈블리 서명에 대 한 자세한 내용은 합니다.

어셈블리 생성에 영향을 주는 링커 옵션도 있습니다.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. 에 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
