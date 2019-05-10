---
title: 코드 최적화
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: f44fb734c8441e10b656c5326c8df4bf6879499a
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220186"
---
# <a name="optimizing-your-code"></a>코드 최적화

실행 파일을 최적화 하 여 빠른 실행 속도 및 작은 코드 크기 간의 균형을 얻을 수 있습니다. 이 항목에서는 Visual Studio 코드를 활용할 수 있도록 제공 하는 메커니즘 중 일부를 설명 합니다.

## <a name="language-features"></a>언어 기능

다음 항목에서는 C의 최적화 기능 중 일부 /C++ 언어입니다.

[최적화 Pragma 및 키워드](optimization-pragmas-and-keywords.md) \
키워드 및 pragma는 성능 향상을 위해 코드에서 사용할 수 있는 목록입니다.

[컴파일러 옵션 범주별 목록](reference/compiler-options-listed-by-category.md) \
목록을 **/O** 특히 실행 속도 또는 코드 크기에 영향을 주는 컴파일러 옵션입니다.

[Rvalue 참조 선언 자: & &](../cpp/rvalue-reference-declarator-amp-amp.md) \
Rvalue 참조의 구현을 지원 *의미 체계 이동*합니다. 이동 의미 체계는 템플릿 라이브러리를 이러한 템플릿을 사용 하는 응용 프로그램의 성능을 구현 하는 데 사용 됩니다 크게 향상 하는 경우.

### <a name="the-optimize-pragma"></a>최적화 pragma

최적화 된 코드의 한 섹션에서 오류가 발생 하거나 시간이 느려졌습니다, 하는 경우 사용할 수 있습니다 합니다 [최적화](../preprocessor/optimize.md) pragma를 해당 섹션에 대 한 최적화를 해제 합니다.

다음과 같이 두 개의 pragma 사이 코드를 묶습니다.

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>프로그래밍 방법

최적화를 사용 하 여 코드를 컴파일할 때 경고 메시지가 나타날 수 있습니다. 최적화 된 코드에만 관련 되기 때문에이 동작이 필요 합니다. 이러한 경고에 주의 하면 여러 최적화 문제를 방지할 수 있습니다.

프로그램 속도 최적화 하면 코드가 더 느리게 실행 발생할 수 있습니다. 일부 최적화 속도 대 한 코드 크기를 늘리기 때문입니다. 예를 들어, 인라인 함수 함수 호출의 오버 헤드를 제거 합니다. 그러나 인라인 너무 많은 코드를 너무 큰 가상 메모리 페이지의 번호를 증가 오류는 프로그램을 수행할 수 있습니다. 따라서 제거 함수 호출에서 얻은 속도 메모리 스와핑이에 손실 될 수 있습니다.

다음 항목에는 바람직한 프로그래밍 방식도 설명합니다.

[시간이 중요 한 코드를 개선 하기 위한 팁](tips-for-improving-time-critical-code.md) \
좋은 코딩 방법을 더 나은 성능을 얻을 수 있습니다. 이 항목에서는 코딩 시간이 중요 한 코드 부분을 만족 스럽게 수행 하는지 확인 하는 데 도움이 되는 방법을 제안 합니다.

[최적화에 대 한 유용한 정보](optimization-best-practices.md) \
응용 프로그램을 최적화 하는 최선의 방법에 대 한 일반적인 지침을 제공 합니다.

## <a name="debugging-optimized-code"></a>최적화 된 코드 디버깅

최적화 컴파일러에서 생성 된 코드가 변경 될 수 있으므로 응용 프로그램을 디버깅 하 고 성능을 측정 하는 다음 코드를 최적화 하는 것이 좋습니다.

다음 항목에서는 빌드 릴리스를 디버그 하는 방법에 대 한 정보를 제공 합니다.

- [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)

- [방법: 최적화된 코드 디버그](/visualstudio/debugger/how-to-debug-optimized-code)

- [부동 소수점 숫자의 정밀도가 떨어지는 이유](why-floating-point-numbers-may-lose-precision.md)


다음 항목 작성, 로드 및 실행 코드를 최적화 하는 방법에 대 한 정보를 제공 합니다.

- [컴파일러 처리량 향상](improving-compiler-throughput.md)

- [함수 이름을 () 없이 사용하면 코드가 생성되지 않음](using-function-name-without-parens-produces-no-code.md)

- [인라인 어셈블리 최적화](../assembler/inline/optimizing-inline-assembly.md)

- [ATL 프로젝트에 대해 컴파일러 최적화 지정](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [로드 시 클라이언트 응용 프로그램의 성능을 향상 시키려면 어떤 최적화 기술을 사용 해야 합니까?](../build/dll-frequently-asked-questions.md#mfc_optimization)


## <a name="in-this-section"></a>단원 내용

[최적화 Pragma 및 키워드](optimization-pragmas-and-keywords.md) \
[컴파일러 처리량 향상](improving-compiler-throughput.md) \
[부동 소수점 숫자 정밀도 떨어지는 이유](why-floating-point-numbers-may-lose-precision.md) \
[IEEE 부동 소수점 표시](ieee-floating-point-representation.md) \
[시간이 중요 한 코드를 개선 하기 위한 팁](tips-for-improving-time-critical-code.md) \
[코드 없이 생성 함수 이름을 () 없이 사용](using-function-name-without-parens-produces-no-code.md) \
[최적화에 대 한 유용한 정보](optimization-best-practices.md) \
[프로필 기반 최적화](profile-guided-optimizations.md) \
[프로필 기반 최적화 환경 변수](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[방법: 여러 개의 PGO 프로필을 단일 프로필로 병합](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](reference/c-cpp-building-reference.md)
