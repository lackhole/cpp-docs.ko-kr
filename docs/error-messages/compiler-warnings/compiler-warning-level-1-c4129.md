---
title: 컴파일러 경고 (수준 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: dc4f4c4c1feeba543ce0baa71e1ee5dfd81fdcae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310958"
---
# <a name="compiler-warning-level-1-c4129"></a>컴파일러 경고 (수준 1) C4129

'character': 문자 이스케이프 시퀀스를 인식할 수 없는

합니다 `character` 백슬래시 다음 (\\) 문자 또는 문자열 상수는 유효한 이스케이프 시퀀스도 인식 되지 않습니다. 백슬래시는 무시 되 고 인쇄 되지 않습니다. 백슬래시 다음의 문자가 출력 됩니다.

단일 백슬래시를 인쇄 하려면 이중 백슬래시를 지정 합니다 (\\\\).

C++ standard 2.13.2 단원의 이스케이프 시퀀스에 설명 합니다.

다음 샘플에서는 C4129 오류가 생성 됩니다.

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```