---
title: /NOENTRY(진입점 없음)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
ms.openlocfilehash: c750fd94e21eec39a25acf216a452faaa277bf7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320411"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY(진입점 없음)

```
/NOENTRY
```

## <a name="remarks"></a>설명

실행 코드가 없는 리소스 전용 DLL을 만들려면 /NOENTRY 옵션을 지정해야 합니다. 자세한 내용은 [Resource-Only DLL 만들기](../creating-a-resource-only-dll.md)합니다.

이 옵션을 사용하면 LINK가 `_main`에 대한 참조를 DLL로 링크하는 것을 방지할 수 있습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **링커** 폴더입니다.

1. 선택 된 **고급** 속성 페이지.

1. 수정 된 **진입점 없음** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[리소스 전용 DLL 만들기](../creating-a-resource-only-dll.md)<br/>
[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
