---
title: /INCLUDE(강제 기호 참조)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 1f7a443e32ed20550e3017c7e6ce70f4adf5137d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269872"
---
# <a name="include-force-symbol-references"></a>/INCLUDE(강제 기호 참조)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>매개 변수

*symbol*<br/>
기호를 기호 테이블을 추가할 수를 지정 합니다.

## <a name="remarks"></a>설명

/INCLUDE 옵션을 사용 하면 링커에서 기호 테이블에 지정된 된 기호를 추가 하려면.

여러 기호를 지정 하려면 쉼표 (,), 세미콜론 (;) 또는 기호 이름 사이 공백을 입력 합니다. 명령줄에서 지정 /INCLUDE:`symbol` 각 기호에 대 한 한 번입니다.

링커 확인 `symbol` 프로그램 기호 정의 포함 하는 개체를 추가 하 여 합니다. 이 기능은 그렇지 않은 경우 링크 되지 프로그램에는 라이브러리 개체를 포함 하는 데 유용 합니다.

이 옵션을 사용 하 여 기호를 지정 하면으로 해당 기호는 제거를 재정의 [/opt: ref](opt-optimizations.md)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **입력** 속성 페이지.

1. 수정 된 **강제 기호 참조** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
