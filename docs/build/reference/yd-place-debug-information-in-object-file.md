---
title: /Yd(개체 파일에 디버그 정보 삽입)
ms.date: 11/04/2016
f1_keywords:
- /yd
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
ms.openlocfilehash: e6719226d28088d10da6c4f0e6caf3bdb78bea27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316173"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd(개체 파일에 디버그 정보 삽입)

함께 사용 하면 미리 컴파일된 헤더 (.pch) 파일에서 만든 모든 개체 파일에 대 한 정보를 디버깅 합니다. 전체 실행 합니다 [/Yc](yc-create-precompiled-header-file.md) 하 고 [/z7](z7-zi-zi-debug-information-format.md) 옵션입니다. 더 이상 사용되지 않습니다.

## <a name="syntax"></a>구문

```
/Yd
```

## <a name="remarks"></a>설명

**/Yd** 사용 되지 않습니다. Visual C++ 에서는 이제 여러 개체를 단일.pdb 파일에 쓸 사용 **/Zi** 대신 합니다. 사용 되지 않는 컴파일러 옵션의 목록을 참조 하세요 **컴파일러 옵션 및 사용 되지 않음** 에 [컴파일러 옵션 범주별 목록](compiler-options-listed-by-category.md)합니다.

디버깅 정보를 포함 하는 라이브러리 배포에 필요 하지 않은 경우 사용 합니다 [/Zi](z7-zi-zi-debug-information-format.md) 옵션 대신 **/z7** 하 고 **/Yd**합니다.

모든.obj 파일의 완전 한 디버깅 정보를 저장 하는 것은 디버깅 정보가 포함 된 라이브러리를 배포 하는 데에 필요 합니다. 컴파일 느려지고 상당한 디스크 공간이 필요 합니다. 때 **/Yc** 하 고 **/z7** 없이 사용 하는 **/Yd**, 컴파일러.pch 파일에서 만든 첫 번째.obj 파일의 일반적인 디버깅 정보를 저장 합니다. 컴파일러는.pch 파일에서 생성 하는.obj 파일에이 정보를 삽입 하지 않습니다. 정보에 대 한 상호 참조를 삽입합니다. .Pch 파일을 사용 하는.obj 파일의 수에 관계 없이 하나의.obj 파일 일반적인 디버깅 정보를 포함 합니다.

이 기본 동작으로 인해 더 빠르게 빌드 시간 및 디스크 공간 요구 사항 감소, 있지만 것이 바람직하지 않은 약간만 변경 하면 일반적인 디버깅 정보를 포함 하는.obj 파일을 빌드해야 하는 경우. 이 경우 컴파일러는 원래.obj 파일에 대 한 상호 참조를 포함 하는 모든.obj 파일을 다시 만들어야 합니다. 또한 일반적인.pch 파일을 다른 프로젝트에서 사용 하는 경우 단일.obj 파일에 대 한 상호 참조에 대 한 의존도 어렵습니다.

미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.

- [/Y(미리 컴파일된 헤더)](y-precompiled-headers.md)

- [미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="examples"></a>예제

두 개의 기본 파일 F.cpp와 이러한 각 포함 G.cpp이 있다고 가정해 봅시다 **#include** 문:

```
#include "windows.h"
#include "etc.h"
```

다음 명령은 미리 컴파일된 헤더를 만듭니다 ETC.pch 파일과 개체 F.obj 파일:

```
CL /YcETC.H /Z7 F.CPP
```

F.obj 개체 파일 형식 및 WINDOWS.h 및 ETC.h에 대 한 기호 정보 (및 다른 헤더 파일 포함)를 포함 합니다. 이제 소스 파일 G.cpp 컴파일하려면 ETC.pch 미리 컴파일된 헤더를 사용할 수 있습니다.

```
CL /YuETC.H /Z7 G.CPP
```

개체 파일 G.obj 미리 컴파일된 헤더에 대 한 디버깅 정보를 포함 하지 않습니다 하지만 F.obj 파일에서 해당 정보를 참조 합니다. F.obj 파일에 연결 해야 하는 참고 합니다.

미리 컴파일된 헤더가 사용 하 여 컴파일되지 않은 경우 **/z7**를 사용 하 여 나중에 사용할 수 있습니다 **/z7**합니다. 그러나 디버깅 정보를 현재 개체 파일에 배치 됩니다 및 함수와 미리 컴파일된 헤더에 정의 된 형식에 대 한 로컬 기호는 디버거에서 사용할 수 없는 합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
