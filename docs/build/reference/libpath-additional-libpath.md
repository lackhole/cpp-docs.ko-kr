---
title: /LIBPATH(추가 Libpath)
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: ab586c788825a854e7d3cb3760da6e4e5558de3a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819885"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH(추가 Libpath)

```
/LIBPATH:dir
```

## <a name="parameters"></a>매개 변수

*dir*<br/>
경로 지정 링커는 LIB 환경 옵션에서 지정 된 경로 검색 하기 전에 검색 합니다.

## <a name="remarks"></a>설명

환경 라이브러리 경로 재정의할 /LIBPATH 옵션을 사용 합니다. 링커는 먼저이 옵션으로 지정 된 경로에서 검색를 누른 다음 LIB 환경 변수에 지정 된 경로에서 검색 합니다. 입력 하면 각 /LIBPATH 옵션에 대 한 디렉터리를 하나만 지정할 수 있습니다. 둘 이상의 디렉터리를 지정 하려는 경우 여러 /LIBPATH 옵션을 지정 해야 합니다. 링커는 다음 순서로 지정 된 디렉터리를 검색 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **일반** 속성 페이지.

1. 수정 된 **추가 라이브러리 디렉터리** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
