---
title: /Ge(스택 조사 사용)
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: a785ec041370e0bcbb2ce8b698bfba89235a0a0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292187"
---
# <a name="ge-enable-stack-probes"></a>/Ge(스택 조사 사용)

지역 변수에 대 한 저장소를 필요로 하는 모든 함수 호출에 대 한 스택 프로브를 활성화 합니다.

## <a name="syntax"></a>구문

```
/Ge
```

## <a name="remarks"></a>설명

이 메커니즘은 스택 프로브 기능을 다시 작성할 때 유용 합니다. 사용 하는 것이 좋습니다 [/Gh (_penter 후크 함수 사용)](gh-enable-penter-hook-function.md) 스택 프로브를 다시 작성 하는 대신 합니다.

[/Gs (컨트롤 스택 검사 호출)](gs-control-stack-checking-calls.md) 동일한 효과가 있습니다.

**/Ge** 는 사용 되지 않습니다; Visual Studio 2005부터 컴파일러가 자동으로 스택 검사를 수행 합니다. 사용 되지 않는 컴파일러 옵션의 목록을 참조 하세요 **컴파일러 옵션 및 사용 되지 않음** 에 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
