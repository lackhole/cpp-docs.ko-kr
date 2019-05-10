---
title: 컴파일러 오류 C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: 8a4a2011124056af7064c8241450e1f3613776a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406706"
---
# <a name="compiler-error-c3073"></a>컴파일러 오류 C3073

'type': ref 클래스에 사용자 정의 복사 생성자가 없습니다

에 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일, 컴파일러에서 참조 형식에 대 한 복사 생성자를 생성 하지 않습니다. 모든 **/clr** 컴파일 복사할 형식의 인스턴스로 예상 되는 경우 참조 형식에 대 한 복사 생성자를 직접 정의 해야 합니다.

자세한 내용은 [ C++ 참조 형식에 대 한 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3073를 생성합니다.

```
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```