---
title: 컴파일러 오류 C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 248431afb25aa4b9480818f76388f6ad56d8e006
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777928"
---
# <a name="compiler-error-c3821"></a>컴파일러 오류 C3821

'function': 관리 되지 않는 함수에서 관리 되는 형식 또는 함수를 사용할 수 없습니다

인라인 어셈블리로 함수 또는 [setjmp](../../c-runtime-library/reference/setjmp.md) 값 형식 또는 관리 되는 클래스를 포함할 수 없습니다. 이 오류를 해결 하려면 인라인 어셈블리를 제거 하 고 `setjmp` 또는 관리 되는 개체를 제거 합니다.

C3821은 vararg 함수에 자동 저장소를 사용 하려는 경우에 발생할 수 있습니다.  자세한 내용은 참조 하세요. [가변 인수 목록 (...) (C++/CLI) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) 하 고 [ C++ 참조 형식에 대 한 의미 체계를 스택](../../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3821.

```
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>예제

다음 샘플에서는 C3821.

```
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
