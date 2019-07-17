---
title: x64 호출 규칙
description: ABI 기본 x64 호출 규칙의 세부 정보입니다.
ms.date: 12/17/2018
ms.assetid: 41ca3554-b2e3-4868-9a84-f1b46e6e21d9
ms.openlocfilehash: 2cad00ac7f2cb5fe086fa262a0f512330997391f
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861158"
---
# <a name="x64-calling-convention"></a>x64 호출 규칙

이 섹션에서는 설명 하는 표준 프로세스 및 규칙 함수 (호출자) x64의 다른 함수 (호출 수신자)를 호출 하는 코드입니다.

## <a name="calling-convention-defaults"></a>호출 규칙 기본값

응용 프로그램 이진 인터페이스 ABI ()에서 4 등록 빠른 호출 규칙을 사용 하는 x64 기본입니다. 호출 스택의 해당 레지스터를 저장 하는 수신자에 대 한 섀도 저장소 공간 할당 됩니다. 함수 호출에 인수 및 해당 인수에 사용 되는 레지스터 간의 엄격한 일대일 대응 관계가 있습니다. 8 바이트에 맞지 않거나 1, 2, 4 또는 8 바이트 없는 모든 인수는 참조로 전달 되어야 합니다. 단일 인수를 여러 레지스터에 걸쳐 되지 않습니다. X87 레지스터 스택 사용 되지 및 호출 수신자를 사용할 수 있지만 고려해 야 volatile 함수 호출에서. 모든 부동 소수점 작업은 수행할 수는 16을 사용 하 여 XMM 등록 합니다. 정수 인수는 RCX, RDX, R8 및 R9 레지스터에 전달 됩니다. 부동 소수점 인수 XMM0L, XMM1L, XMM2L, 및 XMM3L 전달 됩니다. 16 바이트 인수는 참조로 전달 됩니다. 매개 변수 전달에 자세히 설명 되어 [매개 변수 전달](#parameter-passing)합니다. 이러한 등록 하는 것 외에도 RAX, R10, R11, XMM4, 및 XMM5 volatile 간주 됩니다. 다른 모든 레지스터 volatile이 아닌 경우 등록에 자세히 설명 되어 있습니다 [사용 등록](../build/x64-software-conventions.md#register-usage) 하 고 [호출자/호출 수신자 저장 레지스터](#callercallee-saved-registers)합니다.

프로토타입화된 함수의 경우 모든 인수는 전달되기 전에 필요한 호출 수신자 형식으로 변환됩니다. 호출자에 게, 호출 수신자에 게 매개 변수에 대 한 공간을 할당 하는 일을 담당 이며 4 개의 등록 매개 변수를 저장 하는 데 충분 한 공간이 호출 수신자는 여러 매개 변수를 사용 하지 않습니다 하는 경우에 항상 할당 해야 합니다. 이 규칙 vararg C 및 C 언어 프로토타입화 되지 않은 함수는 지원을 단순화 /C++ 함수입니다. Vararg 또는 프로토타입화 되지 않은 함수에 대 한 모든 부동 소수점 값을 반드시 해당 하는 범용 레지스터에 정확히 복제 되어야 합니다. 그림자를 호출 하기 전에 저장 한 후 처음 4 개 이상의 매개 변수를 스택에 저장 되어야 합니다. Vararg 함수 정보에서 확인할 수 있습니다 [Varargs](#varargs)합니다. 프로토타입화 되지 않은 함수 정보에 자세히 설명 되어 [프로토타입화 되지 않은 함수](#unprototyped-functions)합니다.

## <a name="alignment"></a>맞춤

대부분의 구조체는 해당 자연 맞춤으로 정렬 됩니다. 기본 예외는 스택 포인터와 `malloc` 또는 `alloca` 메모리 성능을 향상 시키기 위해 16 바이트에 맞춰집니다. 16 바이트를 초과 맞춤은 수동으로 수행 해야 하지만 대부분의 코드에 대 한이 값이 16 바이트 XMM 작업에 대 한 일반적인 맞춤 크기 이므로 작동 합니다. 구조 레이아웃 및 정렬 하는 방법에 대 한 자세한 내용은 참조 하세요. [형식 및 저장소](../build/x64-software-conventions.md#types-and-storage)합니다. 스택 레이아웃에 대 한 정보를 참조 하세요 [x64 스택 사용](../build/stack-usage.md)합니다.

## <a name="unwindability"></a>Unwindability

리프 함수는 모든 비휘발성 레지스터 변경 되지 않는 함수입니다. 비-리프 함수는 함수를 호출 하거나 로컬 변수에 대 한 추가 스택 공간을 할당 하 여 예를 들어 비휘발성 RSP 변경할 수 있습니다. 비휘발성 레지스터를 예외로 처리 될 때 복구 하기 위해 비-리프 함수 임의의 명령에 함수를 올바르게 해제 하는 방법을 설명 하는 정적 데이터를 사용 하 여 주석을 추가 해야 합니다. 이 데이터는으로 저장 *pdata*, 또는 프로시저 데이터를 다시 참조 하는 *xdata*, 예외 데이터를 처리 합니다. xdata 해제 정보를 포함 하 고 추가 pdata 또는 예외 처리기 함수를 가리킬 수 있습니다. 프롤로그와 에필로그는 xdata에 제대로 설명 될 수 있도록 고도로 제한 합니다. 스택 포인터에 속하지 않는 프롤로그 또는 에필로그를 제외한 리프 함수 내에서 코드의 모든 지역에서 16 바이트 정렬 되어야 합니다. 리프 함수 pdata 및 xdata가 필요 하므로 반환을 시뮬레이션 하면 위치 수 있습니다. 함수 프롤로그 및 에필로그의 올바른 구조에 대 한 자세한 내용은 참조 하세요 [x64 프롤로그 및 에필로그](../build/prolog-and-epilog.md)합니다. 예외 처리 및 예외 처리 및 pdata 및 xdata 해제 하는 방법에 대 한 자세한 내용은 참조 하십시오 [x64 예외 처리](../build/exception-handling-x64.md)합니다.

## <a name="parameter-passing"></a>매개 변수 전달

처음 4 개의 정수 인수 레지스터에 전달 됩니다. 정수 값 각각 RCX, RDX, R8 및 R9에 왼쪽에서 오른쪽 순서로 전달 됩니다. 인수 5 이상이 스택에 전달 됩니다. 모든 인수가 레지스터에 오른쪽 맞춤 호출 수신자는 레지스터의 상위 비트를 무시 하 고 필요한 레지스터의 부분에만 액세스할 수 있습니다.

처음 네 개의 매개 변수에서 부동 소수점 및 이중 정밀도 인수 위치에 따라 XMM0-XMM3에 전달 됩니다. RCX, RDX, R8 및 R9 해당 위치에 대 한 일반적으로 사용 되는 정수 레지스터 무시 되 varargs 인수 경우는 제외 합니다. 자세한 내용은 참조 하세요 [Varargs](#varargs)합니다. 마찬가지로,는 XMM0-XMM3 해당 인수는 정수 또는 포인터 형식 레지스터는 무시 됩니다.

[__m128](../cpp/m128.md) 형식, 배열 및 문자열 직접 값으로 전달 되지 않습니다. 대신, 호출자가 할당 된 메모리에 대 한 포인터 전달 됩니다. 구조체 및 공용 구조체 크기가 8, 16, 32 또는 64 비트 및 __m64 형식의 동일한 크기의 정수 처럼 전달 됩니다. 구조체 또는 공용 구조체 다른 크기의 호출자가 할당 된 메모리에 대 한 포인터로 전달 됩니다. 에 대 한 포인터로 전달 되는 이러한 집계 형식은 포함 하 여 \__m128을 호출자에 게 할당 된 임시 메모리 16 바이트 맞춤 이어야 합니다.

스택 공간을 할당 하지 않습니다 및 다른 함수를 호출 하지는 내장 함수는 종종 추가 레지스터 인수를 전달할 다른 휘발성 레지스터를 사용 합니다. 이 최적화 컴파일러 내장 함수 구현이 사이의 긴밀 한 바인딩에 의해 가능 합니다.

호출 수신자는 해당 섀도 공간이 필요한 경우에 등록 매개 변수를 덤프 하는 일을 담당 합니다.

다음 표에서 매개 변수를 전달 하는 방법을 보여 줍니다.

|매개 변수 유형|전달 하는 방법|
|--------------------|----------------|
|부동 소수점|처음 4 개의 매개 변수-XMM3 통해 XMM0입니다. 다른 스택에 전달 됩니다.|
|정수|처음 4 개의 매개 변수-RCX, RDX, R8 R9입니다. 다른 스택에 전달 됩니다.|
|집계 (8, 16, 32 또는 64 비트) 및 __m64|처음 4 개의 매개 변수-RCX, RDX, R8 R9입니다. 다른 스택에 전달 됩니다.|
|집계 (기타)|포인터입니다. RCX, RDX, R8 및 R9에 포인터로 전달 하는 처음 4 개의 매개 변수입니다.|
|__m128|포인터입니다. RCX, RDX, R8 및 R9에 포인터로 전달 하는 처음 4 개의 매개 변수입니다.|

### <a name="example-of-argument-passing-1---all-integers"></a>1-모든 정수를 전달 하는 인수의 예제

```cpp
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

### <a name="example-of-argument-passing-2---all-floats"></a>예제 2-모든 부동 소수점 수를 전달 하는 인수

```cpp
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

### <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>3-혼합된 정수 및 부동 소수점을 전달 하는 인수의 예제

```cpp
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

### <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>예 4를 전달 하는 인수의-__m64를 \__m128, 및 집계

```cpp
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="varargs"></a>Varargs

매개 변수 (예를 들어, 줄임표 인수) varargs 통해를 전달 하는 경우 다음 일반 등록 매개 변수가 전달 규칙 적용, 다섯 번째 및 이후의 인수는 스택에 분산이 포함 합니다. 이 값은 인수의 주소를 덤프 하 호출 수신자의 책임입니다. 부동 소수점 값을 정수 레지스터와 부동 소수점 레지스터 있어야 값, 호출 수신자에 게 정수 레지스터의 값이 필요한 경우.

## <a name="unprototyped-functions"></a>프로토타입화 되지 않은 함수

완전히 프로토타입화 되지 않은 함수의 경우 호출자에 게 정수 및 부동 소수점 값으로 정수 값 배정밀도로 전달합니다. 부동 소수점 값을 정수 레지스터와 부동 소수점 레지스터 값이 포함 호출 수신자에 게 정수 레지스터의 값이 필요한 경우.

```cpp
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="return-values"></a>반환 값

64 비트에 맞는 스칼라 반환 값은 RAX;를 통해 반환 됩니다. (__m64 형식 포함 합니다. Float, double 및 벡터 형식 등을 포함 하는 스칼라 이외의 형식은 [__m128](../cpp/m128.md)를 [__m128i](../cpp/m128i.md)하십시오 [__m128d](../cpp/m128d.md) XMM0에 반환 됩니다. RAX 또는 XMM0에 반환되는 값에서 사용되지 않는 비트의 상태는 정의되지 않습니다.

사용자 정의 형식은 전역 함수 및 정적 멤버 함수 값으로 반환될 수 있습니다. 사용자 정의 형식이 RAX에서 값을 반환 하려면 1, 2, 4, 8, 16, 32 또는 64 비트 길이의 있어야 합니다. 없는 사용자 정의 생성자, 소멸자 또는 복사 할당 연산자; 권한도 있어야 전용 또는 보호 된 비정적 데이터 멤버가 없습니다. 참조 형식의 비정적 데이터 멤버 없음 기본 클래스가 없고; 가상 함수가 없습니다. 및 이러한 요구도 충족 하지 않는 데이터 멤버가 없습니다. 이것은 기본적으로 C++03 POD 형식의 정의입니다. 사용 하 여 권장 하지 않습니다 정의 c++11 표준에서 변경 되었으므로 `std::is_pod` 이 테스트에 대 한 합니다.) 그렇지 않은 경우 호출자는 메모리를 할당하고 반환 값에 대한 포인터를 첫 번째 인수로 전달할 책임이 있다고 간주됩니다. 그런 다음 후속 인수가 오른쪽으로 하나씩 이동됩니다. RAX에서 호출 수신자에 의해 동일한 포인터가 반환되어야 합니다.

이러한 예에서는 지정된 선언을 사용하여 함수에 대해 매개 변수 및 반환 값이 전달되는 방식을 보여 줍니다.

### <a name="example-of-return-value-1---64-bit-result"></a>반환 값 1-64 비트 결과의 예

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

### <a name="example-of-return-value-2---128-bit-result"></a>반환 값 2-128 비트 결과의 예

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

### <a name="example-of-return-value-3---user-type-result-by-pointer"></a>반환 값 3 – 포인터 별 사용자 형식 결과의 예

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

### <a name="example-of-return-value-4---user-type-result-by-value"></a>반환 값 4-값별 사용자 형식 결과의 예

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="callercallee-saved-registers"></a>호출자/호출 수신자 저장 레지스터

함수 호출 시 레지스터 RAX, RCX, RDX, R8, R9, R10, R11, XMM0-5, 및 위 부분 YMM0 15 및 ZMM0 15 일시적인 것으로 간주 됩니다 및 고려해 야 제거 (하지 않는 한 안전성이 전체 프로그램 최적화와 같은 분석을 통해). AVX512VL, ZMM 고 YMM, XMM 레지스터 16-31은 일시적입니다.

레지스터 RBX, RBP, RDI, RSI, RSP, R12, R13, R14, r, 15 및 XMM6 15 일시적이 아닌 것으로 간주 됩니다 저장 해야 및 함수에서 복원 하는 사용 합니다.

## <a name="function-pointers"></a>함수 포인터
 
함수 포인터는 각 함수의 레이블에 대한 단순한 포인터입니다. 함수 포인터에 적용되는 TOC(목차) 요구 사항은 없습니다.

## <a name="floating-point-support-for-older-code"></a>이전 코드에 대 한 부동 소수점 지원

MMX와 부동 소수점 스택 레지스터(MM0-MM7/ST0-ST7)는 컨텍스트를 전환해도 유지됩니다. 이러한 레지스터에 대한 명시적인 호출 규칙은 없습니다. 이러한 레지스터는 커널 모드 코드에서만 사용하도록 엄격하게 제한되어 있습니다.

## <a name="fpcsr"></a>FpCsr

등록 상태에는 또한 x87 FPU 제어 단어입니다. 호출 규칙 nonvolatile 되도록이 레지스터를 지정 합니다.

프로그램 실행을 x87 FPU 제어 단어 레지스터의 시작 부분에 다음 표준 값으로 설정 됩니다.

| 등록\[비트] | 설정 |
|-|-|
| FPCSR\[0:6] | 모든 1 (모든 예외 마스크)를 마스크 하는 예외 |
| FPCSR\[7] | 예약 됨-0 |
| FPCSR\[8:9] | 정밀도 제어-10B (전체 자릿수를 두 번) |
| FPCSR\[10:11] | 반올림 제어-0 (round를 가장 가까운) |
| FPCSR\[12] | 무한대 제어-0 (사용 되지 않음) |

FPCSR 내의 필드를 수정 하는 호출 수신자는 호출자에 게 반환 하기 전에 해당를 복원 해야 합니다. 또한이 이러한 필드 중 하나를 수정 하는 호출자가 해당 문자열을 계약에 의해 호출 수신자는 수정 된 값이 필요 하지 않으면 호출 수신자를 호출 하기 전에 다른 표준 값으로 복원 해야 합니다.

제어 플래그의 비-변동성에 대 한 규칙의 두 가지 예외는

1. 비휘발성 FpCsr를 수정 하려면 지정 된 함수의 문서화 목적은 함수 플래그 지정 합니다.

1. 이 밖에도 경우 이러한 규칙 위반에는 이러한 규칙 되지 위반, 예를 들어 전체 프로그램 분석을 통해 프로그램에서와 동일 하 게 동작 하는 프로그램에서 결과 수정 합니다.

## <a name="mxcsr"></a>MxCsr

등록 상태에 MxCsr도 포함 됩니다. Volatile 부분과 비휘발성 일부로이 레지스터를 분할 하는 호출 규칙입니다. 6 개의 상태 플래그 MXCSR의 휘발성 부분 구성\[0:5], MXCSR 레지스터를 나머지 동안\[6시 15분], 일시적이 아닌 것으로 간주 됩니다.

비휘발성 부분에는 프로그램 실행의 시작 부분에 다음과 같은 표준 값으로 설정 됩니다.

| 등록\[비트] | 설정 |
|-|-|
| MXCSR\[6] | Denormals 있는 0-0 |
| MXCSR\[7:12] | 모든 1 (모든 예외 마스크)를 마스크 하는 예외 |
| MXCSR\[13:14] | 반올림 제어-0 (round를 가장 가까운) |
| MXCSR\[15] | 마스킹된 언더플로-0 (해제) 0으로 플러시 |

MXCSR 내에서 비 volatile 필드를 수정 하는 호출 수신자는 호출자에 게 반환 하기 전에 해당를 복원 해야 합니다. 또한이 이러한 필드 중 하나를 수정 하는 호출자가 해당 문자열을 계약에 의해 호출 수신자는 수정 된 값이 필요 하지 않으면 호출 수신자를 호출 하기 전에 다른 표준 값으로 복원 해야 합니다.

제어 플래그의 비-변동성에 대 한 규칙의 두 가지 예외는

- 비휘발성 MxCsr를 수정 하려면 지정 된 함수의 문서화 목적은 함수 플래그 지정 합니다.

- 이 밖에도 경우 이러한 규칙 위반에는 이러한 규칙 되지 위반, 예를 들어 전체 프로그램 분석을 통해 프로그램에서와 동일 하 게 동작 하는 프로그램에서 결과 수정 합니다.

특히 함수의 설명서에 설명 된 경우가 아니면 함수 경계를 넘어 volatile 부분의 MXCSR 상태에 대 한 어떠한가 정도 하지를 만들 수 있습니다.

## <a name="setjmplongjmp"></a>setjmp/longjmp

Setjmp.h 나 setjmpex.h를 포함 하는 경우 대 한 모든 호출은 [setjmp](../c-runtime-library/reference/setjmp.md) 하거나 [longjmp](../c-runtime-library/reference/longjmp.md) 소멸자를 호출 하는 해제 될 및 `__finally` 호출 합니다.  X86, 포함 하 여 setjmp.h 결과 위치에서이 반해 `__finally` 절 및 소멸자가 호출 되지 않습니다.

`setjmp`에 대한 호출은 현재 스택 포인터, 비휘발성 레지스터 및 MxCsr 레지스터를 유지합니다.  `longjmp`에 대한 호출은 가장 최근의 `setjmp` 호출 사이트에 반환되고 스택 포인터, 비휘발성 레지스터 및 MxCsr 레지스터를 가장 최근의 `setjmp` 호출에서 유지한 상태로 다시 설정합니다.

## <a name="see-also"></a>참고자료

[x64 소프트웨어 규칙](../build/x64-software-conventions.md)
