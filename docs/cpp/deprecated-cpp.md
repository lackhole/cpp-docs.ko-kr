---
title: 사용되지 않음 (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: 34f9c10cd898b0359463d5933141822576fa4a11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398955"
---
# <a name="deprecated-c"></a>사용되지 않음 (C++)

이 항목에서는 Microsoft 전용에 대해 declspec 선언은 사용 되지 않습니다. C + + 14에 대 한 자세한 `[[deprecated]]` 특성 및 해당 특성 및 Microsoft 전용 declspec 또는 pragma를 사용 하는 경우에 대 한 지침 참조 [ C++ 표준 특성](attributes.md)합니다.

아래 설명 된 예외를 사용 하 여는 **더 이상 사용 되지** 선언으로 동일한 기능을 제공 합니다 [사용 되지 않는](../preprocessor/deprecated-c-cpp.md) pragma:

- 합니다 **사용 되지 않는** 선언을 지정할 수 특정 형태의 함수 오버 로드를 사용 하지 않는 반면에 pragma 형태 모든 오버 로드 된 형태의 함수 이름에 적용 합니다.

- 합니다 **사용 되지 않는** 선언 컴파일 타임에 표시 되는 메시지를 지정할 수 있습니다. 메시지의 텍스트는 매크로에서 제공될 수 있습니다.

- 매크로 이후 지원 되지 않는 됨으로 표시할 수만 있습니다 합니다 **사용 되지 않는** pragma입니다.

컴파일러는 사용 되지 않는 식별자 또는 표준의 사용을 발견 하는 경우 [ `[[deprecated]]` ](attributes.md) 특성을 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 경고가 throw 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 함수를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 함수가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

## <a name="example"></a>예제

다음 샘플에서는 클래스를 사용되지 않는 것으로 표시하는 방법과 사용되지 않는 클래스가 사용되는 경우 컴파일 타임에 표시될 메시지를 지정하는 방법을 보여 줍니다.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)