---
title: /O 옵션(코드 최적화)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: ffd3023120f1d930a24ccef6fa297594062322df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320424"
---
# <a name="o-options-optimize-code"></a>/O 옵션(코드 최적화)

**/O** 옵션은 최대 속도 또는 최소 크기의 코드를 만드는 데 도움이 되도록 다양한 최적화를 제어합니다.

- [/O1](o1-o2-minimize-size-maximize-speed.md)은 최소 크기 코드를 생성하는 최적화의 조합을 설정합니다.

- [/O2](o1-o2-minimize-size-maximize-speed.md)는 최대 속도를 내는 코드로 최적화하는 조합을 설정합니다.

- [/Ob](ob-inline-function-expansion.md) 인라인 함수 확장을 제어 합니다.

- [/Od](od-disable-debug.md)는 컴파일 속도를 향상시키고 디버깅을 간소화하기 위해 최적화를 사용하지 않도록 설정합니다.

- [/Og](og-global-optimizations.md) 전역 최적화를 사용 합니다.

- [/Oi](oi-generate-intrinsic-functions.md)는 적절한 함수 호출을 위한 내장 함수를 생성합니다.

- [/Os](os-ot-favor-small-code-favor-fast-code.md)는 크기 최적화를 속도 최적화보다 우선하도록 컴파일러에 지시합니다.

- [/Ot](os-ot-favor-small-code-favor-fast-code.md)(기본 설정)는 속도 최적화를 크기 최적화보다 우선하도록 컴파일러에 지시합니다.

- [/Ox](ox-full-optimization.md) 다양한 속도에 중점을 두어 최적화를 선택하는 옵션을 조합합니다. **/O2** 최적화의 엄격한 하위집합입니다.

- [/Oy](oy-frame-pointer-omission.md)는 보다 빠른 함수 호출을 위해 호출 스택에서 프레임 포인터를 생성하지 않도록 합니다.

## <a name="remarks"></a>설명

여러 **/O** 옵션을 단일 옵션문으로 결합할 수 있습니다. 예를들어 **/Odi**는 **/Od /Oi**와 같습니다. 특정 옵션은 상호 배타적이므로 함께 사용할 경우 컴파일러 오류가 발생합니다. 자세한 내용은 개별 **/O** 옵션을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
