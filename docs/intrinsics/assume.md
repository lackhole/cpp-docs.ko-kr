---
title: __assume
ms.date: 10/09/2018
f1_keywords:
- __assume
- _assume
- __assume_cpp
helpviewer_keywords:
- __assume keyword [C++]
ms.assetid: d8565123-b132-44b1-8235-5a8c8bff85a7
ms.openlocfilehash: 1d84e9306dcd468153f38cc0c3085b43388e1dbd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029423"
---
# <a name="assume"></a>__assume

**Microsoft 전용**

최적화 프로그램에 힌트를 전달합니다.

## <a name="syntax"></a>구문

```
__assume(
   expression
)
```

#### <a name="parameters"></a>매개 변수

*expression*<br/>
true로 평가된다고 간주되는 식입니다.

## <a name="remarks"></a>설명

최적화 프로그램은 키워드가 표시되는 지점에서 `expression`으로 표시되는 조건이 true이며 변수에 할당하는 등의 작업을 통해 `expression`을 수정할 때까지 true로 유지된다고 가정합니다. `__assume`이 최적화 프로그램에 전달하는 힌트를 적절하게 사용하면 최적화 성능을 개선할 수 있습니다.

모순(항상 false로 평가되는 식)으로 작성되는 `__assume` 문은 항상 `__assume(0)`으로 처리됩니다. 코드가 정상적으로 동작하지 않으면 앞에서 설명한 대로 정의한 `expression`이 유효하며 true인지 확인합니다. 올바른 `__assume(0)` 동작에 대한 자세한 내용은 아래의 설명을 참조하세요.

> [!WARNING]
>  프로그램에서는 연결 가능한 경로에 잘못된 `__assume` 문을 포함하지 않아야 합니다. 컴파일러가 잘못된 `__assume` 문에 연결할 수 있는 경우 프로그램이 예측할 수 없으며 위험할 수 있는 동작을 수행할 수 있습니다.

`__assume`은 올바른 내장 함수가 아니며, 함수로 선언할 필요도 없고 `#pragma intrinsic` 지시문에서 사용할 수도 없습니다. 코드는 생성되지 않지만 최적화 프로그램에서 생성하는 코드가 영향을 받습니다.

사용 하 여 `__assume` 에 [ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 만 경우 assert는 복구할 수 없습니다. 후속 오류 복구 코드가 있는 어설션에서는 `__assume`을 사용하지 마세요. 이렇게 하면 컴파일러가 오류 처리 코드를 최적화하지 않을 수도 있습니다.

`__assume(0)` 문은 특수한 경우입니다. 연결할 수 없는 코드 경로를 나타내려는 경우 `__assume(0)`을 사용합니다. 다음 예제에서는 `__assume(0)`을 사용하여 스위치 문의 기본 사례에 연결할 수 없음을 나타내는 방법을 보여 줍니다. 여기에는 가장 일반적인 `__assume(0)` 사용 방식이 나와 있습니다.

이전 버전과 호환성에 대 한 **_assume** 에 대 한 동의어가 **__assume** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 는 지정 합니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__assume`|x86, ARM, x64|

## <a name="example"></a>예제

```
// compiler_intrinsics__assume.cpp
#ifdef DEBUG
# define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__) )
#else
# define ASSERT(e)    ( __assume(e) )
#endif

void func1(int i)
{
}

int main(int p)
{
   switch(p){
      case 1:
         func1(1);
         break;
      case 2:
         func1(-1);
         break;
      default:
         __assume(0);
            // This tells the optimizer that the default
            // cannot be reached. As so, it does not have to generate
            // the extra code to check that 'p' has a value
            // not represented by a case arm. This makes the switch
            // run faster.
   }
}
```

`__assume(0)`을 사용하는 경우 기본 사례에 연결할 수 없음을 최적화 프로그램에 알립니다. 예제에서는 `p`에 사용 가능한 입력이 1이나 2뿐이라는 것을 프로그래머가 알고 있음을 보여 줍니다. `p`에 대해 다른 값이 전달되면 프로그램은 유효하지 않은 상태가 되어 예측할 수 없는 동작을 수행합니다.

`__assume(0)` 문으로 인해 컴파일러는 `p`가 case 문에 표시되지 않는 값을 포함하는지 여부를 테스트하는 코드를 생성하지 않습니다. 이 코드가 작동하도록 하려면 `__assume(0)` 문이 기본 사례 본문의 첫 번째 문이어야 합니다.

컴파일러는 `__assume`을 기반으로 코드를 생성하므로 `__assume` 문 내의 식이 런타임에 false이면 해당 코드가 올바르게 실행되지 않을 수 있습니다. 식이 런타임에 항상 true로 평가될지 확실치 않으면 `assert` 함수를 사용하여 코드를 보호할 수 있습니다.

```
#define ASSERT(e)    ( ((e) || assert(__FILE__, __LINE__)), __assume(e) )
```

그러나 이처럼 `assert`를 사용하면 컴파일러가 이 문서 앞부분에서 설명한 기본 사례 최적화를 수행할 수 없습니다. 따라서 다음과 같이 별도의 매크로를 대신 사용할 수 있습니다.

```
#ifdef DEBUG
# define NODEFAULT   ASSERT(0)
#else
# define NODEFAULT   __assume(0)
#endif

   default:
      NODEFAULT;
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)