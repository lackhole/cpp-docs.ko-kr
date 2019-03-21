---
title: /H(외부 이름 길이 제한)
ms.date: 09/05/2018
f1_keywords:
- /h
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
ms.openlocfilehash: bdd3da8d3a5165262c00bc3475122e31f5770726
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811266"
---
# <a name="h-restrict-length-of-external-names"></a>/H(외부 이름 길이 제한)

더 이상 사용되지 않습니다. 외부 이름 길이 제한합니다.

## <a name="syntax"></a>구문

> **/H**<em>number</em>

## <a name="arguments"></a>인수

*number*<br/>
프로그램에서 허용 하는 외부 이름의 최대 길이 지정 합니다.

## <a name="remarks"></a>설명

기본적으로 외부 (공용) 이름의 길이 2,047 자입니다. 이 C 및 c + + 프로그램 마찬가지입니다. 사용 하 여 **/H** 줄어들를 식별자의 최대 허용 길이 줄어들 수 있습니다. 사이 공백을 **/H** 하 고 *번호* 선택 사항입니다.

프로그램 보다 긴 외부 이름이 있으면 *번호*, 나머지 문자는 무시 됩니다. 없이 프로그램을 컴파일하는 경우 **/H** 2,047 개 이상의 문자열을 포함 하는 식별자는 컴파일러에서 생성 하 고 [심각한 오류 C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)합니다.

길이 대 한 제한을 포함 모든 컴파일러 생성 선행 밑줄 (**\_**) 또는 at 기호 (**\@**). 이러한 문자는 식별자의 일부 이며 중요 한 의미를 수행 합니다.

- 컴파일러에 선행 밑줄이 추가 (**\_**)에 의해 수정 된 이름에는 `__cdecl` (기본값) 및 `__stdcall` 호출 규칙 및 최고의 at 기호 (**\@** )에 의해 수정 된 이름에는 `__fastcall` 호출 규칙입니다.

- 컴파일러에서 수정한 이름 인수 크기 정보를 추가 합니다 `__fastcall` 및 `__stdcall` 호출 규칙 및 c + + 이름에 유형 정보를 추가 합니다.

사용할 수 있습니다 **/H** 유용 합니다.

- 혼합 언어 또는 이식 가능한 프로그램을 만드는 경우.

- 사용 하는 경우 외부 식별자의 길이 제한 하는 도구입니다.

- 디버그 빌드에서 기호를 사용 하는 공간의 크기를 제한 하려는 경우.

다음 예제에서는 어떻게 사용 하 여 **/H** 식별자 길이 너무 많이 제한 하는 경우 오류가 실제로 발생할 수 있습니다.

```cpp
// compiler_option_H.cpp
// compile with: /H5
// processor: x86
// LNK2005 expected
void func1(void);
void func2(void);

int main() { func1(); }

void func1(void) {}
void func2(void) {}
```

또한 사용할 때는 주의 해야 합니다 **/H** 컴파일러 미리 정의 된 식별자가 있으므로 옵션입니다. 식별자의 최대 길이가 너무 작은 경우 특정 미리 정의 된 식별자는 확인 되지 않은 뿐만 아니라 특정 라이브러리 함수 호출 됩니다. 예를 들어 경우는 `printf` 함수는 옵션과 **/H5** 기호 컴파일 타임에 지정 된 **있으면** 참조 하기 위해 만들어집니다 `printf`,이 확인할 수는 라이브러리입니다.

이용 **/H** 와 호환 되지 않습니다 [/GL (전체 프로그램 최적화)](gl-whole-program-optimization.md)합니다.

합니다 **/H** 옵션은 Visual Studio 2005부터 사용 되지 않습니다; 최대 길이 한도 증가 되었습니다 및 **/H** 더 이상 필요 합니다. 사용 되지 않는 컴파일러 옵션의 목록을 참조 하세요 **컴파일러 옵션 및 사용 되지 않음** 에 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 컴파일러 옵션을 입력 합니다 **추가 옵션** 상자입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
