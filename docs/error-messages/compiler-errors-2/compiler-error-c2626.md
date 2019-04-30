---
title: 컴파일러 오류 C2626
ms.date: 11/04/2016
f1_keywords:
- C2626
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
ms.openlocfilehash: 434858991c23345e2a6c174c8f323000d42b9b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222886"
---
# <a name="compiler-error-c2626"></a>컴파일러 오류 C2626

'identifier': 익명 구조체 또는 공용 구조체에서는 전용 또는 보호된 데이터 멤버가 허용되지 않습니다.

익명 구조체 또는 공용 구조체의 멤버는 공용 액세스 권한이 있어야 합니다.

다음 샘플에서는 C2626을 생성합니다.

```
// C2626.cpp
int main() {
   union {
   protected:
      int j;     // C2626, j is protected
   private:
      int k;     // C2626, k is private
   };
}
```

이 문제를 해결하려면 전용 또는 보호된 태그를 제거하세요.

```
// C2626b.cpp
int main() {
   union {
   public:
      int i;   // OK, i is public
   };
}
```