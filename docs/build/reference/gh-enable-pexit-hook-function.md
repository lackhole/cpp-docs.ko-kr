---
title: /GH(_pexit 후크 함수 사용)
ms.date: 11/04/2016
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: 077096cc296f2aa2128127493a84a91da9a067c5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822173"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH(_pexit 후크 함수 사용)

호출 된 `_pexit` 함수의 모든 메서드 또는 함수의 끝입니다.

## <a name="syntax"></a>구문

```
/GH
```

## <a name="remarks"></a>설명

합니다 `_pexit` 함수 라이브러리의 일부가 아니며에 대 한 정의 제공 하는 것 `_pexit`입니다.

명시적으로 호출 하려는 경우가 아니면 `_pexit`, 프로토타입을 제공 해야 합니다. 함수 처럼 다음과 같은 프로토타입의 되었 및 항목에 대해 모든 레지스터의 콘텐츠를 푸시 하며 종료 시 변경 되지 않은 콘텐츠를 pop에 나타나야 합니다.

```
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit` 비슷합니다 `_penter`; 참조 [/Gh (_penter 후크 함수 사용)](gh-enable-penter-hook-function.md) 작성 하는 방법의 예는 `_pexit` 함수입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
