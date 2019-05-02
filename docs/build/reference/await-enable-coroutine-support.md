---
title: /await (코루틴 지원 사용)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: c0c8c0183c356900ba8f95d39e427d56eb1ec96b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295008"
---
# <a name="await-enable-coroutine-support"></a>/await (코루틴 지원 사용)

**/await**은 코루틴에 대한 컴파일러 지원을 사용하도록 설정하는 컴파일러 옵션입니다.

## <a name="syntax"></a>구문

> /await

## <a name="remarks"></a>설명

합니다 **/await** 컴파일러 옵션을 사용 하면 C++ 코루틴 및 키워드에 대한 컴파일러 지원 **co_await**를 **co_yield**, 및 **co_return**. 이 옵션은 기본적으로 해제되어 있습니다. Visual Studio에서 코루틴에 대한 지원에 대한 자세한 내용은 참조는 [Visual Studio 팀 블로그](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)합니다. 코 루틴 표준 제안에 대 한 자세한 내용은 참조 하세요. [N4628 작업 초안, 코 루틴에 대한 C++ 확장에 대한 기술 사양](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf)합니다.

**/await** 옵션은 Visual Studio 2015부터 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트를 엽니다 **속성 페이지** 대화 상자.

1. **구성 속성**에서 **C/C++** 폴더를 확장하고 **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 **/await** 컴파일러 옵션을 입력합니다. **확인**이나 **적용**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
