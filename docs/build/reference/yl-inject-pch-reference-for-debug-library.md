---
title: /Yl(디버그 라이브러리에 PCH 참조 넣기)
ms.date: 01/29/2018
f1_keywords:
- /yl
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
ms.openlocfilehash: 92e47836e0fdae077defa0fe35b515ab4ca20a66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316251"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl(디버그 라이브러리에 PCH 참조 넣기)

합니다 **/Yl** 옵션이 미리 컴파일된 헤더 파일에서 고유한 기호를 생성 하 고이 기호의 참조를 미리 컴파일된 헤더를 사용 하는 모든 개체 파일에 삽입 됩니다.

## <a name="syntax"></a>구문

>**/Yl**
> **/Yl**_name_
> **/Yl-**

### <a name="arguments"></a>인수

*name*<br/>
고유한 기호의 일부로 사용 하는 선택적 이름입니다.

*\-*<br/>
대시 (-)을 명시적으로 비활성화 합니다 **/Yl** 컴파일러 옵션입니다.

## <a name="remarks"></a>설명

**/Yl** 컴파일러 옵션 사용 하 여 만든 미리 컴파일된 헤더 파일에 고유한 기호 정의 생성 합니다 [/Yc](yc-create-precompiled-header-file.md) 옵션입니다. 이 기호에 대 한 참조를 사용 하 여 미리 컴파일된 헤더를 포함 하는 모든 파일에서 자동으로 주입 되어는 [/Yu](yu-use-precompiled-header-file.md) 컴파일러 옵션입니다. 합니다 **/Yl** 옵션은 기본적으로 때 **/Yc** 미리 컴파일된 헤더 파일을 만드는 데 사용 됩니다.

합니다 **/Yl**_이름_ 옵션이 미리 컴파일된 헤더 파일에 식별할 수 있는 기호를 만드는 데 사용 됩니다. 컴파일러를 사용 합니다 *이름* 만듭니다, 비슷합니다 데코레이팅된 기호 이름의 일부로 인수 `__@@_PchSym_@00@...@name`고유한 컴파일러에서 생성 된 줄임표 (...) 나타내는 문자열을 합니다. 경우는 *이름을* 인수를 생략 하면, 컴파일러에서 자동으로 기호 이름을 생성 합니다. 일반적으로 기호의 이름을 알 필요가 없습니다. 그러나 프로젝트가 미리 컴파일된 헤더 파일이 여러 개 사용 합니다 **/Yl**_이름_ 옵션 개체에는 미리 컴파일된 헤더를 사용 하 여 파일을 확인 하는 데 유용할 수 있습니다. 사용할 수 있습니다 *이름을* 덤프 파일에 기호 참조를 찾으려면 검색 문자열로 합니다.

**/Yl-** 기본 동작을 사용 하지 않도록 설정 하 고 미리 컴파일된 헤더 파일에 식별 기호를 넣지 않습니다. 이 미리 컴파일된 헤더를 포함 하는 컴파일된 파일에서 공통 기호 참조를 가져오지 못합니다.

때 **/Yc** 지정 하지 않으면 모든 **/Yl** 옵션에 지정 된 경우 모든 일치 해야 하지만 효과가 **/Yl** 옵션을 전달 하는 경우 **/Yc** 는 지정 합니다.

사용 하는 경우 **/Yl-** 를 **/Yc** 하 고 [/z7](z7-zi-zi-debug-information-format.md) 디버깅 정보를 미리 컴파일된 헤더 파일을 작성 하는 옵션은 소스 파일을 만드는 데 사용에 대 한 개체 파일에 저장 합니다 미리 컴파일된 헤더를 별도.pdb 파일 보다는 합니다. 경우이 개체 파일은 다음 라이브러리의 일부 [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) 오류 또는 [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) 경고 소스 파일을 만드는 데이 라이브러리 및 미리 컴파일된 헤더 파일을 사용 하는 빌드에 발생할 수 있습니다는 미리 컴파일된 헤더 파일 정의 하지 않습니다 모든 기호 자체. 개체 파일의 경우 nothing 라이브러리 클라이언트에서 참조 될 때 링커 디버깅 관련된 정보와 함께 링크에서 개체 파일을 제외 될 수 있습니다. 이 문제를 해결 하려면 지정 **/Yl** (또는 제거를 **/Yl-** 옵션) 사용 하는 경우 **/Yc** 미리 컴파일된 헤더 파일을 만들 수 있습니다. 이렇게 하면 디버깅 정보가 포함 된 라이브러리에서 개체 파일을 가져옵니다 빌드에 연결 되어 있음을 합니다.

미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.

- [/Y(미리 컴파일된 헤더)](y-precompiled-headers.md)

- [미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 추가 된 **/Yl**_이름_ 컴파일러 옵션을 **추가 옵션** 상자. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
