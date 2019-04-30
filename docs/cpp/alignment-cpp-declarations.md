---
title: 맞춤(C++ 선언)
ms.date: 11/04/2016
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 0709ad414af3f167a64d9c89c342690015190287
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155396"
---
# <a name="alignment-c-declarations"></a>맞춤(C++ 선언)

C++의 하위 수준 기능 중 하나는 특정 하드웨어 아키텍처를 최대한 활용하기 위해 메모리 내 개체의 정확한 맞춤을 지정하는 기능입니다. 기본적으로 컴파일러는 해당 크기 값에 클래스 및 구조체 멤버를 맞춥니다: bool 및 char 맞춰집니다 1 바이트 경계, short는 2 바이트에서 int는 4 바이트 long long, double 및 long double은 8 바이트입니다. 대부분의 시나리오에서는 기본 맞춤이 이미 최적화되어 있기 때문에 맞춤에 주의할 필요가 없습니다. 그러나 데이터 구조에 대해 사용자 지정 맞춤을 지정하여 상당한 성능 향상이나 메모리 절약 효과를 얻을 수 있는 경우도 있습니다. Visual Studio 2015 이전에는 Microsoft 특정 키워드 __alignof 및 declspec(alignas)를 사용하여 기본값보다 큰 맞춤을 지정할 수 있었습니다. Visual Studio 2015에서부터 C + + 11 표준 키워드를 사용 해야 [alignof 및 alignas](../cpp/alignof-and-alignas-cpp.md) 최대 코드 이식성에 대 한 합니다. 새 키워드는 내부적으로 Microsoft 특정 확장과 동일한 방식으로 동작하며 해당 확장에 대한 설명서가 새 키워드에도 적용됩니다. 참조 [__alignof 연산자](../cpp/alignof-operator.md) 하 고 [맞춤](../cpp/align-cpp.md) 자세한 내용은 합니다. C++ 표준 #pragma Microsoft를 사용 해야 하므로 대상 플랫폼에 대 한 컴파일러 기본값 보다 작은 경계에 맞추기 위한 압축 동작을 지정 하지 않습니다 [pack](../preprocessor/pack.md) 경우.

C++ 표준 라이브러리를 제공 합니다 [aligned_storage 클래스](../standard-library/aligned-storage-class.md) 에 대 한 사용자 지정 맞춤을 사용 하 여 데이터 구조에 대 한 메모리 할당 및 [aligned_union 클래스](../standard-library/aligned-union-class.md) 맞춤을 지정 하는 것에 대 한 trivial이 아닌 생성자 또는 소멸자를 사용 하 여 공용 구조체입니다.

## <a name="about-alignment"></a>맞춤 정보

맞춤은 숫자 주소 모듈로 2의 거듭제곱으로 표현된 메모리 주소의 속성입니다. 예를 들어 주소 0x0001103F의 모듈로 4는 3입니다. 해당 주소는 4n+3에 맞춰지며, 여기서 4는 선택된 2의 거듭제곱을 나타냅니다. 주소 맞춤은 선택된 2의 거듭제곱에 따라 달라집니다. 동일한 주소의 모듈로 8은 7입니다. 맞춤이 Xn+0인 경우 주소가 X에 맞춰집니다.

CPU는 메모리에 저장된 데이터에서 작동하는 명령을 실행하고 데이터는 메모리의 해당 주소로 식별됩니다. 해당 주소 외에도 단일 데이터에는 크기가 있습니다. 주소가 크기에 맞춰진 경우 데이터가 자연스럽게 맞춰진 것으로 간주되고, 그렇지 않은 경우 잘못 맞춰진 것으로 간주됩니다. 예를 들어 8바이트 부동 소수점 데이터는 데이터 식별에 사용된 주소가 8에 맞춰진 경우 자연스럽게 맞춰집니다.

데이터 맞춤에 대한 컴파일러 처리. 장치 컴파일러는 데이터가 잘못 맞춰지지 않도록 데이터를 할당하려고 합니다.

단순 데이터 형식의 경우 컴파일러에서 데이터 형식 크기(바이트)의 배수인 주소를 할당합니다. 따라서 컴파일러는 long 형식의 변수에 4의 배수인 주소를 할당하고 주소의 하위 2비트를 0으로 설정합니다.

또한 컴파일러는 구조의 각 요소를 자연스럽게 맞추는 방식으로 구조를 채웁니다. 다음 코드 예제에서 구조체 x_의 구조를 고려해 보세요.

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} MyStruct;
```

컴파일러는 자연스럽게 맞춰지도록 이 구조를 채웁니다.

다음 코드 예제에서는 컴파일러가 채워진 구조를 memory:Copy에 배치하는 방법을 보여 줍니다.

```cpp
// Shows the actual memory layout
struct x_
{
   char a;            // 1 byte
   char _pad0[3];     // padding to put 'b' on 4-byte boundary
   int b;            // 4 bytes
   short c;          // 2 bytes
   char d;           // 1 byte
   char _pad1[1];    // padding to make sizeof(x_) multiple of 4
}
```

1. 두 선언에서 모두 sizeof(구조체 x_)가 12바이트로 반환됩니다.

1. 두 번째 선언에는 다음 두 개의 패딩 요소가 포함되어 있습니다.

1. char _pad0[3] - 4바이트 경계에 int b 멤버를 맞춥니다.

1. char _pad1[1] - 구조체 _x bar[3] 구조의 배열 요소를 맞춥니다.

1. 패딩은 자연스러운 액세스를 허용하는 방식으로 bar[3]의 요소를 맞춥니다.

다음 코드 예제에서는 bar[3] 배열 레이아웃을 보여 줍니다.

```
adr offset   element
------   -------
0x0000   char a;         // bar[0]
0x0001   char pad0[3];
0x0004   int b;
0x0008   short c;
0x000a   char d;
0x000b   char _pad1[1];

0x000c   char a;         // bar[1]
0x000d   char _pad0[3];
0x0010   int b;
0x0014   short c;
0x0016   char d;
0x0017   char _pad1[1];

0x0018   char a;         // bar[2]
0x0019   char _pad0[3];
0x001c   int b;
0x0020   short c;
0x0022   char d;
0x0023   char _pad1[1];
```

## <a name="see-also"></a>참고자료

[데이터 구조 맞춤](http://en.wikipedia.org/wiki/Data_structure_alignment)