---
title: 컴파일러 오류 C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: dbc7186edfce6cc12a38fb2fc1dda08ac4a181c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300728"
---
# <a name="compiler-error-c2951"></a>컴파일러 오류 C2951

형식 선언이 전역 네임 스페이스 에서만 허용 됩니다 또는 클래스 범위

제네릭 또는 템플릿 클래스 외부 전역 또는 네임 스페이스 범위를 선언할 수 없습니다. 제네릭 또는 템플릿 선언에에서 포함 파일을 하는 경우 전역 범위에서 포함 파일 인지 확인 합니다.

다음 샘플에서는 C2951 오류가 생성 됩니다.

```
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951은 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```