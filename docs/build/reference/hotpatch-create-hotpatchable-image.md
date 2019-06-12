---
title: /hotpatch(핫 패치 가능 이미지 만들기)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 8830b26b8fdfc3db2aa5fe31a52e6226fd554946
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291654"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch(핫 패치 가능 이미지 만들기)

핫 패치가 가능한 이미지를 준비합니다.

## <a name="syntax"></a>구문

```
/hotpatch
```

## <a name="remarks"></a>설명

컴파일 시 **/hotpatch**를 사용하면 컴파일러는 각 함수의 첫 번째 명령이 핫 패치가 요구하는 최소 2바이트인지 확인합니다.

이미지를 핫 패칭 가능하게 만들기 위한 준비를 위해서는, **/hotpatch**를 사용하여 컴파일한 후 [/FUNCTIONPADMIN(핫 패치 가능 이미지 만들기)](functionpadmin-create-hotpatchable-image.md)를 사용하여 링크해야 합니다. cl.exe를 한번 호출하여 이미지를 컴파일하고 연결할 때 **/hotpatch**는 **/functionpadmin**을 의미합니다.

ARM 아키텍처 지침에는 명령어가 항상 2바이트 이상이므로 x64 컴파일은 항상 **/hotpatch**가 지정된 것처럼 처리되므로 이러한 대상에 대해 컴파일할 때 **/hotpatch**를 지정하지 않아도 됩니다. 하지만 **/functionpadmin**를 사용하여 링크하여 핫 패치 가능 이미지를 만들어야 합니다. **/hotpatch** 컴파일러 옵션은 x86 컴파일에만 영향을 줍니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 선택합니다

1. **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 추가합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
