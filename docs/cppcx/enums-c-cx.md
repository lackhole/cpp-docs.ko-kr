---
title: 열거형(C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: f16a288a0b928b74ef42de5781fd1b54930927d6
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57752144"
---
# <a name="enums-ccx"></a>열거형(C++/CX)

C + + /cli CX 지원 합니다 `public enum class` 표준 c + +과 유사한 키워드를 `scoped  enum`입니다. `public enum class` 키워드를 사용하여 선언된 열거자를 사용할 경우 열거형 식별자를 사용하여 각 열거자 값의 범위를 지정해야 합니다.

### <a name="remarks"></a>설명

`public enum class` 과 같은 액세스 지정자가 없는 `public`는 표준 C++ [범위 지정 열거형](../cpp/enumerations-cpp.md)으로 처리됩니다.

A `public enum class` 또는 `public enum struct` 선언은 내부 형식이 모든 정수 계열 형식 가질 수 있는 Windows 런타임 자체에서는 int32 또는 uint32 플래그 열거형 형식 이어야 합니다. 다음 구문에서는 `public enum class` 또는 `public enum struct`부분을 설명합니다.

이 예제에서는 public enum 클래스를 정의하는 방법을 보여 줍니다.

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

다음 예제에서는 클래스를 사용하는 방법을 보여 줍니다.

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>예제

다음 예제에서는 열거형을 선언하는 방법을 보여 줍니다.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

다음 예제에서는 해당 숫자로 캐스팅하고 비교를 수행하는 방법을 보여 줍니다. 열거자 `One` 의 사용은 `Enum1` 열거형 식별자로 범위가 지정되고, 열거자 `First` 는 `Enum2`로 범위가 지정됩니다.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>참고자료

[형식 시스템](../cppcx/type-system-c-cx.md)<br/>
[Visual c + + 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[네임 스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
