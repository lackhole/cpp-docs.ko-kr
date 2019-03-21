---
title: /homeparams(스택에 레지스터 매개 변수 복사)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: a1f9269c7deae6c9ae2e4f198006ad09dd37abc3
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820665"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams(스택에 레지스터 매개 변수 복사)

또한 해당 위치에 작성 함수 시작 시 스택의 레지스터에 전달 된 매개 변수입니다.

## <a name="syntax"></a>구문

> **/homeparams**

## <a name="remarks"></a>설명

이 컴파일러 옵션은만 네이티브 및 x64를 대상으로 하는 크로스 컴파일러를 사용할 수 있습니다.

X64 호출 규칙에는 레지스터에 전달 된 매개 변수에 대해서도 모든 매개 변수에 할당할 스택 공간이 필요 합니다. 자세한 내용은 [매개 변수 전달](../../build/x64-calling-convention.md#parameter-passing)합니다. 기본적으로 레지스터 매개 변수는 릴리스 빌드에서 할당 된 스택 공간에 복사 되지 않습니다. 따라서 프로그램의 최적화 된 릴리스 빌드를 디버그 하기 어렵게 합니다.

릴리스 빌드에 사용할 수 있습니다 합니다 **/homeparams** 복사할 컴파일러가 옵션 응용 프로그램을 디버깅할 수 있도록 스택에 매개 변수를 등록 합니다. **/homeparams** 스택에 레지스터 매개 변수를 로드 하는 추가 주기가 필요 하기 때문에 성능 단점이 의미지 않습니다.

디버그 빌드에서 스택의 항상 채워집니다 레지스터에 전달 된 매개 변수입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 엽니다는 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 컴파일러 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
