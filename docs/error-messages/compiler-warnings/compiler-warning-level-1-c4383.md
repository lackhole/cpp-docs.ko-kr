---
title: 컴파일러 경고(수준 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 2510dda59047632e2a4823f734feeffd0c0a5b02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390440"
---
# <a name="compiler-warning-level-1-c4383"></a>컴파일러 경고(수준 1) C4383

'instance_dereference_operator':; 사용자 정의 된 'operator' 연산자가 있으면 핸들 역참조의 의미가 변경 수 연산자는 피연산자에 대 한 명시적 정적 함수로 작성

관리 되는 형식에서 역참조 연산자의 사용자 정의 인스턴스 재정의 추가 하면 잠재적으로 핸들의 개체를 반환 하는 형식의 역참조 연산자의 기능을 재정의 합니다. 고려 역참조 연산자는 static 및 사용자 정의 작성 합니다.

자세한 내용은 [개체 연산자 (^)에 대 한 핸들](../../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) 하 고 [추적 참조 연산자](../../extensions/tracking-reference-operator-cpp-component-extensions.md)합니다.

또한 인스턴스 연산자는 참조 된 메타 데이터를 통해 다른 언어 컴파일러를 사용할 수 있습니다. 자세한 내용은 [사용자 정의 연산자 (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플 C4383를 생성합니다.

```
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```