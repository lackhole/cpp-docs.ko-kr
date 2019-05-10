---
title: /Yu(미리 컴파일된 헤더 파일 사용)
ms.date: 11/04/2016
f1_keywords:
- /yu
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
ms.openlocfilehash: c0dcb045450d6e6eca31b8c76a92726e62400656
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316147"
---
# <a name="yu-use-precompiled-header-file"></a>/Yu(미리 컴파일된 헤더 파일 사용)

현재 컴파일에서 기존의 미리 컴파일된 헤더 (.pch) 파일을 사용 하도록 컴파일러에 지시 합니다.

## <a name="syntax"></a>구문

```
/Yu[filename]
```

## <a name="arguments"></a>인수

*filename*<br/>
이름을 사용 하 여 소스 파일에 포함 된 헤더 파일에 **#include** 전처리기 지시문입니다.

## <a name="remarks"></a>설명

포함 파일의 이름을 둘 다에 대해 동일 해야 합니다 **/Yc** 및 미리 컴파일된 헤더를 만드는 옵션 후속 **/Yu** 미리 컴파일된 헤더 사용을 지정 하는 옵션입니다.

에 대 한 **/Yc**를 `filename` 시점을 지정 중지 되는 미리 컴파일; 컴파일러 컴파일하며 모든 코드 `filename` include 파일 확장의 기본 이름을 사용 하 여 미리 컴파일된 헤더의 결과 .pch로 합니다.

.Pch 파일을 만들어야 합니다를 사용 하 여 **/Yc**합니다.

컴파일러는.h 파일로 미리 컴파일된 하기 전에 발생 하는 모든 코드를 처리 합니다. 뒤에 건너뜁니다 합니다 **#include** .h 파일과 연결 된 지시문.pch 파일에 포함 된 코드를 사용 하 고 다음 모든 코드를 컴파일합니다 `filename`합니다.

명령줄에서 없습니다 사이 공백을 **/Yu** 고 `filename`입니다.

지정 하는 경우는 **/Yu** 옵션 없이 소스 프로그램 파일 이름 포함 해야 합니다는 [#pragma hdrstop](../../preprocessor/hdrstop.md) 미리 컴파일된 헤더.pch 파일의 파일 이름을 지정 하는 pragma입니다. 이 경우 컴파일러에서 라는 미리 컴파일된 헤더 (.pch 파일)를 사용할지 [/Fp (이름입니다. Pch 파일)](fp-name-dot-pch-file.md)합니다. 컴파일러는 해당 pragma의 위치를 건너뛰고 pragma를 사용 하면 지정 된 미리 컴파일된 헤더 파일의 컴파일된 상태를 복원만 pragma 뒤에 오는 코드를 컴파일합니다. 하는 경우 **#pragma hdrstop** 확장명이.pch 인 소스 파일의 기본 이름에서 파생 된 이름으로 파일의 컴파일러는 파일 이름을 지정 하지 않습니다. 사용할 수도 있습니다는 **/Fp** 다른.pch 파일을 지정 하는 옵션입니다.

지정 하는 경우는 **/Yu** 파일 이름 없이 옵션을 지정 하지는 **hdrstop** pragma에 오류 메시지가 생성 되 고 컴파일이 성공 합니다.

경우는 **/Yc** `filename` 하 고 **/Yu** `filename` 옵션 같은 명령줄에서 발생 하 고 모두 동일한 파일 이름을 참조 **/Yc** `filename` 사용 우선 순위가 최대 모든 코드를 미리 컴파일 및 명명 된 파일을 포함 합니다. 이 기능은 메이크파일 작성을 단순화 합니다.

.Pch 파일에서 컴퓨터 환경에 대 한 정보 뿐만 아니라 프로그램의 메모리 주소 정보에 포함 하기 때문에 만들어진 컴퓨터의 pch 파일만 사용 해야 합니다.

미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.

- [/Y(미리 컴파일된 헤더)](y-precompiled-headers.md)

- [미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 지정할 [/Yc (미리 컴파일된 헤더 파일 만들기)](yc-create-precompiled-header-file.md) 프로젝트에서.cpp 파일입니다.

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **미리 컴파일된 헤더** 속성 페이지.

1. 수정 된 **파일에서 PCH 만들기/사용** 속성 또는 **미리 컴파일된 헤더 만들기/사용** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>을 참조하십시오.

## <a name="examples"></a>예제

하는 경우 다음 코드:

```
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
...
```

명령줄을 사용 하 여 컴파일된 `CL /YuMYAPP.H PROG.CPP`, 컴파일러는 세 가지를 처리 하지 않습니다 문은 하지만 MYAPP.pch 사용 하 여 미리 컴파일된 코드 파일 (및 모든 파일)의 세 가지를 모두 전처리에 포함 된 저장 함으로써 포함 합니다.

사용할 수는 [/Fp (이름입니다. Pch 파일)](fp-name-dot-pch-file.md) 옵션을 **/Yu** 이름 중 하나는 파일 이름 인수를 다른 경우.pch 파일의 이름을 지정 하는 옵션 **/Yc** 또는 같은 소스 파일의 기본 이름을 다음:

```
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP
```

이 명령은 MYPCH.pch 라는 미리 컴파일된 헤더 파일을 지정 합니다. 컴파일러 모든까지 헤더 파일을 포함 하 여 MYAPP.h 미리 컴파일된 상태를 복원 하려면 해당 콘텐츠를 사용 합니다. 컴파일러는 MYAPP.h 뒤에 오는 코드를 컴파일합니다 **포함** 문입니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
