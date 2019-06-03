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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270915"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH(_pexit 후크 함수 사용)

모든 메서드와 함수의 끝에 `_pexit` 함수를 호출합니다.

## <a name="syntax"></a>구문

```
/GH
```

## <a name="remarks"></a>설명

`_pexit` 함수는 라이브러리의 일부가 아니며, `_pexit`에 대한 정의는 개발자의 제공에 따라 달라집니다.

명시적으로 `_pexit`를 호출하지 않는다면 프로토타입을 제공하지 않아도 됩니다. 마치 함수에 이어 프로토타입이 있는 것처럼 실행되며 레지스터에 있는 모든 내용을 푸시하고 종료 시 변경되지 않은 내용을 팝해야 합니다.

```
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit`는 `_penter`와 비슷합니다. `_pexit` 함수의 작성 방법은 [/Gh(_penter 후크 함수 사용)](gh-enable-penter-hook-function.md)을 참조합니다.

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
