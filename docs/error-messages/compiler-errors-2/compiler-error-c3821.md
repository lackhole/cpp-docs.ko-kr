---
title: 컴파일러 오류 C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 25023277258d33ab77bde18f6cdfabc862f50a63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741744"
---
# <a name="compiler-error-c3821"></a>컴파일러 오류 C3821

' function ': 관리 되는 형식 또는 함수는 관리 되지 않는 함수에서 사용할 수 없습니다.

인라인 어셈블리 또는 [setjmp](../../c-runtime-library/reference/setjmp.md) 함수는 값 형식 또는 관리 되는 클래스를 포함할 수 없습니다. 이 오류를 해결 하려면 인라인 어셈블리를 제거 하 고 관리 되는 개체를 `setjmp` 하거나 제거 합니다.

C3821는 vararg 함수에서 자동 저장소를 사용 하려는 경우에도 발생할 수 있습니다.  자세한 내용은 [가변 인수 목록 (...) (C++/cli)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) 및 [ C++ 참조 형식에 대 한 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3821를 생성 합니다.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>예제

다음 샘플에서는 C3821를 생성 합니다.

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
