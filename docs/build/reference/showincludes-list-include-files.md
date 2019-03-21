---
title: /showIncludes(포함 파일 나열)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
ms.openlocfilehash: d454054c132976a899fcc4a56a63be427e79beec
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819240"
---
# <a name="showincludes-list-include-files"></a>/showIncludes(포함 파일 나열)

컴파일러가 포함 파일의 목록을 출력 합니다. 중첩 된 포함 파일 표시 (포함 된 파일을 포함 하는 파일에서)도 있습니다.

## <a name="syntax"></a>구문

```
/showIncludes
```

## <a name="remarks"></a>설명

포함 파일을 컴파일하는 동안 발생 하는 경우는 메시지가 출력 됩니다. 예를 들어:

```
Note: including file: d:\MyDir\include\stdio.h
```

중첩 된 포함 파일을 들여써서 중첩의 각 수준에 대 한 예를 들어 표시 됩니다.

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

이 예에서 `2.h` 내에 포함 된 `1.h`, 따라서 들여쓰기입니다.

합니다 **/showIncludes** 옵션을 내보냅니다 `stderr`아니라 `stdout`합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **고급** 속성 페이지.

1. 수정 된 **포함 표시** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
