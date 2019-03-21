---
title: /Zo(최적화된 디버깅 향상)
ms.date: 11/04/2016
f1_keywords:
- -Zo
- /Zo
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
ms.openlocfilehash: 2fb64b0cc39d5b7ff0c96d3eae47197c455526f5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809940"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo(최적화된 디버깅 향상)

디버그되지 않은 빌드에서 최적화된 코드에 대해 향상된 디버깅 정보를 생성합니다.

## <a name="syntax"></a>구문

```cpp
/Zo[-]
```

## <a name="remarks"></a>설명

합니다 **/Zo** 컴파일러 스위치는 최적화 된 코드에 대 한 향상 된 디버깅 정보를 생성 합니다. 최적화는 지역 변수에 레지스터를 사용하고 코드를 다시 정렬하며 루프를 벡터화하고 인라인 함수 호출을 수행할 수 있습니다. 이와 같이 최적화를 수행하면 소스 코드와 컴파일된 개체 코드 간 관계가 명확하지 않을 수 있습니다. 합니다 **/Zo** 스위치는 지역 변수 및 인라인 된 함수에 대 한 추가 디버깅 정보를 생성 하도록 컴파일러에 지시 합니다. 변수를 사용 합니다 **자동**, **지역**, 및 **조사식** 최적화 된 Visual Studio 디버거에서 코드를 단계별로 실행할 때 windows. 또한 스택 추적을 설정하여 WinDBG 디버거에 인라인된 함수를 표시할 수도 있습니다. 디버그 빌드 최적화를 사용 하지 않도록 설정한 ([/Od](od-disable-debug.md)) 경우에 생성 된 추가 디버깅 정보를 사용할 필요가 없습니다 **/Zo** 지정 됩니다. 사용 된 **/Zo** 최적화가 설정 된 릴리스 구성을 디버그로 전환 합니다. 최적화 스위치에 대 한 자세한 내용은 참조 하세요. [/O 옵션 (코드 최적화)](o-options-optimize-code.md)합니다. 합니다 **/Zo** 옵션은 Visual Studio에서 기본적으로 사용 하 여 디버깅 정보를 지정 하는 경우 **/Zi** 하거나 **/z7**합니다. 지정할 **/Zo-** 명시적으로이 컴파일러 옵션을 사용 하지 않도록 설정 합니다.

합니다 **/Zo** 스위치는 Visual Studio 2013 업데이트 3부터 사용할 수 있으며 이전에 문서화 되지 않은 대체 **/d2Zi+** 전환 합니다.

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio에서 /Zo 컴파일러 옵션을 설정하려면

1. 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성**를 **C/c + +** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 `/Zo` 를 선택한 후 **확인**합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[/Z7, /Zi, /ZI(디버깅 정보 형식)](z7-zi-zi-debug-information-format.md)<br/>
[편집하며 계속하기](/visualstudio/debugger/edit-and-continue)
