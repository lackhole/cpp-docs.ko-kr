---
title: /ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: fb707a2721ed40ee3ec37d01b2bbcfcc51f05c38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295164"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE(.NET Framework 리소스에 대한 링크)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>인수

*filename*<br/>
어셈블리에서 연결할 .NET Framework 리소스 파일입니다.

## <a name="remarks"></a>설명

/ASSEMBLYLINKRESOURCE 옵션은 출력 파일에.NET Framework 리소스에 대 한 링크를 만듭니다. 리소스 파일을 출력 파일에 배치 되지 않습니다. [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) 출력 파일에 리소스 파일을 포함 합니다.

연결 된 리소스는 링커를 사용 하 여 만든 어셈블리에서는 public입니다.

/ASSEMBLYLINKRESOURCE 컴파일에 포함 해야 [/clr](clr-common-language-runtime-compilation.md); [/LN](ln-create-msil-module.md) 하거나 [/NOASSEMBLY](noassembly-create-a-msil-module.md) /ASSEMBLYLINKRESOURCE 허용 되지 않습니다.

경우 *filename* .NET Framework 리소스 파일인, 예를 들어에서 만든 [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) 개발 환경에서의 멤버를 사용 하 여 액세스할 수 있습니다 또는 **System.Resources** 네임 스페이스입니다. 자세한 내용은 [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager)합니다. 다른 모든 리소스를 사용 하 여 합니다 **런타임에** \* 의 메서드를 **System.Reflection.Assembly** 런타임에 리소스에 액세스 하는 클래스입니다.

*filename* 모든 파일 형식이 될 수 있습니다. 예를 들어, 다음 전역 어셈블리 캐시에 설치 및 어셈블리의 관리 되는 코드에서 액세스할 수 있도록 하는 어셈블리의 네이티브 DLL 부분을 확인 하는 것이 좋습니다.

어셈블리 생성에 영향을 주는 링커 옵션도 있습니다.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

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
