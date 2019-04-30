---
title: 컴파일러 경고(수준 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: c864feb2478e9f99ad6e4c0087dcef72b55de601
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397266"
---
# <a name="compiler-warning-level-1-c4566"></a>컴파일러 경고(수준 1) C4566

현재 코드 페이지 (페이지)에서 유니버설 문자 이름 'char' 문자를 나타낼 수 없습니다.

현재 ANSI 코드 페이지에 있는 모든 유니코드 문자를 나타낼 수 있습니다.

와이드 문자열 (2 바이트 문자)에 없는 반면 좁은 문자열 (1 바이트 문자) 멀티 바이트 문자로 변환 됩니다.

다음 샘플에서는 C4566 오류가 생성 됩니다.

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```