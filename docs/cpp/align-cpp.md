---
title: 맞춤 (C++)
ms.date: 12/17/2018
f1_keywords:
- align_cpp
helpviewer_keywords:
- align __declspec keyword
- __declspec keyword [C++], align
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
ms.openlocfilehash: 1bfe6e7a4646be8cea622078b4d85f20f458e1c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258151"
---
# <a name="align-c"></a>맞춤 (C++)

Visual Studio 2015 이상 버전에서는 사용할 C + + 11 표준 `alignas` 지정자 맞춤을 제어 합니다. 자세한 내용은 [맞춤](../cpp/alignment-cpp-declarations.md)합니다.

**Microsoft 전용**

`__declspec(align(#))`를 사용하여 사용자 정의 데이터(예: 함수의 정적 할당 또는 자동 데이터)를 정확하게 제어합니다.

## <a name="syntax"></a>구문

> **__declspec( align(** *#* **) )** *declarator*

## <a name="remarks"></a>설명

최신 프로세서 명령을 사용하는 애플리케이션을 작성할 경우 몇 가지 새로운 제약 조건과 문제가 생깁니다. 특히 새로운 명령을 사용할 때 데이터를 16바이트 경계에 맞춰야 하는 경우가 많습니다. 또한 자주 사용하는 데이터를 특정 프로세서의 캐시 줄 크기에 맞춤으로써 캐시 성능이 향상됩니다. 예를 들어 크기가 32바이트 미만인 구조체를 정의할 경우 해당 구조체 형식의 개체가 효과적으로 캐시되도록 이 구조체를 32바이트에 맞출 수 있습니다.

\# 맞춤 값이입니다. 유효한 항목은 2, 4, 8, 16, 32 또는 64와 같이 1에서 8192(바이트) 사이에 속하는 2의 정수 제곱입니다. `declarator`는 aligned로 선언하는 데이터입니다.

형식의 값을 반환 하는 방법에 대 한 자세한 `size_t` 형식의 맞춤 요구 사항인를 참조 하십시오 [__alignof](../cpp/alignof-operator.md)합니다. 64 비트 프로세서를 대상으로 하는 경우 정렬 되지 않은 포인터를 선언 하는 방법에 대 한 자세한 내용은 [__unaligned](../cpp/unaligned.md)합니다.

사용할 수 있습니다 `__declspec(align(#))` 정의 하는 경우는 **구조체**를 **union**, 또는 **클래스**, 변수를 선언 하는 경우 또는 합니다.

컴파일러는 복사 또는 데이터 변형 작업 중에 데이터의 맞춤 특성 보존을 보장하거나 시도하지 않습니다. 예를 들어 [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) 사용 하 여 선언 된 구조체를 복사할 수 `__declspec(align(#))` 모든 위치에 있습니다. 일반 할당자-예를 들어 [malloc](../c-runtime-library/reference/malloc.md), C++ [new 연산자](new-operator-cpp.md), 및 Win32 할당자-일반적으로 충분히에 맞추지 않은 메모리 반환 `__declspec(align(#))` 구조 또는 구조체의 배열입니다. 복사 또는 데이터 변환 작업의 대상을 올바르게 정렬 될을 보장 하기 위해 사용 하 여 [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md), 하거나 고유한 할당자를 작성 합니다.

함수 매개 변수의 맞춤을 지정할 수 없습니다. 맞춤 특성을 포함하는 데이터가 스택의 값에 의해 전달되면 해당 맞춤은 호출 규칙을 통해 제어됩니다. 호출된 함수에서 데이터 맞춤이 중요한 경우에는 사용 전에 매개 변수를 올바르게 맞춰진 메모리로 복사합니다.

없이 `__declspec(align(#))`, 컴파일러는 대상 프로세서와 32 비트 프로세서에서 4 바이트 경계 최대 데이터 크기에 따라 자연 경계 및 64 비트 프로세서에서 8 바이트 경계에 데이터를 일반적으로 맞춥니다. 클래스 또는 구조체의 데이터는 최소한의 자연 맞춤 및 현재의 압축 설정(#pragma `pack` 또는 `/Zp` 컴파일러 옵션에서)으로 클래스나 구조체에 맞춰집니다.

이 예제에서는 `__declspec(align(#))`의 사용을 보여 줍니다.

```cpp
__declspec(align(32)) struct Str1{
   int a, b, c, d, e;
};
```

현재 이 형식에는 32비트 맞춤 특성이 포함되어 있습니다. 즉, 모든 정적 및 자동 인스턴스가 32바이트 경계에서 시작됩니다. 멤버로이 형식으로 선언 된 추가 구조체 형식은이 형식의 맞춤 특성 보존, 즉, 모든 구조체 `Str1` 요소는 32 이상의 맞춤 특성을 포함 하는 대로 합니다.

`sizeof(struct Str1)`는 32입니다. 즉, Str1 개체 배열을 만드는 경우 배열의 기준을 32바이트로 맞추면 배열의 각 멤버도 32바이트로 맞춰집니다. 동적 메모리에 해당 기준이 올바르게 맞춰진 배열을 만들려면 사용 [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md), 하거나 고유한 할당자를 작성 합니다.

구조체의 `sizeof` 값은 최종 멤버의 오프셋에 해당 멤버의 크기를 더하여 최대 멤버 맞춤 값 또는 전체 구조체 맞춤 값 중 더 큰 값의 가장 근사한 배수로 반올림한 값입니다.

컴파일러는 구조체 맞춤에 다음과 같은 규칙을 사용합니다.

- `__declspec(align(#))`로 재정의하지 않으면 스칼라 구조체 멤버의 맞춤은 최소 크기와 현재 압축입니다.

- `__declspec(align(#))`로 재정의하지 않으면 구조체의 멤버는 멤버의 최대 개별 맞춤입니다.

- 구조체 멤버는 이전 멤버 끝의 오프셋보다 크거나 같은 맞춤의 최소 배수인 부모 구조체의 시작 부분부터 오프셋에 배치됩니다.

- 구조체의 크기는 마지막 멤버의 오프셋 끝보다 크거나 같은 맞춤의 최소 배수입니다.

`__declspec(align(#))`는 맞춤 제한만 늘릴 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [align 예제](#vclrfalignexamples)

- [__Declspec(align(#))를 사용 하 여 새 형식 정의](#vclrf_declspecaligntypedef)

- [스레드 로컬 저장소에서 데이터 정렬](#vclrfthreadlocalstorageallocation)

- [데이터 압축과 함께 작동을 정렬 하는 방법](#vclrfhowalignworkswithdatapacking)

- [구조체 맞춤 예제](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 전용)

## <a name="vclrfalignexamples"></a> align 예제

다음 예제에서는 `__declspec(align(#))`가 데이터 구조체의 크기 및 맞춤에 영향을 주는 방식을 보여 줍니다. 예제에서는 다음과 같은 정의를 가정합니다.

```cpp
#define CACHE_LINE  32
#define CACHE_ALIGN __declspec(align(CACHE_LINE))
```

이 예제에서는 `S1`를 사용하여 `__declspec(align(32))` 구조체를 정의합니다. 변수 정의에 대해 또는 기타 형식 선언에서 사용되는 모든 `S1`은 32바이트로 맞춰집니다. `sizeof(struct S1)`는 32를 반환하고 `S1`은 16바이트 뒤에 정수 4개에 필요한 16 패딩 바이트를 둡니다. 각 **int** 멤버에는 4 바이트 맞춤이 필요 하지만 구조체 자체의 맞춤은 32로 선언 됩니다. 따라서 전체 맞춤은 32입니다.

```cpp
struct CACHE_ALIGN S1 { // cache align all instances of S1
   int a, b, c, d;
};
struct S1 s1;   // s1 is 32-byte cache aligned
```

이 예제에서는 최대 맞춤 요구 사항의 배수가 8의 배수인 16이므로 `sizeof(struct S2)`는 멤버 크기의 합계와 똑같은 16을 반환합니다.

```cpp
__declspec(align(8)) struct S2 {
   int a, b, c, d;
};
```

다음 예제에서 `sizeof(struct S3)`는 64를 반환합니다.

```cpp
struct S3 {
   struct S1 s1;   // S3 inherits cache alignment requirement
                  // from S1 declaration
   int a;         // a is now cache aligned because of s1
                  // 28 bytes of trailing padding
};
```

이 예제에서 `a`에는 자연 형식 맞춤(여기서는 4바이트)이 사용됩니다. 그러나 `S1`은 32바이트 맞춤이어야 합니다. 28바이트 패딩이 `a` 뒤에 나와 `s1`이 32 오프셋에서 시작됩니다. 그런 다음 `S4`가 구조체의 최대 맞춤 요구 사항인 `S1`의 맞춤 요구 사항을 상속합니다. `sizeof(struct S4)`가 64를 반환합니다.

```cpp
struct S4 {
   int a;
   // 28 bytes padding
    struct S1 s1;      // S4 inherits cache alignment requirement of S1
};
```

다음 3개의 변수 선언에도 `__declspec(align(#))`가 사용됩니다. 각 선언에서 변수가 32바이트 맞춤이어야 합니다. 배열의 경우 각 배열 멤버가 아니라 배열의 기준 주소가 32바이트 맞춤입니다. `sizeof`를 사용해도 각 배열 멤버의 `__declspec(align(#))` 값에 영향을 주지 않습니다.

```cpp
CACHE_ALIGN int i;
CACHE_ALIGN int array[128];
CACHE_ALIGN struct s2 s;
```

배열의 각 멤버를 맞추려면 다음과 같은 코드를 사용해야 합니다.

```cpp
typedef CACHE_ALIGN struct { int a; } S5;
S5 array[10];
```

이 예제에서는 구조체 자체를 맞추는 경우와 첫 번째 요소를 맞추는 경우의 결과는 같습니다.

```cpp
CACHE_ALIGN struct S6 {
   int a;
   int b;
};

struct S7 {
   CACHE_ALIGN int a;
               int b;
};
```

`S6`및 `S7`의 맞춤, 할당 및 크기 특성이 동일합니다.

이 예제에서 a, b, c, d의 시작 주소 맞춤은 각각 4, 1, 4, 1입니다.

```cpp
void fn() {
   int a;
   char b;
   long c;
   char d[10]
}
```

메모리가 힙에 할당된 경우 호출되는 할당 함수에 따라 맞춤이 결정됩니다.  예를 들어, `malloc`를 사용할 경우 피연산자 크기에 따라 결과가 결정됩니다. 하는 경우 *arg* > = 8 이면 반환 되는 메모리는 8 바이트에 맞춰집니다. 하는 경우 *arg* < 8, 반환 되는 메모리의 맞춤은 2의 첫 번째 거듭제곱이 미만 *arg*합니다. 예를 들어 malloc(7)를 사용하는 경우의 맞춤은 4바이트입니다.

## <a name="vclrf_declspecaligntypedef"></a> __Declspec(align(#))를 사용 하 여 새 형식 정의

맞춤 특성을 사용하여 형식을 정의할 수 있습니다.

예를 들어 정의할 수 있습니다는 `struct` 맞춤을 사용 하 여 이러한 방식으로 값:

```cpp
struct aType {int a; int b;};
typedef __declspec(align(32)) struct aType bType;
```

이제 `aType` 하 고 `bType` 동일한 크기 (8 바이트)는 형식의 변수에 `bType` 32 바이트 맞춤 됩니다.

## <a name="vclrfthreadlocalstorageallocation"></a> 스레드 로컬 저장소에서 데이터 정렬

`__declspec(thread)` 특성으로 만들어 이미지의 TLS 섹션에 넣은 정적 TLS(스레드 로컬 스토리지)는 보통의 정적 데이터와 똑같은 맞춤으로 작동합니다. 운영 체제에서는 TLS 데이터를 만들기 위해 메모리에 TLS 섹션의 크기를 할당하고 TLS 섹션 맞춤 특성을 고려합니다.

다음 예제에서는 맞춰진 데이터를 스레드 로컬 스토리지에 배치하는 여러 가지 방법을 보여 줍니다.

```cpp
// put an aligned integer in TLS
__declspec(thread) __declspec(align(32)) int a;

// define an aligned structure and put a variable of the struct type
// into TLS
__declspec(thread) __declspec(align(32)) struct F1 { int a; int b; } a;

// create an aligned structure
struct CACHE_ALIGN S9 {
   int a;
   int b;
};
// put a variable of the structure type into TLS
__declspec(thread) struct S9 a;
```

## <a name="vclrfhowalignworkswithdatapacking"></a> 데이터 압축과 함께 작동을 정렬 하는 방법

합니다 `/Zp` 컴파일러 옵션 및 `pack` pragma는 구조체 및 공용 구조체 멤버에 대 한 데이터를 압축 하는 중입니다. 이 예제에서는 어떻게 `/Zp` 및 `__declspec(align(#))` 함께 사용:

```cpp
struct S {
   char a;
   short b;
   double c;
   CACHE_ALIGN double d;
   char e;
   double f;
};
```

다음 테이블에서는 여러 `/Zp`(또는 #pragma `pack`)에 속한 각 멤버의 오프셋을 나열하고 둘 사이의 상호 작용 방식을 보여 줍니다.

|변수|/Zp1|/Zp2|/Zp4|/Zp8|
|--------------|-----------|-----------|-----------|-----------|
|a|0|0|0|0|
|b|1|2|2|2|
|c|3|4|4|8|
|일|32|32|32|32|
|e|40|40|40|40|
|f|41|42|44|48|
|sizeof(S)|64|64|64|64|

자세한 내용은 [/Zp(구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)를 참조하세요.

개체의 오프셋은 이전 개체의 오프셋과 현재 압축 설정을 기반으로 합니다. 단, 개체에 `__declspec(align(#))` 특성이 있는 경우 맞춤은 이전 개체의 오프셋과 개체의 `__declspec(align(#))` 값을 기반으로 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[ARM ABI 규칙 개요](../build/overview-of-arm-abi-conventions.md)<br/>
[x64 소프트웨어 규칙](../build/x64-software-conventions.md)