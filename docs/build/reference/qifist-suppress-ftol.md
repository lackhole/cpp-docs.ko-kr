---
title: /QIfist(_ftol 사용 안 함)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 7af88c91793688d23cf35177ae7a5250b04832a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319293"
---
# <a name="qifist-suppress-ftol"></a>/QIfist(_ftol 사용 안 함)

더 이상 사용되지 않습니다. 부동 소수점 형식에서 정수 계열 형식으로 변환해야 할 때 도우미 함수 `_ftol` 이 호출되지 않도록 합니다.

## <a name="syntax"></a>구문

```
/QIfist
```

## <a name="remarks"></a>설명

> [!NOTE]
>  **/Qifist** 은 영어로 x86 대상 컴파일러가 컴파일러 옵션이 x64를 대상으로 한 컴파일러에서 제공 되지 않습니다. 또는 Arm입니다.

부동 소수점 형식에서 정수 계열 형식으로 변환하는 것 외에도 `_ftol` 함수를 사용하면 제어 워드의 비트 10과 11을 설정하여 부동 소수점 단위(FPU)의 반올림 모드가 0(잘라내기)을 향하게 합니다. 이것은 부동 소수점 단위에서 정수 형식으로의 변환이 ANSI C 표준(숫자의 소수 부분이 삭제)에 설명된 대로 변환됨을 보장합니다. **/QIfist**를 사용할 때는 이 사항이 적용되지 않습니다. 반올림 모드는 Intel 참조 매뉴얼에 설명된 대로 4가지 모드 중 하나가 됩니다.

- 가장 가까운 쪽으로 반올림(원에서 균등한 거리인 경우 짝수)

- 음의 무한대 방향으로 반올림합니다.

- 양의 무한대 방향으로 반올림 합니다.

- 0으로 반올림

사용할 수는 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C 런타임 함수 FPU의 반올림 동작을 수정 합니다. 반올림 모드 FPU의 기본값은 "가장 가까운 쪽으로 반올림"입니다. 사용 하 여 **/QIfist** 위험이 있지만 응용 프로그램의 성능을 향상 시킬 수 있습니다. 반올림 모드를 사용 하 여 빌드한 코드를 기반으로 신뢰 하기 전에 영향을 받는 코드 부분을 철저히 테스트 해야 **/QIfist** 프로덕션 환경에서.

[/arch (x86)](arch-x86.md)와 **/QIfist**는 동일한 컴파일 대상에 사용할 수 없습니다.

> [!NOTE]
>  **/Qifist** 는 실제로 기본적으로 비트도 부동 소수점을 부동으로 영향을 가리키지 반올림 (하는 발생 모든 계산 후), C-스타일 (0)으로 반올림 하는 것에 대 한 플래그를 설정 하면 부동 소수점 계산 달라질 수 있습니다. **/Qifist** 코드가 부동 소수점 숫자의 소수 부분을 자르기의 예상된 동작으로 사용할 수 해야 합니다. 확실 하지 않은 경우 사용 하지 마세요 **/QIfist**합니다.

Visual Studio 2005부터는 **/QIfist** 옵션이 더 이상 사용되지 않습니다. 컴파일러는 float에서 int로의 변환 속도를 크게 향상시켰습니다. 더 이상 사용되지 않는 컴파일러 옵션의 목록은 [범주별 컴파일러 옵션 목록](compiler-options-listed-by-category.md)의 **더 이상 사용되지 않거나 삭제된 컴파일러 옵션**을 참조합니다.

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
