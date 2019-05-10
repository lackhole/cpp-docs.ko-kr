---
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: cb4be000c3c41862d5b4df766d21ae1cddeb6838
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243993"
---
# <a name="void-c"></a>void (C++)

함수 반환 형식으로 사용된 경우 **void** 키워드는 함수가 값을 반환하지 않도록 지정합니다. 함수의 매개 변수 목록에 사용된 경우 void는 함수가 매개 변수를 사용하지 않도록 지정합니다. 포인터 선언에 사용된 경우 void는 포인터를 '범용'으로 지정합니다.

포인터 형식이 `void *`이면 포인터가 **const** 또는 **volatile** 키워드로 선언되지 않은 모든 변수를 가리킬 수 있습니다. void 포인터는 다른 형식으로 캐스팅되지 않은 경우 역참조할 수 없습니다. void 포인터를 다른 형식의 데이터 포인터로 변환할 수 있습니다.

void 포인터는 함수를 가리킬 수 있지만 C++의 클래스 멤버는 가리킬 수 없습니다.

void 형식의 변수는 선언할 수 없습니다.

## <a name="example"></a>예제

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[기본 형식(C++)](../cpp/fundamental-types-cpp.md)