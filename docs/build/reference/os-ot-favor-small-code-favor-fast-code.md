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
ms.openlocfilehash: d4e8d062685a543c428f0c86a22c17c8faf017ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814254"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /OT(크기 우선 코드, 속도 우선 코드)

최소화 또는 Exe 및 Dll의 크기를 최대화 합니다.

## <a name="syntax"></a>구문

```
/Os
/Ot
```

## <a name="remarks"></a>설명

**/Os** (크기 우선 코드) 속도 보다 크기 우선. 컴파일러에 지시 하 여 Exe 및 Dll의 크기를 최소화 합니다. 컴파일러는 기계어 코드로의 기능적으로 비슷하지만 순서에 여러 C 및 c + + 구문의 줄일 수 있습니다. 경우에 따라 이러한 차이 크기와 속도의 균형을 제공합니다. 합니다 **/Os** 하 고 **/Ot** 옵션 둘 중 하나에 대 한 기본 설정을 지정할 수 있습니다.

**/Ot** (크기 우선 코드) 크기 보다 속도 우선. 컴파일러에 지시 하 여 Exe 및 Dll의 속도 최대화 합니다. (이것이 기본값입니다.) 컴파일러는 기계어 코드로의 기능적으로 비슷하지만 순서에 여러 C 및 c + + 구문의 줄일 수 있습니다. 경우에 따라 이러한 차이 크기와 속도의 균형을 제공합니다. 속도 최대화 /Ot 옵션이 포함 됩니다 ([/o2](o1-o2-minimize-size-maximize-speed.md)) 옵션입니다. 합니다 **/o2** 옵션 매우 빠르게 코드를 생성 하기 위해 몇 가지 옵션을 결합 합니다.

사용 하는 경우 **/Os** 하거나 **/Ot**에 지정 해야 합니다 [/Og](og-global-optimizations.md) 코드를 최적화 하려면.

> [!NOTE]
>  프로 파일링 테스트 실행에서 수집 되는 정보를 지정 하는 경우 적용에서 되는 최적화 덮어씁니다 **/Ob**를 **/Os**, 또는 **/Ot**합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다.

**x86 특정**

다음 예제 코드에서는 코드 크기 우선 간의 차이 보여 줍니다 (**/Os**) 옵션 및 코드 속도 우선 (**/Ot**) 옵션:

> [!NOTE]
>  다음 사용 하는 경우 예상 되는 동작에 설명 합니다 **/Os** 하거나 **/Ot**합니다. 그러나 컴파일러 동작 릴리스 간에 아래 코드에 대 한 다른 최적화 될 수 있습니다.

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

아래 컴퓨터 코드의 조각에 표시 된 것과 같이 DIFFER.c를 컴파일할 때 크기에 대 한 (**/Os**), 컴파일러 구현은 곱하기 식 return 문에서 명시적으로 코드 짧지만 느린 시퀀스:

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

DIFFER.c를 속도 대해 컴파일할 때에 또는 (**/Ot**), 컴파일러 구현은 곱하기 시프트의 계열로 return 문에서 식 및 `LEA` 코드 빠르지만 긴 시퀀스를 생성 하는 지침:

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END x86 특정**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **최적화** 속성 페이지.

1. 수정 된 **크기 또는 속도** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
