---
title: 컴파일러 오류 C2665
ms.date: 11/04/2016
f1_keywords:
- C2665
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
ms.openlocfilehash: 63817c4181edb942f43f41c24fb10278d14f397e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386891"
---
# <a name="compiler-error-c2665"></a>컴파일러 오류 C2665

'function': 'type' 형식에서 매개 변수 number2를 변환할 수 number1 오버 로드

오버 로드 된 함수의 매개 변수는 필수 형식으로 변환할 수 없습니다.  가능한 해결 방법:

- 변환 연산자를 제공 합니다.

- 명시적 변환을 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2665 오류가 발생 합니다.

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```