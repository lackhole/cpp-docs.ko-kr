---
title: 컴파일러 오류 C2835
ms.date: 11/04/2016
f1_keywords:
- C2835
helpviewer_keywords:
- C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
ms.openlocfilehash: 069514d1a5d2b16e1175bbc1ce0c796bee64110a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406836"
---
# <a name="compiler-error-c2835"></a>컴파일러 오류 C2835

사용자 정의 변환 'type' 형식 매개 변수를 사용합니다.

사용자 정의 형식 변환 정식 매개 변수를 사용할 수 없습니다.

다음 샘플에서는 C2835를 생성합니다.

```
// C2835.cpp
class A {
public:
   char v_char;

   A() {
      v_char = 'A';
   };
   operator char(char a) {   // C2835
   // try the following line instead
   // operator char() {
      return v_char + 1;
   };
};

int main() {
   A a;
}
```