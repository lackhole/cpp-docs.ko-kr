---
title: 최적화에 대 한 유용한 정보
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++, optimization
- optimization, best practices
ms.assetid: f3433148-7255-4ca6-8a4f-7c31aac88508
ms.openlocfilehash: edb036292b87593a3f8bb9b3f5ec5f7beb84c3a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274172"
---
# <a name="optimization-best-practices"></a>최적화에 대 한 유용한 정보

이 문서에서는 시각적 개체의 최적화에 대 한 몇 가지 모범 사례를 설명 C++입니다.

## <a name="compiler-and-linker-options"></a>컴파일러 및 링커 옵션

### <a name="profile-guided-optimization"></a>프로필 기반 최적화

Visual C++ 지원 *프로필 기반 최적화* (PGO). 이 최적화는 응용 프로그램의 뒷부분에 나오는 최적화를 수행 하는 응용 프로그램의 계측된 된 버전의 교육 실행에서 프로필 데이터를 사용 합니다. PGO 사용 시간이 걸릴 수 있습니다, 되므로 모든 개발자가 사용 하는 항목이 없을 있지만 PGO를 사용 하 여 제품의 최종 릴리스 빌드에 대 한 권장지 않습니다. 자세한 내용은 [프로필 기반 최적화](profile-guided-optimizations.md)합니다.

또한 *전체 프로그램 최적화* (링크 타임 코드 생성으로 인식) 및 **/o1** 하 고 **/o2** 최적화 향상 되었습니다. 일반적으로 이러한 옵션 중 하나를 사용 하 여 컴파일된 응용 프로그램을 이전 버전의 컴파일러를 사용 하 여 컴파일된 동일한 응용 프로그램 보다 빠를 수 됩니다.

자세한 내용은 [/GL (전체 프로그램 최적화)](reference/gl-whole-program-optimization.md) 하 고 [/o1, / o2 (크기 최소화, 속도 최대화)](reference/o1-o2-minimize-size-maximize-speed.md)합니다.

### <a name="which-level-of-optimization-to-use"></a>사용 하도록 최적화 수준

가능한, 최종 릴리스 빌드 프로필 기반 최적화를 사용 하 여 컴파일해야 합니다. 없으면 간의 균형을 사용 하 여 빌드할 수 인프라가 부족 하 여 계측 된 빌드를 실행 하거나 시나리오에 액세스할 수 없는 경우에 권장 되는 사항은 전체 프로그램 최적화를 사용 하 여 구성 합니다.

합니다 **/Gy** 스위치의도 매우 유용 합니다. 생성 참조 되지 않은 Comdat 및 COMDAT 제거 하더라도 링커 더 많은 유연성을 제공 각 함수에 대 한 별도 COMDAT 정리 합니다. 사용 하는 유일한 단점은 **/Gy** 디버그할 때 문제를 일으킬 수 있으므로 됩니다. 따라서 사용 하 여 일반적으로 좋습니다. 자세한 내용은 [/Gy(함수 수준 링크 사용)](reference/gy-enable-function-level-linking.md)를 참조하세요.

64 비트 환경에 연결 하는 것에 대 한 것이 좋습니다 사용 하는 **ICF, /opt: ref** 링커 옵션 및 32 비트 환경 **/opt: ref** 것이 좋습니다. 자세한 내용은 [/OPT (최적화)](reference/opt-optimizations.md)합니다.

또한 강력한도 최적화 된 릴리스 빌드에서 디버그 기호를 생성 하는 것이 좋습니다. 생성된 된 코드에 영향을 주지 않습니다 하 고 해결할 수 있도록 하는 경우 응용 프로그램을 디버그 하기가 매우 쉬워집니다 있어야 합니다.

### <a name="floating-point-switches"></a>부동 소수점 스위치

합니다 **/Op** 컴파일러 옵션이 제거 되 고 부동 소수점 최적화를 다루는 다음 네 가지 컴파일러 옵션이 추가 되었습니다.

|||
|-|-|
|**/fp:precise**|기본 권장 사항을 이며 대부분의 경우에 사용 해야 합니다.|
|**/fp:fast**|예를 들어 게임에에서는 가장 중요 성능 인지 하는 것이 좋습니다. 이렇게 하면 가장 빠른 성능.|
|**/fp:strict**|권장 되는 경우 정확한 부동 소수점 예외 및 IEEE 동작이 필요 합니다. 이렇게 하면 성능이 가장 낮습니다.|
|**/fp:except[-]**|와 함께에서 사용할 수 있습니다 **/fp: strict** 또는 **/fp: 정확한**, 있지만 **/fp:fast**합니다.|

자세한 내용은 [/fp(부동 소수점 동작 지정)](reference/fp-specify-floating-point-behavior.md)를 참조하세요.

## <a name="optimization-declspecs"></a>최적화 declspec

이 섹션에서 살펴보겠습니다 성능을 위해 프로그램에서 사용할 수 있는 두 개의 declspec: `__declspec(restrict)` 고 `__declspec(noalias)`입니다.

`restrict` declspec만 적용할 수와 같은 포인터를 반환 하는 함수 선언 `__declspec(restrict) void *malloc(size_t size);`

`restrict` declspec 별칭이 지정 되지 않은 포인터를 반환 하는 함수에 사용 됩니다. 이 키워드는 C 런타임 라이브러리 구현의 `malloc` 하므로 이미 사용 중인 현재 프로그램의 (하지 않는 경우 해제 된 후에 메모리를 사용 하는 등 잘못 된 것) 포인터 값을 반환 하지 것입니다.

`restrict` declspec 컴파일러 컴파일러 최적화를 수행 하는 것에 대 한 자세한 정보를 제공 합니다. 컴파일러가 결정 하는 데 가장 어려운 일 중 하나를 다른 포인터를 포인터 별칭은 및 컴파일러를 통해이 정보를 사용 하 여 크게입니다.

지적할이 구성은 것 컴파일러가 확인 하는 것과 컴파일러에는 약속입니다. 프로그램이이 사용 하면 `restrict` declspec 프로그램 잘못 된 동작이 있을 수 부적절 하 게 합니다.

자세한 내용은 [제한](../cpp/restrict.md)합니다.

`noalias` declspec도 함수에만 적용 됩니다 및 함수는 반 순수 함수를 나타냅니다. 반 순수 함수를 참조 하거나 지역 변수, 인수 및 인수 1 차 간접 참조를 수정 하는 경우 이러한 declspec를 컴파일러에 약속 이며 응용 프로그램을 중단 하는 함수가 전역 변수를 참조 하거나 두 번째 수준의 간접 참조는 포인터 인수는 컴파일러의 코드를 생성할 수 있습니다.

자세한 내용은 [noalias](../cpp/noalias.md)를 참조하세요.

## <a name="optimization-pragmas"></a>최적화 pragma

몇 가지 유용한 pragma 코드 최적화도 있습니다. 첫 번째 하겠습니다 `#pragma optimize`:

```cpp
#pragma optimize("{opt-list}", on | off)
```

이 pragma를 사용 하면 함수에서 함수에서 기준 최적화 수준을 설정할 수 있습니다. 이 이상적인 드문 최적화를 사용 하 여 지정된 된 함수 컴파일될 때 응용 프로그램이 충돌 하는 위치입니다. 단일 함수에 대 한 최적화를 해제 하려면이 사용할 수 있습니다.

```cpp
#pragma optimize("", off)
int myFunc() {...}
#pragma optimize("", on)
```

자세한 내용은 [최적화](../preprocessor/optimize.md)합니다.

인라인 처리는 컴파일러가 수행 하 고이 동작을 수정 하는 데 도움이 되는 pragma 가지에 대 한 이야기 여기는 가장 중요 한 최적화 중 하나입니다.

`#pragma inline_recursion` 원하는 응용 프로그램을 재귀 호출을 인라인 할 수 있는지 여부를 지정 하는 데 유용 합니다. 기본적으로 해제 됩니다. 단순 재귀 작은 함수에 대 한이 설정을 켜면 할 수 있습니다. 자세한 내용은 [inline_recursion](../preprocessor/inline-recursion.md)합니다.

깊이 제한 하는 것에 대 한 다른 유용한 pragma 인라인 처리는 `#pragma inline_depth`합니다. 이 일반적으로 함수는 프로그램의 크기를 제한 하려는 경우에 유용 합니다. 자세한 내용은 [inline_depth](../preprocessor/inline-depth.md)합니다.

## <a name="restrict-and-assume"></a>__restrict 및 \__assume

시각적 개체에는 키워드의 두 가지가 있습니다 C++ 성능을 향상 시킬 수 있는: [__restrict](../cpp/extension-restrict.md) 하 고 [__assume](../intrinsics/assume.md)합니다.

먼저이 점에 유의 해야 하는 `__restrict` 및 `__declspec(restrict)` 서로 구분 합니다. 어느 정도 관련이 있지만 그에 따라 의미가 다릅니다. `__restrict` 형식 한정자를 같은입니다 `const` 또는 `volatile`, 포인터 형식에 대해서만 합니다.

사용 하 여 수정 된 포인터 `__restrict` 라고는 *포인터 __restrict*합니다. __Restrict 포인터가 통해서만 액세스할 수 있는 포인터를 \__restrict 포인터입니다. 즉, 가리키는 데이터에 액세스 하려면 다른 포인터를 사용할 수 없습니다는 \__restrict 포인터입니다.

`__restrict` 시각적 개체에 대 한 강력한 도구를 수 있습니다 C++ 최적화 프로그램 있지만 주의 사용 하 여 사용 합니다. 부적절 하 게 사용 되는 경우 최적화 프로그램은 응용 프로그램이 중단 되는 최적화를 수행할 수 있습니다.

합니다 `__restrict` 키워드를 대체 합니다 **/Oa** 이전 버전에서 전환 합니다.

사용 하 여 `__assume`, 개발자는 컴파일러가 일부 변수 값에 대 한 가정을를 알 수 있습니다.

예를 들어 `__assume(a < 5);` 변수의 코드 줄에는 최적화 프로그램에 알립니다 `a` 5 보다 작게 됩니다. 다시 컴파일러에는 약속입니다. 경우 `a` 실제로 6이 시점에서 프로그램에 다음 컴파일러 최적화 한 후 프로그램의 동작을 예상할 수 있는 되지 않을 수 있습니다. `__assume` switch 문의 및/또는 조건식 전에 가장 유용 합니다.

몇 가지 제한 사항이를 `__assume`입니다. 먼저 같은 `__restrict`것이 권장 사항일 뿐, 이므로 컴파일러는 무료 무시 합니다. 또한 `__assume` 현재 변수 부등식 상수 에서만 작동 합니다. 기호화 된 부등식 예를 들어, 전파 되지 않습니다 assume(a < b) 합니다.

## <a name="intrinsic-support"></a>내장 함수 지원

내장 함수는 함수를 호출 하는 컴파일러 호출에 대 한 기본 정보에는 라이브러리의 함수를 호출 하는 대신 해당 함수에 대 한 코드를 내보냅니다. 헤더 파일 \<intrin.h > 각 지원 되는 하드웨어 플랫폼에 대 한 모든 사용할 수 있는 내장 함수를 포함 합니다.

내장 함수는 프로그래머가 어셈블리를 사용 하지 않고도 코드를 심층적으로 이동 하는 기능을 제공 합니다. 내장 함수를 사용 하 여 여러 장점이 있습니다.

- 코드 이식성이 향상 됩니다. 다양 한 내장 함수는 여러 CPU 아키텍처에서 사용할 수 있습니다.

- 코드는 코드는 여전히 C로 작성 되므로 읽기 쉽게 /C++입니다.

- 코드는 컴파일러 최적화의 이점을 가져옵니다. 컴파일러 개선 되, 대로 내장 함수에 대 한 코드 생성 향상 됩니다.

자세한 내용은 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)합니다.

## <a name="exceptions"></a>예외

한 성능 예외를 사용 하 여 연결 된 키를 누릅니다. 특정 최적화를 수행할 수 없도록 컴파일러를 방해 하는 try 블록을 사용 하는 경우 몇 가지 제한 사항이 도입 되었습니다. X86 플랫폼에서 추가 성능 저하는 코드 실행 중 생성 해야 하는 추가 상태 정보로 인해 블록을 시도 합니다. 64 비트 플랫폼에서 시도 블록을 성능 저하 되지 않습니다 하지만 예외가 throw 된 처리기를 찾기 및 스택 해제 과정은 비용이 높을 수 있습니다.

따라서 다음에 실제로 필요 하지 않은 코드를 try/catch 블록 추가 되지 않도록 하는 것이 좋습니다. 예외를 사용 해야 하는 경우 가능 하면 동기 예외를 사용 합니다. 자세한 내용은 [Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)을 참조하세요.

마지막으로, 예외적인 경우에만 대 한 예외를 throw 합니다. 일반 제어 흐름에 대 한 예외를 사용 하 여 성능이 저하 될 가능성이 확인 합니다.

## <a name="see-also"></a>참고자료

- [코드 최적화](optimizing-your-code.md)
