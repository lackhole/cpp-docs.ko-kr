---
title: /ASSEMBLYRESOURCE(관리되는 리소스 포함)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: 1eac489ffd01f6bd79fc8c5bbda23adb751c9486
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822654"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE(관리되는 리소스 포함)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>매개 변수

*filename*<br/>
이 어셈블리에 포함할 관리 되는 리소스입니다.

*name*<br/>
선택 사항입니다. 리소스에 대 한 논리적 이름 리소스를 로드 하는 데 사용 하는 이름입니다. 기본값은 파일 이름입니다.

필요에 따라 파일은 어셈블리 매니페스트에 개인 이어야 하는 경우 지정할 수 있습니다. 기본적으로 *이름을* 어셈블리에 공개 합니다.

## <a name="remarks"></a>설명

어셈블리에 리소스를 포함 하려면 /ASSEMBLYRESOURCE 옵션을 사용 합니다.

리소스는 링커를 사용 하 여 만든 어셈블리에서 public입니다. 링커가는 어셈블리의 리소스 이름을 바꿀 수 없도록 합니다.

경우 *filename* 는, 예를 들어에서 만든.NET Framework 리소스 (.resources) 파일을 [리소스 파일 생성기 (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) 또는 개발 환경에서의 멤버를 사용 하 여 액세스할 수 있습니다는 **System.Resources** 네임 스페이스 (참조 [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager) 자세한). 다른 모든 리소스를 사용 합니다 **런타임에** \* 의 메서드 **System.Reflection.Assembly** 런타임에 리소스에 액세스 하는 클래스입니다.

어셈블리 생성에 영향을 주는 링커 옵션도 있습니다.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **입력** 속성 페이지.

1. 수정 된 **관리 되는 리소스 파일 포함** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
