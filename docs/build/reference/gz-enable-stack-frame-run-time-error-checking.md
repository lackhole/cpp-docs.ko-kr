---
title: /GZ(스택 프레임 런타임 오류 검사 사용)
ms.date: 11/04/2016
f1_keywords:
- /gz
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
ms.openlocfilehash: 3e6ffce487cc8183e45f3a911e7060ea22b28216
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292059"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ(스택 프레임 런타임 오류 검사 사용)

[/RTC (런타임 오류 검사)](rtc-run-time-error-checks.md) 옵션과 동일한 작업을 수행 합니다. 더 이상 사용되지 않습니다.

## <a name="syntax"></a>구문

```
/GZ
```

## <a name="remarks"></a>설명

**/GZ**는 최적화 되지 않은 빌드에 사용하기 위한 ([/Od (비활성화 (디버그))](od-disable-debug.md))에서만 사용됩니다.

**/GZ**는 Visual Studio 2005부터 사용되지 않습니다. 대신 [/RTC (런타임 오류 검사)](rtc-run-time-error-checks.md)를 사용합니다. 사용 되지 않는 컴파일러 옵션은 **컴파일러 옵션 및 사용 되지 않음**의 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)을 참조합니다.

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
