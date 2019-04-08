---
title: 경고
ms.date: 11/04/2016
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: 1341472af22582635207a2bdff93b4367fd59330
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037752"
---
# <a name="warning-pragma"></a>경고 Pragma
컴파일러 경고 메시지의 동작을 선택적으로 수정할 수 있습니다.

## <a name="syntax"></a>구문

```
#pragma warning(
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )
#pragma warning( push[ ,n ] )
#pragma warning( pop )
```

## <a name="remarks"></a>설명

다음과 같은 경고 지정자 매개 변수를 사용할 수 있습니다.

|경고 지정자|의미|
|------------------------|-------------|
|*1, 2, 3, 4*|주어진 수준을 지정된 경고에 적용합니다. 기본적으로 해제되어 있는 지정된 경고를 설정하기도 합니다.|
|*default*|경고 동작을 기본값으로 다시 설정합니다. 기본적으로 해제되어 있는 지정된 경고를 설정하기도 합니다. 문서화된 기본 수준에서 경고가 생성됩니다.<br /><br /> 자세한 내용은 [Compiler Warnings That Are Off by Default](../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.|
|*사용 안 함*|지정된 경고 메시지를 생성하지 마십시오.|
|*오류*|지정된 경고를 오류로 보고합니다.|
|*once*|지정된 메시지를 한 번만 표시합니다.|
|*표시 안 함*|pragma의 현재 상태를 스택에 푸시하고 다음 줄에 지정된 경고를 비활성화한 후 pragma 상태가 다시 설정되도록 경고 스택을 표시합니다.|

다음 코드 문에서는 `warning-number-list` 매개 변수가 경고 번호를 여러 개 포함할 수 있으며 같은 pragma 지시문에 여러 `warning-specifier` 매개 변수를 지정할 수 있음을 보여 줍니다.

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

이 코드 문은 다음 코드와 기능적으로 동일합니다.

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning 4385 only once.
#pragma warning( once : 4385 )

// Report warning 4164 as an error.
#pragma warning( error : 164 )
```

컴파일러가 0에서 999 사이의 경고 번호에 4000을 추가합니다.

4700-4999 범위에 속하고 코드 생성과 관련된 경고 번호의 경우 컴파일러가 함수의 왼쪽 중괄호를 발견할 때 적용되는 경고의 상태가 나머지 함수에 적용됩니다. 사용 하는 **경고** pragma 번호가 4699 보다 큰 경고의 상태를 변경 하는 함수에만 적용 됩니다 함수 종료 된 후입니다. 다음 예제에서는 올바른 배치 **경고** 코드 생성 경고 메시지를 사용 하지 않으려면 pragma 차례로 복원 합니다.

```cpp
// pragma_warning.cpp
// compile with: /W1
#pragma warning(disable:4700)
void Test() {
   int x;
   int y = x;   // no C4700 here
   #pragma warning(default:4700)   // C4700 enabled after Test ends
}

int main() {
   int x;
   int y = x;   // C4700
}
```

본문의 마지막 설정이 전체 함수는 합니다 **경고** pragma 전체 함수에 적용 됩니다.

## <a name="push-and-pop"></a>푸시 및 팝

합니다 **경고** pragma는 또한 다음 구문을 지원 위치 *n* 경고 수준 (1 ~ 4)를 나타냅니다.

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

Pragma `warning( push )` 모든 경고에 대 한 현재 경고 상태를 저장 합니다. Pragma `warning( push, n )` 모든 경고의 현재 상태를 저장 하 고 글로벌 경고 수준을 설정 *n*합니다.

Pragma `warning( pop )` 스택에 푸시된 마지막 경고 상태를 팝 합니다. 간의 경고 상태에 대 한 변경 내용을 *푸시* 하 고 *pop* 취소 됩니다. 다음 예제를 고려해 보세요.

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

이 코드의 끝 *pop* 모든 경고의 상태를 복원 (4705, 4706, 4707 포함)를 코드의 시작 부분에 있습니다.

헤더 파일을 작성할 때 사용할 수 있습니다 *푸시* 하 고 *pop* 는 사용자가 경고 상태를 변경 해도 헤더를 올바르게 컴파일할 되도록 합니다. 사용 하 여 *푸시* 헤더의 시작 및 *pop* 끝입니다. 예를 들어, 경고 수준 4에서 완전히 컴파일되지 않는 헤더가 있을 경우 다음 코드를 사용하면 경고 수준이 3으로 변경되고 헤더 끝에서 원래의 경고 수준이 복원됩니다.

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

경고 표시 안 함 옵션 도움이 되는 컴파일러에 대 한 자세한 참조 [/FI](../build/reference/fi-name-forced-include-file.md) 하 고 [/w](../build/reference/compiler-option-warning-level.md)합니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)