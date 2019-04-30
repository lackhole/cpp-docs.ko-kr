---
title: 링커 도구 오류 LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 7290a90dfd92d84c4632e7f9dd38d36eccd4ac27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386332"
---
# <a name="linker-tools-error-lnk2020"></a>링커 도구 오류 LNK2020

확인 되지 않은 ' token '토큰

유사 하지만 정의 되지 않은 외부 오류가 된다는 점이 메타 데이터를 통해 참조 됩니다. 메타 데이터의 모든 함수 및 데이터를 정의 합니다.

해결 방법:

- 누락 된 함수 또는 데이터를 정의 합니다. 또는

- 개체 파일 또는 누락 된 함수 또는 데이터는 이미 정의 된 라이브러리를 포함 합니다.

## <a name="example"></a>예제

다음 샘플 LNK2020를 생성합니다.

```
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

## <a name="example"></a>예제

LNK2020는 관리 되는 템플릿 형식의 변수를 만들지만 형식을 인스턴스화하지 않습니다 하는 경우에 발생 합니다.

다음 샘플 LNK2020를 생성합니다.

```
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```