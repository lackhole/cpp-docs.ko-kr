---
title: 왼쪽된 시프트 및 오른쪽 시프트 연산자 (&gt; &gt; 하 고 &lt; &lt;)
ms.date: 08/13/2018
f1_keywords:
- <<
- '>>'
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
ms.openlocfilehash: 2f118c11aab9fb2bbdd6cfa4f23425077b382b23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216423"
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>왼쪽된 시프트 및 오른쪽 시프트 연산자 (&gt; &gt; 하 고 &lt; &lt;)

비트 시프트 연산자는 오른쪽 시프트 연산자 (**&gt;&gt;**)의 비트를 이동 하는 *시프트 식* 오른쪽 및 왼쪽 시프트 연산자 (**&lt; &lt;**)의 비트를 이동 하는 *시프트 식* 왼쪽에 있습니다. <sup>1</sup>

## <a name="syntax"></a>구문

> *shift-expression* `<<` *additive-expression*
> *shift-expression* `>>` *additive-expression*

## <a name="remarks"></a>설명

> [!IMPORTANT]
> 다음 설명 및 예제에 유효한 Windows x86 및 x64 아키텍처에 대 한 합니다. 왼쪽 시프트 및 오른쪽 시프트 연산자의 구현은 크게 다른 Windows에서 ARM 장치에 대 한 합니다. 자세한 내용은 "시프트 연산자" 섹션을 참조 합니다 [Hello ARM](https://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx) 블로그 게시물.

## <a name="left-shifts"></a>왼쪽 시프트

왼쪽 시프트 연산자의 bits *시프트 식* 지정 된 위치 수 만큼 왼쪽으로 이동할 *덧셈 식을*합니다. 시프트 연산으로 비워진 비트 위치는 0으로 채워집니다. 왼쪽 시프트는 논리 시프트입니다(부호 비트를 포함해 끝에서 벗어나 이동한 비트는 무시됨). 비트 시프트에 대 한 자세한 내용은 참조 하세요. [비트 시프트](https://en.wikipedia.org/wiki/Bitwise_shift)합니다.

다음 예제에서는 부호 없는 숫자를 사용하는 왼쪽 시프트 연산을 보여 줍니다. 예제에서는 값을 비트 집합으로 나타내어 비트에서 어떤 일이 발생하는지 보여 줍니다. 자세한 내용은 [bitset 클래스](../standard-library/bitset-class.md)합니다.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short1 = 4;
    bitset<16> bitset1{short1};   // the bitset representation of 4
    cout << bitset1 << endl;  // 0b00000000'00000100

    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8
    bitset<16> bitset2{short2};
    cout << bitset2 << endl;  // 0b00000000'00001000

    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16
    bitset<16> bitset3{short3};
    cout << bitset3 << endl;  // 0b00000000'00010000
}
```

부호 비트가 영향을 받도록 부호 있는 숫자를 왼쪽 시프트하면 결과가 정의되지 않습니다. 다음 예제에서는 1비트가 부호 비트 위치로 왼쪽 이동하면 Visual C++에서 어떤 일이 발생하는지 보여 줍니다.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 16384;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;  // 0b01000000'00000000

    short short3 = short1 << 1;
    bitset<16> bitset3(short3);  // 16384 left-shifted by 1 = -32768
    cout << bitset3 << endl;  // 0b10000000'00000000

    short short4 = short1 << 14;
    bitset<16> bitset4(short4);  // 4 left-shifted by 14 = 0
    cout << bitset4 << endl;  // 0b00000000'00000000
}
```

## <a name="right-shifts"></a>오른쪽 시프트

오른쪽 시프트 연산자를 통해에서 비트 패턴이 *시프트 식* 지정 된 위치 수 만큼 오른쪽으로 이동할 *덧셈 식을*합니다. 부호 없는 숫자의 경우 시프트 연산으로 비워진 비트 위치는 0으로 채워집니다. 부호 있는 숫자의 경우 부호 비트는 비워진 비트 위치를 채우는 데 사용됩니다. 즉, 숫자가 양수이면 0이 사용되고 숫자가 음수이면 1이 사용됩니다.

> [!IMPORTANT]
> 부호 있는 음수의 오른쪽 시프트 결과는 구현에 따라 다릅니다. Visual C++는 부호를 사용하여 비워진 비트 위치를 채우지만 다른 구현도 마찬가지라는 보장은 없습니다.

이 예제에서는 부호 없는 숫자를 사용하는 오른쪽 시프트 연산을 보여 줍니다.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short11 = 1024;
    bitset<16> bitset11{short11};
    cout << bitset11 << endl;     // 0b00000100'00000000

    unsigned short short12 = short11 >> 1;  // 512
    bitset<16> bitset12{short12};
    cout << bitset12 << endl;     // 0b00000010'00000000

    unsigned short short13 = short11 >> 10;  // 1
    bitset<16> bitset13{short13};
    cout << bitset13 << endl;     // 0b00000000'00000001

    unsigned short short14 = short11 >> 11;  // 0
    bitset<16> bitset14{short14};
    cout << bitset14 << endl;     // 0b00000000'00000000
}
```

다음 예제에서는 부호 있는 양수를 사용하는 오른쪽 시프트 연산을 보여 줍니다.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 1024;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;     // 0b00000100'00000000

    short short2 = short1 >> 1;  // 512
    bitset<16> bitset2(short2);
    cout << bitset2 << endl;     // 0b00000010'00000000

    short short3 = short1 >> 11;  // 0
    bitset<16> bitset3(short3);
    cout << bitset3 << endl;     // 0b00000000'00000000
}
```

다음 예제에서는 부호 있는 음수를 사용하는 오른쪽 시프트 연산을 보여 줍니다.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short neg1 = -16;
    bitset<16> bn1(neg1);
    cout << bn1 << endl;  // 0b11111111'11110000

    short neg2 = neg1 >> 1; // -8
    bitset<16> bn2(neg2);
    cout << bn2 << endl;  // 0b11111111'11111000

    short neg3 = neg1 >> 2; // -4
    bitset<16> bn3(neg3);
    cout << bn3 << endl;  // 0b11111111'11111100

    short neg4 = neg1 >> 4; // -1
    bitset<16> bn4(neg4);
    cout << bn4 << endl;  // 0b11111111'11111111

    short neg5 = neg1 >> 5; // -1
    bitset<16> bn5(neg5);
    cout << bn5 << endl;  // 0b11111111'11111111
}
```

## <a name="shifts-and-promotions"></a>시프트 및 확장

시프트 연산자 양쪽에 있는 식은 정수 계열 형식이어야 합니다. 정수 계열 확장에 설명 된 규칙에 따라 수행 됩니다 [표준 변환](standard-conversions.md)합니다. 결과의 형식은 승격 된의 형식과 동일 *시프트 식*합니다.

다음 예에서 형식 변수의 **char** 승격 되는 **int**.

```cpp
#include <iostream>
#include <typeinfo>

using namespace std;

int main() {
    char char1 = 'a';

    auto promoted1 = char1 << 1;   // 194
    cout << typeid(promoted1).name() << endl;  // int

    auto promoted2 = char1 << 10;  // 99328
    cout << typeid(promoted2).name() << endl;  // int
}
```

## <a name="additional-details"></a>추가 정보

경우 시프트 연산의 결과가 정의 되지 않습니다 *덧셈 식을* 가 음수 이거나 *덧셈 식을* 보다 크거나 (승격)의 비트 수와 같고  *시프트 식*합니다. 시프트 연산이 없는 경우 수행 *덧셈 식을* 은 0입니다.

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned int int1 = 4;
    bitset<32> b1{int1};
    cout << b1 << endl;    // 0b00000000'00000000'00000000'00000100

    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int6 = int1 << 0;
    bitset<32> b6{int6};
    cout << b6 << endl;    // 0b00000000'00000000'00000000'00000100 (no change)
}
```

## <a name="footnotes"></a>각주

<sup>1</sup> 다음은 C + + 11 ISO 사양 (INCITS/ISO/IEC 14882-2011[2012]), 단원 5.8.2 및 5.8.3의에서 시프트 연산자에 대 한 설명을

`E1 << E2`의 값은 `E1` 왼쪽 이동된 `E2` 비트 위치입니다. 비워진 비트는 0으로 채워집니다. 하는 경우 `E1` 부호 없는 형식 결과의 값이 **E1 × 2**<sup>**E2**</sup>고 줄어든 나머지는 결과 형식에 나타낼 수 있는 최대 값 보다 1 더 큽니다. 그렇지 않고 `E1` 이 부호 있는 형식이 고 음수가 아닌 값 및 **E1 × 2**<sup>**E2** </sup> 이면 해당 부호 없는 형식의 결과 형식으로 표현할 수 결과 형식으로 변환할 값은 결과 값입니다. 그렇지 않으면 동작이 정의 되지 않습니다.

`E1 >> E2`의 값은 `E1` 오른쪽 이동된 `E2` 비트 위치입니다. 하는 경우 `E1` 부호 없는 형식 이거나 `E1` 부호 있는 형식이 고 음수가 아닌 값에는 결과 값의 몫의 정수 부분 **E1/2**<sup>**E2** </sup>. `E1`이 부호 있는 형식이고 음수인 경우 결과 값은 구현 시 정의됩니다.

## <a name="see-also"></a>참고자료

[이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
