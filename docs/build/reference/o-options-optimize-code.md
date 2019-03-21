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
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816128"
---
# <a name="o-options-optimize-code"></a>/O 옵션(코드 최적화)

합니다 **/O** 다양 한 옵션 제어 코드 최대 속도 또는 최소 크기를 만들 수 있도록 최적화 합니다.

- [/ O1](o1-o2-minimize-size-maximize-speed.md) 최소 크기 코드를 생성 하는 최적화의 조합을 설정 합니다.

- [/ O2](o1-o2-minimize-size-maximize-speed.md) 최대 속도 대 한 코드를 최적화 하는 최적화의 조합을 설정 합니다.

- [/Ob](ob-inline-function-expansion.md) 인라인 함수 확장을 제어 합니다.

- [/Od](od-disable-debug.md) 컴파일 속도 향상 및 디버깅을 간소화 하도록 최적화를 사용 하지 않도록 설정 합니다.

- [/Og](og-global-optimizations.md) 전역 최적화를 사용 합니다.

- [/Oi](oi-generate-intrinsic-functions.md) 적절 한 함수 호출에 대 한 내장 함수를 생성 합니다.

- [/Os](os-ot-favor-small-code-favor-fast-code.md) 크기 최적화 속도 최적화 보다 우선. 컴파일러에 지시 합니다.

- [/Ot](os-ot-favor-small-code-favor-fast-code.md) (기본 설정) 속도 최적화 크기 최적화 보다 우선. 컴파일러에 지시 합니다.

- [/Ox](ox-full-optimization.md) 다양 한 속도에 중점을 두어 최적화를 선택 하는 조합을 옵션입니다. 엄격한 하위 집합을 **/o2** 최적화 합니다.

- [/Oy](oy-frame-pointer-omission.md) 빠르게 함수 호출에 대 한 호출 스택에서 프레임 포인터를 생성 하지 않습니다.

## <a name="remarks"></a>설명

여러 결합할 수 있습니다 **/O** 단일 옵션 문으로 옵션입니다. 예를 들어 **/Odi** 와 같습니다 **/Od /Oi**합니다. 특정 옵션은 상호 배타적 이므로 함께 사용할 경우 컴파일러 오류가 발생 합니다. 개별 참조 **/O** 옵션을 참조 하십시오.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
