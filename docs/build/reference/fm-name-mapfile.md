---
title: /Fm(맵 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: eebb1bc0c553dba1934aea75e2e63edc0f222fff
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815408"
---
# <a name="fm-name-mapfile"></a>/Fm(맵 파일 이름 지정)

해당.exe 파일이 나 DLL에 나타나는 순서로 세그먼트의 목록을 포함 하는 맵 파일을 만들도록 링커에 지시 합니다.

## <a name="syntax"></a>구문

```
/Fmpathname
```

## <a name="remarks"></a>설명

기본적으로 맵 파일에는 해당 C 또는 C++ 소스 파일의 기본 이름이 지정 됩니다을 합니다. 맵 확장 합니다.

지정 **/Fm** 지정 않았던 것 처럼 동일한 효과가 합니다 [/MAP (맵 파일 생성)](map-generate-mapfile.md) 링커 옵션입니다.

지정 하는 경우 [(컴파일 없이 링크 사용)는 /c](c-compile-without-linking.md) 에 연결 하지 않으려면 **/Fm** 영향을 주지 않습니다.

컴파일러는 변수 이름에 선행 밑줄이 추가 하기 때문에 일반적으로 맵 파일의 전역 기호는 하나 이상의 선행 밑줄이 있습니다. 맵 파일에 표시 되는 많은 전역 기호는 컴파일러 및 표준 라이브러리에서 내부적으로 사용 됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
