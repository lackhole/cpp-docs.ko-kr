---
title: 컴파일러 경고 (수준 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: ab3108c60c18276e8e4797c7cfde1b66535dbaaa
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627429"
---
# <a name="compiler-warning-level-1-c4129"></a>컴파일러 경고 (수준 1) C4129

' character ': 문자 이스케이프 시퀀스를 인식할 수 없습니다.

문자 또는 문자열 상수에서 백슬래시 (\\) 뒤에 나오는 `character`는 유효한 이스케이프 시퀀스로 인식 되지 않습니다. 백슬래시는 무시 되 고 인쇄 되지 않습니다. 백슬래시 다음에 나오는 문자가 인쇄 됩니다.

단일 백슬래시를 인쇄 하려면 이중 백슬래시 (\\\\)를 지정 합니다.

2\.13.2 C++ 섹션의 표준은 이스케이프 시퀀스에 대해 설명 합니다.

다음 샘플에서는 C4129를 생성 합니다.

```cpp
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```