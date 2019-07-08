---
title: /Qimprecise_fwaits(Try 블록 내의 fwait 제거)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 40683382686ea64a80563f3f29b7d3523f4144a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319592"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits(Try 블록 내의 fwait 제거)

[/fp:except](fp-specify-floating-point-behavior.md) 컴파일러 옵션을 사용할 때 `try` 블록 내의 `fwait` 명령을 제거합니다.

## <a name="syntax"></a>구문

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>설명

이 옵션은 **/fp:except**가 지정되지 않은 경우 아무런 효과가 없습니다. **/fp:except** 옵션을 지정하면 컴파일러는 `try` 블록의 코드 줄마다 `fwait` 명령을 삽입합니다. 컴파일러는 이러한 방식으로 예외를 발생시키는 코드의 특정 줄을 식별할 수 있습니다. **/Qimprecise_fwaits**는 내부 `fwait` 명령을 제거하여 `try` 블록 주위의 대기만을 남겨둡니다. 이렇게 되면 성능은 향상이 되지만 컴파일러는 몇 번째 라인에서가 아니라 어떤 `try` 블록이 예외를 발생시키는지에 대해서만 알 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
