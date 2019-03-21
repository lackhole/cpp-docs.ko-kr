---
title: /OPT(최적화)
ms.date: 05/18/2018
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
ms.openlocfilehash: fb59b861bc46c93a3f5fa1b6c6b8d1b73ddefc66
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818299"
---
# <a name="opt-optimizations"></a>/OPT(최적화)

LINK가 빌드하는 동안 수행할 최적화를 제어합니다.

## <a name="syntax"></a>구문

> **/OPT:**{**REF** | **NOREF**}<br/>
> **/OPT:**{**ICF**[**=**_iterations_] | **NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>인수

**REF** &AMP;#124; **NOREF**

**/Opt: ref** 함수와; 참조 되지 않는 데이터를 제거 합니다. **/Opt: noref** 함수 및 참조 되지 않는 데이터를 유지 합니다.

링크 /opt: ref를 사용 하는 경우 참조 되지 않은 패키지에 포함 된 함수 및 데이터와 제거 *Comdat*합니다. 이러한 최적화를 전이적 COMDAT 제거라고 합니다. 합니다 **/opt: ref** 옵션 또한 증분 링크를 해제 합니다.

인라인된 함수 및 클래스 선언 안에 정의 된 멤버 함수는 항상 Comdat입니다. 모든 개체 파일의 함수에 대 한 Comdat를 사용 하 여 컴파일된 경우 합니다 [/Gy](gy-enable-function-level-linking.md) 옵션입니다. 배치할 **상수** Comdat에 데이터를 선언 해야 합니다를 사용 하 여 `__declspec(selectany)`입니다. 제거 또는 정리에 대 한 데이터를 지정 하는 방법에 대 한 정보를 참조 하세요 [selectany](../../cpp/selectany.md)합니다.

기본적으로 **/opt: ref** 아니면 링커에서 사용 됩니다 **/opt: noref** 하거나 [디버그](debug-generate-debug-info.md) 지정 됩니다. 이 기본값을 재정의 하 고 프로그램에서 참조 되지 않는 Comdat를 유지 하려면 지정 **/opt: noref**합니다. 사용할 수는 [/include](include-force-symbol-references.md) 특정 기호는 제거 되지 않도록 하는 옵션입니다.

경우 [디버그](debug-generate-debug-info.md) 지정 된 경우에 대 한 기본값 **/opt** 됩니다 **NOREF**, 되어 모든 함수가 이미지에 보존 됩니다. 이 기본값을 재정의 하 고 디버그 빌드를 최적화 하려면 지정 **/opt: ref**합니다. 이 프로그램 실행 파일의 크기를 줄일 수 및 디버그에도 유용한 최적화 작성 될 수 있습니다. 지정 하는 것이 좋습니다 **/opt: noicf** 동일한 유지 하기 위해 디버그에서 함수 작성. 이렇게 하면 스택 추적을 읽고 다른 방식으로는 함께 정리될 함수에서 중단점을 쉽게 설정할 수 있습니다.

**ICF**\[**=**_반복_] &#124; **NOICF**

사용 하 여 **ICF**\[**=**_반복_] 동일한 COMDAT 정리를 수행 하 합니다. 중복 COMDAT는 링커 출력에서 제거될 수 있습니다. 선택적 *반복* 매개 변수는 중복 항목에 대 한 기호를 트래버스하는 횟수를 지정 합니다. 기본 반복 횟수는 1입니다. 추가 반복에서 이전 반복의 정리를 통해 발견되지 않은 중복 항목을 더 많이 찾을 수도 있습니다.

기본적으로 **/opt: icf** 아니면 링커에서 사용 됩니다 **/opt: noicf** 하거나 [디버그](debug-generate-debug-info.md) 지정 됩니다. 이 기본값을 재정의 하 고 프로그램에서 접히는에서 Comdat를 방지 하려면 지정 **/opt: noicf**합니다.

디버그 빌드를 명시적으로 지정 해야 **/opt: icf** COMDAT 정리 사용 하도록 설정 합니다. 그러나 때문 **/opt: icf** 동일한 데이터 또는 함수를 병합할 수 있습니다, 스택 추적에 표시 되는 함수 이름을 변경할 수 있습니다. 못할 수 있습니다도 특정 함수에 중단점을 설정 하거나 디버거에서 일부 데이터를 조사 하 고 예기치 않은 함수로 이동할 수 있습니다 때 코드를 단계별로 실행 하는 단일 있습니다. 코드의 동작은 동일 하지만 디버거 프레젠테이션 매우 복잡할 수 있습니다. 따라서 권장 하지는 않습니다를 사용 하는 **/opt: icf** 디버그에서 작은 코드 장점이 이러한 단점 보다 되지를 빌드합니다.

> [!NOTE]
> 때문에 **/opt: icf** 다른 함수나 읽기 전용 데이터 멤버에 할당 될 동일한 주소를 발생할 수 있습니다 (즉, **const** 변수를 사용 하 여 컴파일하면 **/Gy**), 함수 또는 읽기 전용 데이터 멤버에 대해 고유한 주소에 종속 된 프로그램을 중단할 수 있습니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](gy-enable-function-level-linking.md)를 참조하세요.

**LBR** &#124; **NOLBR**

합니다 **/OPT:LBR** 하 고 **/OPT:NOLBR** 옵션 ARM 이진 파일에만 적용 됩니다. 특정 ARM 프로세서 분기 명령에는 제한된 범위가 있으므로 링커가 범위를 벗어난 주소로 점프하는 것을 감지하면 분기 명령의 대상 주소를 실제 대상을 목표로 하는 분기 명령이 포함된 코드 "아일랜드"의 주소로 대체합니다. 사용할 수 있습니다 **/OPT:LBR** 하 긴 분기 지침 검색 및 전체 코드 크기를 최소화 하기 위해 중간 코드 아일랜드 배치를 최적화 합니다. **/OPT:NOLBR** 최적화 하지 않고 현재 발생 긴 분기 지침에 대 한 코드 아일랜드를 생성 하도록 링커에 지시 합니다.

기본적으로 **/OPT:LBR** 증분 링크를 사용 하지 않는 경우 옵션이 설정 되어 있습니다. 지정 하지 않은 비증분 링크 하지만 긴 분기 최적화 하지 않으려면 **/OPT:NOLBR**합니다. 합니다 **/OPT:LBR** 옵션 증분 링크를 해제 합니다.

## <a name="remarks"></a>설명

명령줄을 사용 하면 링커가 기본적으로 **ICF, /opt: ref LBR**합니다. 하는 경우 **/debug** 기본값은 지정 된 **NOICF, /opt: noref NOLBR**합니다.

합니다 **/opt** 최적화 일반적으로 이미지 크기를 줄이고 프로그램 속도 향상 합니다. 일반 정품 빌드에 기본적으로 설정 된 이유는 이러한 향상 된이 기능, 더 큰 프로그램에서 길 수 있습니다.

링커 최적화는 추가 시간 들겠지만, 걸리지만 최적화 된 코드 및 처리 하 고 PDB에 쓰는 디버그 정보가 줄어듭니다 했을 때 더 많은 시간을 절약 링커를 수정할 수 있도록 더 적은 재배치에 고 작은 최종 이미지를 만듭니다 시간을 절약할 수도 있습니다. 최적화를 사용할 때이 발생할 수 있습니다 더 빠른 링크 시간이 전반적으로으로 분석에 적은 추가 비용 절감 링커 작은 이진 파일을 통해 전달 하는 시간을 기준으로 오프셋 보다 더 많을 수 있습니다.

합니다 **/opt** 인수 지정할 수 있습니다 함께 쉼표로 구분 합니다. 예를 들어, 대신의 **/opt: ref /opt: noicf**를 지정할 수 있습니다 **/opt: ref, NOICF**합니다.

사용할 수는 [/verbose](verbose-print-progress-messages.md) 에서 제거 되는 함수는 링커 옵션 **/opt: ref** 함수와로 정리 된 **/opt: icf**합니다.

**/opt** 인수에 자주 사용 하 여 만든 프로젝트에 대 한 설정이 합니다 **새 프로젝트** Visual Studio IDE에서 대화 고 일반적으로 디버그에 대 한 여러 값 및 릴리스 구성 합니다. 프로젝트에서 이러한 링커 옵션에 대 한 없는 값을 설정 하는 경우 명령줄에서 링커에서 사용 하는 기본 값과에서 다를 수 있는 프로젝트 기본값을 발생할 수 있습니다.

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:ICF 또는 OPT:REF 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 다음 속성 중 하나를 수정합니다.

   - **COMDAT 정리 사용**

   - **참조**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 OPT:LBR 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 옵션을 입력 **추가 옵션**:

   `/opt:lbr` 또는 `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 
  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> 속성을 참조하십시오.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
