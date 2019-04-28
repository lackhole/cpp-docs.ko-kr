---
title: /c(링크 없이 컴파일)
ms.date: 11/04/2016
f1_keywords:
- /c
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
ms.openlocfilehash: bfe351daf43b913f10df74b1059ba98f7d5d657b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294852"
---
# <a name="c-compile-without-linking"></a>/c(링크 없이 컴파일)

링크에 대 한 자동 호출을 방지합니다.

## <a name="syntax"></a>구문

```
/c
```

## <a name="remarks"></a>설명

사용 하 여 컴파일하면 **/c** 만.obj 파일을 만듭니다. 적절 한 파일 및 빌드 링크 단계를 수행 하는 옵션을 사용 하 여 연결을 명시적으로 호출 해야 합니다.

개발 환경에서 만든 내부 프로젝트를 사용 합니다 **/c** 옵션이 기본적으로 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

- 이 옵션은 개발 환경 내에서 사용할 수 없습니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>를 참조하세요.

## <a name="example"></a>예제

다음 명령줄 FIRST.obj 및 SECOND.obj 개체 파일을 만듭니다. THIRD.obj 무시 됩니다.

```
CL /c FIRST.C SECOND.C THIRD.OBJ
```

실행 파일을 만들려면 링크를 호출 해야 합니다.

```
LINK firsti.obj second.obj third.obj /OUT:filename.exe
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
