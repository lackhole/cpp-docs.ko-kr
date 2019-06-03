---
title: 맞춤(C++ 선언)
description: Modern의 데이터 정렬을 지정 하는 방법을 C++입니다.
ms.date: 05/30/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: b6e03ac2b89624a0eb6602183d4ff4bf8b518f8d
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450777"
---
# <a name="alignment-c-declarations"></a>맞춤(C++ 선언)

C++의 하위 수준 기능 중 하나는 특정 하드웨어 아키텍처를 최대한 활용하기 위해 메모리 내 개체의 정확한 맞춤을 지정하는 기능입니다. 기본적으로 컴파일러는 해당 크기 값에 클래스 및 구조체 멤버를 맞춥니다: `bool` 하 고 `char` 1 바이트 경계에 `short` 2 바이트 경계에서 `int`에 `long`, 및 `float` 4 바이트 경계에 `long long`하십시오 `double`, 및 `long double` 8 바이트 경계에서. 대부분의 시나리오에서 필요가 기본 맞춤이 이미 최적화 때문에 맞춤을 사용 하 여 관여 해야 합니다. 그러나 경우에 따라 얻을 수 있습니다 상당한 성능 향상 이나 메모리 절약 효과 데이터 구조에 대 한 사용자 지정 맞춤을 지정 하 여. Visual Studio 2015 이전 Microsoft 관련 키워드를 사용할 수 있습니다 `__alignof` 고 `declspec(alignas)` 기본값 보다 큰 맞춤을 지정 합니다. Visual Studio 2015에서부터 C + + 11 표준 키워드를 사용 해야 [alignof 및 alignas](../cpp/alignof-and-alignas-cpp.md) 최대 코드 이식성에 대 한 합니다. 새 키워드는 Microsoft 전용 확장으로 내부에서 동일한 방식으로 작동합니다. 이러한 확장에 대 한 설명서는 새 키워드에도 적용 됩니다. 자세한 내용은 [__alignof 연산자](../cpp/alignof-operator.md) 하 고 [맞춤](../cpp/align-cpp.md)합니다. C++ #pragma Microsoft를 사용 해야 하므로 표준은 대상 플랫폼에 대 한 컴파일러 기본값 보다 작은 경계에 맞춤에 대 한 압축 동작 지정 하지 않습니다 [pack](../preprocessor/pack.md) 경우.

사용 된 [aligned_storage 클래스](../standard-library/aligned-storage-class.md) 사용자 지정 맞춤을 사용 하 여 데이터 구조의 메모리 할당에 대 한 합니다. 합니다 [aligned_union 클래스](../standard-library/aligned-union-class.md) 는 특수 한 생성자 또는 소멸자를 사용 하 여 공용 구조체의 맞춤을 지정 합니다.

## <a name="about-alignment"></a>맞춤 정보

맞춤은 숫자 주소 모듈로 2의 거듭제곱으로 표현된 메모리 주소의 속성입니다. 예를 들어 주소 0x0001103F 모듈로 4은 3입니다. 해당 주소는 4n+3에, 여기서 4는 선택된 된 2의 거듭제곱을 나타냅니다 정렬 되었다고 말합니다. 주소 맞춤은 선택된 된 2의 거듭제곱에 따라 달라 집니다. 동일한 주소의 모듈로 8은 7입니다. 맞춤이 Xn+0인 경우 주소가 X에 맞춰집니다.

Cpu는 메모리에 저장 된 데이터에서 작동 하는 지침을 실행 합니다. 데이터는 메모리의 해당 주소로 식별 됩니다. 단일 데이터 크기를 있습니다. 데이텀 이라고 *자연스럽 게 정렬* 해당 주소는 해당 크기에 따라 정렬 하는 경우. 라고 *불일치* 그렇지 않은 경우. 예를 들어는 8 바이트 부동 소수점 데이터를 식별 하기 위해 사용 되는 주소는 8 바이트 정렬을 있으면에 자연스럽 게 맞춥니다.

## <a name="compiler-handling-of-data-alignment"></a>데이터 맞춤 컴파일러 처리

컴파일러는 데이터 정렬 오류를 방지 하는 방식으로 데이터 할당을 시도 합니다.

단순 데이터 형식의 경우 컴파일러에서 데이터 형식 크기(바이트)의 배수인 주소를 할당합니다. 컴파일러가 형식의 변수에 주소를 할당 하는 예를 들어 `long` 아래쪽 주소 2 비트를 0으로 설정 하는 4의 배수가 되는 합니다.

또한 컴파일러는 구조체의 각 요소를 자연스럽 게 맞추는 방식으로 구조를 채웁니다. 구조를 `struct x_` 다음 코드 예제에서:

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

다음 코드 예제에서는 컴파일러가 채워진된 구조 메모리에 배치 하는 방법을 보여 줍니다.

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

1. () 선언 모두 반환 `sizeof(struct x_)` 12 바이트로 합니다.

1. 두 번째 선언에는 다음 두 개의 패딩 요소가 포함되어 있습니다.

1. `char _pad0[3]` 에 맞게는 `int b` 4 바이트 경계에 멤버

1. `char _pad1[1]` 구조체의 배열 요소를 맞추려면 `struct _x bar[3];`

1. 안쪽 여백을 맞춥니다 요소의 `bar[3]` 자연 스러운 액세스를 허용 하는 방식에서입니다.

다음 코드 예제는 `bar[3]` 배열 레이아웃:

```Output
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

[데이터 구조 맞춤](https://en.wikipedia.org/wiki/Data_structure_alignment)
