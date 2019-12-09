---
title: 컴파일러 오류 C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 85381b237480b86b59c33f02601a1b9dc644a5a4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761532"
---
# <a name="compiler-error-c3539"></a>컴파일러 오류 C3539

' type ': 템플릿 인수는 ' a u t o '를 포함 하는 형식일 수 없습니다.

표시 된 템플릿 인수 형식은 `auto` 키워드의 사용을 포함할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. `auto` 키워드를 사용 하 여 템플릿 인수를 지정 하지 마십시오.

## <a name="example"></a>예제

다음 예에서는 C3539를 생성 합니다.

```cpp
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>참조

[auto 키워드](../../cpp/auto-keyword.md)
