---
title: /Oi(내장 함수 만들기)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
ms.openlocfilehash: f3afedade6f99129c21069e5117daa4ceb616cc2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811890"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi(내장 함수 만들기)

일부 함수 호출을 내장 함수나 특정 형태의 함수 응용 프로그램 수 있도록 대체 더 빠르게 실행 합니다.

## <a name="syntax"></a>구문

```
/Oi[-]
```

## <a name="remarks"></a>설명

내장 함수를 사용 하는 프로그램 되므로 빠르게 함수 호출의 오버 헤드가 없는 있지만 추가 코드를 만들기 때문에 클 수 있습니다.

참조 [내장](../../preprocessor/intrinsic.md) 자세한 함수는 내장 형식이 있습니다.

**/Oi** 요청 컴파일러 내장 함수;를 사용 하 여 일부 함수 호출을 바꾸려면 컴파일러 수 함수를 호출 합니다 (및 내장 함수를 사용 하 여 함수 호출을 대체 하지) 성능이 향상 되는 결과입니다.

**x86 특정**

내장 부동 소수점 함수에 입력된 값에 특수 한 검사를 수행 하 고 따라서 제한 된 범위의 입력에서 작동를 마십시오 다른 예외 처리와 같은 이름 가진 라이브러리 루틴과 경계 조건. IEEE 예외 처리의 손실과 손실 의미 실제 내장 형식을 사용 하 여 `_matherr` 고 `errno` 기능 후자 ANSI 규칙의 손실을 의미 합니다. 그러나, 내장 형식은 수 상당히 프로그램의 속도를 부동 소수점를 많이 사용 되며 대부분의 프로그램에 대 한 규칙과 관련 된 문제를 작은 실제 값의 합니다.

사용할 수는 [Za](za-ze-disable-language-extensions.md) 컴파일러 옵션을 실제 내장 부동 소수점 옵션 생성을 재정의 합니다. 이 경우에는 함수가 인수를 프로그램 스택으로 푸시하는 대신 부동 소수점 칩으로 직접 전달하는 라이브러리 루틴으로 생성됩니다.

**END x86 특정**

또한 사용 하 여 [내장](../../preprocessor/intrinsic.md) 내장 함수 또는 [함수 (C/c + +)](../../preprocessor/function-c-cpp.md) 함수 호출을 명시적으로 적용할 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **최적화** 속성 페이지.

1. 수정 된 **내장 함수를 사용 하도록 설정** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md)
