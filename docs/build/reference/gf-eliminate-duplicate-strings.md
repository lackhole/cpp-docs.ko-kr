---
title: /GF(중복 문자열 제거)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: 90d3fb5c601d9534215a46594884be5d168fe0aa
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449548"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF(중복 문자열 제거)

컴파일러가 실행 중에 프로그램 이미지와 메모리에 동일한 문자열의 단일 복사본을 만들 수 있도록 합니다. 이 최적화는 *문자열 풀링*이라고 불리며, 보다 작은 프로그램을 만들 수 있습니다.

## <a name="syntax"></a>구문

```
/GF
```

## <a name="remarks"></a>설명

**/GF**를 사용하면 운영 체제는 메모리의 문자열 부분을 바꾸지 않고 이미지 파일에서 해당 문자열을 다시 읽습니다.

**/GF**는 문자열을 읽기 전용으로 풀링합니다. **/GF**가 적용된 상황에서 문자열을 수정하려고 하면 응용 프로그램 오류가 발생합니다.

문자열 풀링은 다중 버퍼에 대한 다중 포인터를 단일 버퍼에 대해 다중 포인터로 간주합니다. 다음 코드에서 `s`와 `t`는 같은 문자열로 초기화됩니다. 문자열 풀링을 사용하면 동일한 메모리를 가리킬 수 있습니다.

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
>  편집 및 계속에 사용되는 [/ZI](z7-zi-zi-debug-information-format.md) 옵션은 **/GF** 옵션을 자동으로 설정합니다.

> [!NOTE]
>  **/GF** 컴파일러 옵션은 각 고유 문자열에 대하여 주소 지정이 가능한 섹션을 만듭니다. 기본적으로 개체 파일에는 최대 65,536개의 주소 지정 섹션을 포함할 수 있습니다. 65,536개 이상의 문자열을 포함하는 프로그램을 사용하는 경우 [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) 컴파일러 옵션을 사용하여 더 많은 섹션을 만듭니다.

**/GF**는 [/O1](o1-o2-minimize-size-maximize-speed.md) 또는 [/O2](o1-o2-minimize-size-maximize-speed.md)가 사용될 때 적용됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **코드 생성** 속성 페이지를 클릭합니다.

1. **문자열 풀링 사용** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
