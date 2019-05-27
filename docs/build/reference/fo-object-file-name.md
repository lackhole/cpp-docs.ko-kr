---
title: /Fo(개체 파일 이름)
ms.date: 11/04/2016
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: a8f2c1a196f18e6d310fd41d4dbed751440a4c20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293045"
---
# <a name="fo-object-file-name"></a>/Fo(개체 파일 이름)

기본값 대신 사용할 개체(.obj) 파일 이름이나 디렉터리를 지정합니다.

## <a name="syntax"></a>구문

```
/Fopathname
```

## <a name="remarks"></a>설명

이 옵션을 사용하지 않는 경우 개체 파일은 소스 파일의 기본 이름과 .obj 확장자를 사용합니다. 원하는 이름이나 확장자를 사용할 수 있지만 .obj를 사용하는 것이 좋습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **출력 파일** 속성 페이지를 클릭합니다.

1. **개체 파일 이름** 속성을 수정합니다.  개발 환경에서는 개체 파일 확장명이 .obj여야 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령줄은 B드라이브의 기존 \OBJECT 디렉터리에 THIS.obj라는 파일명으로 개체 파일을 만듭니다.

```
CL /FoB:\OBJECT\ THIS.C
```

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
