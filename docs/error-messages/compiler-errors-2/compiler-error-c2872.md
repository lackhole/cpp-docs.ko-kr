---
title: 컴파일러 오류 C2872
ms.date: 11/04/2016
f1_keywords:
- C2872
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
ms.openlocfilehash: 103998c7872b683c7405796ee28bd550246ae9bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257616"
---
# <a name="compiler-error-c2872"></a>컴파일러 오류 C2872

'*symbol*' : ambiguous symbol

컴파일러는 참조 하는 기호를 확인할 수 없습니다. 범위에서 지정한 이름 가진 둘 이상의 기호를 합니다. 컴파일러에서 모호한 기호에 대 한 검색 파일 위치 및 선언에 대 한 오류 메시지를 다음에 나오는 참고를 참조 하세요. 이 문제를 해결 하려면을 정규화 모호한 기호 해당 네임 스페이스, 예를 들어,를 사용 하 여 `std::byte` 또는 `::byte`합니다. 사용할 수도 있습니다는 [네임 스페이스 별칭](../../cpp/namespaces-cpp.md#namespace_aliases) 소스 코드에서 기호를 명확히 구분 하는 경우 포함 된 네임 스페이스를 사용 하기 위해 편리한 짧은 이름을 지정 하 합니다.

C2872 헤더 파일을 포함 하는 경우 발생할 수 있습니다는 [지시문을 사용 하 여](../../cpp/namespaces-cpp.md#using_directives), 및 후속 헤더 파일이 포함 되어에 지정 된 네임 스페이스에 있는 형식을 포함 하는 `using` 지시문입니다. 지정 된 `using` 헤더 파일 사용 하 여 지정 된 모든 해야만 지시문 `#include`합니다.

C2872 Visual Studio 2013 간의 충돌로 인해 발생할 수 있습니다 합니다 `Windows::Foundation::Metadata::Platform` 열거형 형식 및 C++CX 정의 된 `Platform` 네임 스페이스입니다. 이 문제를 해결 하려면 다음이 단계를 수행 합니다.

- 프로젝트 파일에서 "네임 스페이스 Windows::Foundation::Metadata using" 절을 제거 합니다.

- 이 네임 스페이스에 포함 된 모든 형식에 대 한 정규화 된 이름을 지정 합니다.

## <a name="example"></a>예제

모호한 참조가 라는 변수에 수 있기 때문에 다음 샘플에서는 C2872, `i`두; 같은 이름 가진 변수는 범위:

```cpp
// C2872.cpp
// compile with: cl /EHsc C2872.cpp
namespace A {
   int i;
}

using namespace A;
int i;
int main() {
   ::i++;   // ok, uses i from global namespace
   A::i++;   // ok, uses i from namespace A
   i++;   // C2872 ambiguous: ::i or A::i?
   // To fix this issue, use the fully qualified name
   // for the intended variable.
}
```
