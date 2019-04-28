---
title: /KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정)
ms.date: 11/04/2016
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
ms.openlocfilehash: d309390c1ac1a19d9d4a982908dbbbac0bd52714
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291563"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE(어셈블리에 서명할 키 또는 키 쌍 지정)

```
/KEYFILE:filename
```

## <a name="arguments"></a>인수

*filename*<br/>
키가 포함 된 파일입니다. 큰따옴표에서는 문자열을 배치 ("")에 공백이 있는 경우.

## <a name="remarks"></a>설명

링커는 공개 키를 어셈블리 매니페스트에 삽입 하 고 개인 키를 사용 하 여 최종 어셈블리에 서명 합니다. 키 파일을 생성 하려면 입력 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 명령줄에서. 서명된 된 어셈블리에 강력한 이름이 있어야 라고 합니다.

사용 하 여 컴파일하면 [/LN](ln-create-msil-module.md), 키 파일의 이름이 모듈에 저장 되 고 통해 모듈에 대 한 명시적 참조를 포함 하는 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [#using](../../preprocessor/hash-using-directive-cpp.md)를 사용 하 여 연결 하는 경우 또는 [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)합니다.

사용 하 여 링커에 암호화 정보를 전달할 수도 있습니다 [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)합니다. 사용 하 여 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) 부분적으로 서명된 된 어셈블리에 들어 있습니다. 참조 [강력한 이름 어셈블리 (어셈블리 서명) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.

둘 다를 경우 **/KEYFILE** 및 **/KEYCONTAINER** 지정 됩니다 (명령줄 옵션이 나 사용자 지정 특성), 링커는 먼저 키 컨테이너를 시도 합니다. 키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다. 링커 키 컨테이너를 찾을 수 없는 경우 /KEYFILE로 지정 된 파일을 찾으려고 합니다. 해당 파일을 찾으면 키 파일의 정보를 사용하여 어셈블리가 서명되고, 키 정보가 키 컨테이너에 설치되므로(sn -i와 유사) 다음에 컴파일할 때 키 컨테이너가 유효해집니다.

키 파일에는 공개 키만 포함될 수 있습니다.

참조 [강력한 어셈블리 만들기 및 사용](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) 어셈블리 서명에 대 한 자세한 내용은 합니다.

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
