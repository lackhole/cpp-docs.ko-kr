---
title: /J(부호 없는 기본 문자 형식)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: ed296d339949814dbd796bb5d8e23a406be71c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269403"
---
# <a name="j-default-char-type-is-unsigned"></a>/J(부호 없는 기본 문자 형식)

기본 `char` 형식을 `signed char`에서 `unsigned char`로 변경하고, `char` 형식은 `int` 형식으로 형변환시 확장되는 부분을 0으로 채웁니다.

## <a name="syntax"></a>구문

```
/J
```

## <a name="remarks"></a>설명

`char` 값이 명시적으로 `signed`라고 선언된 경우 **/J** 옵션은 영향을 주지 않으며 `int` 형식으로 확장되면 부호확장 됩니다.

**/J** 옵션은 `_CHAR_UNSIGNED`를 정의하며 LIMITS.h 파일의 `#ifndef`과 함께 사용되어 `char` 형식의 범위를 정의합니다.

ANSI C 및 C++에서는 `char` 형식의 특정된 구현이 필요하지 않습니다. 이 옵션은 결국 영어 이외의 언어로 변환될 문자 데이터로 작업할 때 유용 합니다.

> [!NOTE]
>  ATL/MFC에서 이 컴파일러 옵션을 사용하면 오류가 생성될 수 있습니다. `_ATL_ALLOW_CHAR_UNSIGNED`를 정의해서 이 오류를 비활성화할 수도 있지만 이 해결 방법은 지원되지 않으며, 항상 작동하지 않을 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.

1. 프로젝트에서 **속성 페이지** 대화 상자에서 왼쪽 창의 **구성 속성**를 확장하고 **C/C++**  선택한 후 **명령줄**을 선택합니다.

1. **추가 옵션** 창에서 **/J** 컴파일러 옵션을 지정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)

