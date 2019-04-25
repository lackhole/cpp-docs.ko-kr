---
title: 컴파일러 오류 C3162
ms.date: 11/04/2016
f1_keywords:
- C3162
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
ms.openlocfilehash: f522a2de77e03a7c5f8f8dc774d62744417344fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174291"
---
# <a name="compiler-error-c3162"></a>컴파일러 오류 C3162

'type': 소멸자가 있는 참조 형식은 정적 데이터 멤버 ' 유형으로 사용할 수 없습니다

공용 언어 런타임 클래스는 정적 멤버 함수에도 포함 되어 있으면 사용자 정의 소멸자를 실행 하는 시기를 알 수 없습니다.

개체를 명시적으로 삭제 하지 않는 한 소멸자가 실행 되지 않습니다.

자세한 내용은 다음 항목을 참조하세요.

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)

- [일반적인 Visual C++ 64비트 마이그레이션 문제](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>예제

다음 샘플 C3162를 생성합니다.

```
// C3162.cpp
// compile with: /clr /c
ref struct A {
   ~A() { System::Console::WriteLine("in destructor"); }
   static A i;   // C3162
   static A^ a = gcnew A;   // OK
};

int main() {
   A ^ a = gcnew A;
   delete a;
}
```