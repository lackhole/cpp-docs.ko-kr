---
title: 컴파일러 오류 C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: 7d6c8627fe0904dd2fe81dd805d8f87bbebf29c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173238"
---
# <a name="compiler-error-c3470"></a>컴파일러 오류 C3470

'type': 클래스에 인덱서(인덱싱된 기본 속성)와 operator[]가 동시에 포함될 수 없습니다.

하나의 형식으로 기본 인덱서와 연산자[]를 모두 정의할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3470을 생성합니다.

```
// C3470.cpp
// compile with: /clr
using namespace System;

ref class R {
public:
   property int default[int] {
      int get(int i) {
         return i+1;
      }
   }

   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470
};

int main() {
   R ^ r = gcnew R;
   // return r[9] + r["32"] - 42;
}
```