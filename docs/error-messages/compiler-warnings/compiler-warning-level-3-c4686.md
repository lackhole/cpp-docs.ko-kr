---
title: 컴파일러 경고(수준 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 5e23e6aa69fe8a59e3dfd22af7e33780c223cdd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401607"
---
# <a name="compiler-warning-level-3-c4686"></a>컴파일러 경고(수준 3) C4686

> '*사용자 정의 형식*': 동작 변경 되었을 수 있습니다, udt 반환 호출 규칙이

## <a name="remarks"></a>설명

클래스 템플릿 특수화가 없는 반환 형식에 사용 되기 전에 정의 됩니다. C4686; 확인 되는 클래스를 인스턴스화하는 모든 항목 인스턴스를 선언 하거나 멤버에 액세스 (C\<int >:: 아무 것도) 옵션 이기도 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

## <a name="example"></a>예제

대신 다음 사용해 보세요.

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```