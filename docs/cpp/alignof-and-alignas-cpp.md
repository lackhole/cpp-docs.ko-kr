---
title: alignof 및 alignas(C++)
ms.date: 11/04/2016
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
ms.openlocfilehash: 825df25494497e13d29212f7f951be8247b6f136
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155253"
---
# <a name="alignof-and-alignas-c"></a>alignof 및 alignas(C++)

**alignas** 형식 지정자는 변수 및 사용자 정의 형식의 사용자 지정 맞춤을 지정하는 포팅 가능한 C++ 표준 방법입니다. 마찬가지로 **alignof** 연산자도 지정된 형식 또는 변수의 맞춤을 얻는 포팅 가능한 표준 방법입니다.

## <a name="example"></a>예제

클래스, 구조체/공용 구조체 또는 개별 멤버에 **alignas**를 사용할 수 있습니다. 여러 **alignas** 지정자가 발견되는 경우 컴파일러는 가장 엄격한 지정자(가장 큰 값을 가진 지정자)를 선택합니다.

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>참고 항목

[맞춤](../cpp/alignment-cpp-declarations.md)
