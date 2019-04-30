---
title: /Zc:rvalueCast(형식 변환 규칙 적용)
ms.date: 03/06/2018
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: e5a6abd3b85136b05ae58ebc8750aa9120cabc33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315783"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast(형식 변환 규칙 적용)

경우는 **/zc: rvaluecast** 옵션을 지정 하면 컴파일러는 c++11 표준에 따라 캐스트 연산의 결과로 rvalue 참조 형식의 올바르게 식별 합니다. 이 옵션이 지정되지 않은 경우 컴파일러 동작은 Visual Studio 2012와 동일합니다.

## <a name="syntax"></a>구문

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>설명

하는 경우 **/zc: rvaluecast** 컴파일러는 c++11 표준의 섹션 5.4 따르며 캐스트 식 비참조 형식에서 발생할 수 있으며 비 함수 형식 rvalue 참조가 발생 하는 캐스트 식만 처리 된 형식 rvalue입니다. 기본적으로 이거나 **/Zc:rvalueCast-** 를 지정한 경우 컴파일러는 비호환 고 rvalue로 rvalue 참조는 모든 캐스트 식을 처리 합니다. 준수 및 오류 캐스트를 제거 하기를 사용 하는 것이 좋습니다 **/zc: rvaluecast**합니다.

기본적으로 **/zc: rvaluecast** 해제 되어 (**/Zc:rvalueCast-**). 합니다 [/ permissive-](permissive-standards-conformance.md) 컴파일러 옵션에는 암시적으로이 옵션을 설정 하지만 사용 하 여 재정의할 수 있습니다 **/Zc:rvalueCast-** 합니다.

사용 하 여 **/zc: rvaluecast** rvalue 참조 형식을 사용 하는 함수에 캐스트 식을 인수로 전달 하는 경우. 기본 동작은 컴파일러 오류를 발생 시킵니다 [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) 때 컴파일러가 잘못 판단 캐스트 식의 형식입니다. 이 예제에서는 올바른 컴파일러 오류를 보여 줍니다. 때 코드 **/zc: rvaluecast** 지정 하지 않으면:

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

보고하지 않는 것이 적절한 경우 기본 컴파일러 동작이 오류 C2102를 보고하지 않을 수도 있습니다. 이 예에서 컴파일러는 오류를 보고 하지 경우 id 캐스트에서 만든 rvalue의 주소가 사용 되 면 **/zc: rvaluecast** 지정 하지 않으면:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: rvaluecast** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
