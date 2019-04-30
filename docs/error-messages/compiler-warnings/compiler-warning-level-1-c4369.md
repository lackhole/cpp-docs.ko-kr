---
title: 컴파일러 경고(수준 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b374b67fa3319be35490358d7664bcb45bc640db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207032"
---
# <a name="compiler-warning-level-1-c4369"></a>컴파일러 경고(수준 1) C4369

'열거자': 열거자 값 'value' '형식으로 나타낼 수 없습니다, 값은 'new_value'

열거자는 지정된 된 기본 형식에 대 한 최대값 보다 클 수를 계산 했습니다.  이 오버플로가 발생 하 고 컴파일러 래핑된 형식의 가능한 최소값인 열거자 값입니다.

## <a name="example"></a>예제

다음 샘플 C4369를 생성합니다.

```
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```