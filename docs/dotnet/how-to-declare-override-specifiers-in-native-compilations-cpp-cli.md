---
title: '방법: Override 지정자 선언 (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: db74ef226242ec8f4f70f2769fbc8ba102a808c8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777183"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>방법: 네이티브 컴파일에 Override 지정자 선언 (C++/CLI)

[봉인](../extensions/sealed-cpp-component-extensions.md), [추상](../extensions/abstract-cpp-component-extensions.md), 및 [재정의](../extensions/override-cpp-component-extensions.md) 사용 하지 않는 컴파일에 사용할 **/ZW** 또는 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.

> [!NOTE]
>  ISO C + + 11 표준 언어에는 [재정의](../cpp/override-specifier.md) 식별자와 [최종](../cpp/final-specifier.md) 식별자와 Visual Studio 사용에서을 지 `final` 대신 `sealed` 는 코드에서 네이티브 전용으로 컴파일됩니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예에서는 `sealed` 네이티브 컴파일에 유효 합니다.

### <a name="code"></a>코드

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예에서는 `override` 네이티브 컴파일에 유효 합니다.

### <a name="code"></a>코드

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example"></a>예제

### <a name="description"></a>설명

이 예에서는 `abstract` 네이티브 컴파일에 유효 합니다.

### <a name="code"></a>코드

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>참고자료

[Override 지정자](../extensions/override-specifiers-cpp-component-extensions.md)
