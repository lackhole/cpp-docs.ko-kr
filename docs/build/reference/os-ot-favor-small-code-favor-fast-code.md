---
title: /Os, /OT(크기 우선 코드, 속도 우선 코드)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
ms.openlocfilehash: 5bbdda07eacdb003515a40a93a232c0f8626ca89
ms.sourcegitcommit: aed09c9c05e6b031c8a9f87a8d6bbdaf253485e8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67412238"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /OT(크기 우선 코드, 속도 우선 코드)

EXE와 DLL의 크기를 최소화하거나 최대화합니다.

## <a name="syntax"></a>구문

```
/Os
/Ot
```

## <a name="remarks"></a>설명

**/Os**(크기 우선 코드)는 컴파일러에게 속도보다 크기를 우선으로 하여 EXE 및 DLL의 크기를 최소화합니다. 컴파일러는 많은 C 와 C++ 구문을 기능이 비슷한 기계어 코드 시퀀스로 줄일 수 있습니다. 경우에 따라 이러한 차이는 크기와 속도의 균형을 제공합니다. **/Os**와 **/Ot** 옵션을 사용하면 다른 옵션보다 우선 순위를 지정할 수 있습니다.

**/Ot**(속도 우선 코드)는 컴파일러가 크기보다 속도를 우선하도록 하여 EXE 및 DLL의 속도를 최대화합니다. (이것이 기본값입니다.) 컴파일러는 많은 C 와 C++ 구문을 기능이 비슷한 기계어 코드 시퀀스로 줄일 수 있습니다. 경우에 따라 이러한 차이는 크기와 속도의 균형을 제공합니다. **/Ot** 옵션은 속도 최대화([/O2](o1-o2-minimize-size-maximize-speed.md)) 옵션에 의해 설정됩니다. **/O2** 옵션은 매우 빠른 코드를 생성하기 위해 몇 가지 옵션을 결합합니다.

**/Os**나 **/Ot**를 사용하는 경우 [/Og](og-global-optimizations.md)도 함께 지정하여 코드를 최적화해야 합니다.

> [!NOTE]
>  프로파일링 테스트 실행에서 수집되는 정보는 **/Ob**, **/Os** 또는 **/Ot**를 지정하면 적용되는 최적화를 무시합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)를 참조합니다.

**x86 특정**

다음 예제 코드에서는 크기 우선 코드( **/Os**)와 속도 우선 코드( **/Ot**) 옵션의 차이점을 보여줍니다.

> [!NOTE]
>  다음은 **/Os**나 **/Ot**를 사용하는 경우 예상되는 동작을 설명합니다. 그러나 릴리스에 따라 컴파일러 동작이 다를 수 있어 아래 코드에 대해 다른 최적화가 초래될 수 있습니다.

```
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

아래 컴퓨터 코드의 조각에 표시된 것과 같이 DIFFER.c가 크기 우선 코드( **/Os**) 옵션으로 컴파일되면, 컴파일러는 return 문에서 multiply 표현식 곱하기를 명시적으로 구현하여 짧지만 느린 코드 시퀀스를 생성합니다.

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

반면, DIFFER.c가 속도 우선 코드( **/Ot**) 옵션으로 컴파일되면, 컴파일러는 return 문에서 곱하기를 시프트의 계열 및 `LEA` 명령어로 구현하여 빠르지만 긴 시퀀스를 생성합니다.

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END x86 특정**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **최적화** 속성 페이지를 클릭합니다.

1. **크기 또는 속도 우선** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
