---
title: __vectorcall
ms.date: 12/17/2018
f1_keywords:
- __vectorcall_cpp
- __vectorcall
- _vectorcall
helpviewer_keywords:
- __vectorcall keyword
- __vectorcall
ms.assetid: 1c95ed59-86c6-4857-b4ed-10519193f851
ms.openlocfilehash: 55c383c4bdf83ddb5fdf1c4990d5f2e47b4d819a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393885"
---
# <a name="vectorcall"></a>__vectorcall

**Microsoft 전용**

합니다 **__vectorcall** 호출 규칙 지정 함수에 대 한 인수를 가능 하면 레지스터로 전달 하도록 합니다. **__vectorcall** 인수에 대 한 자세한 레지스터를 사용 하 여 [__fastcall](../cpp/fastcall.md) 기본값을 가져오거나 [x64 호출 규칙](../build/x64-calling-convention.md) 사용 합니다. 합니다 **__vectorcall** 호출 규칙은 sse2(스트리밍 SIMD 확장 2 ()를 포함 하는 x86 및 x64 프로세서 이상 네이티브 코드에만 지원 됩니다. 사용 하 여 **__vectorcall** 레지스터에 로드 된 여러 부동 소수점을 전달 하는 함수 또는 SIMD 벡터 인수 속도 및 인수를 활용 하는 작업을 수행 합니다. 다음은 x86 및 x64 구현에 공통 되는 기능을 보여 줍니다 **__vectorcall**합니다. 차이점은 이 문서의 뒷부분에 설명되어 있습니다.

|요소|구현|
|-------------|--------------------|
|C 이름 데코레이션 규칙|함수 이름은 두 개의 "at" 기호 붙습니다 (\@\@) 뒤에 매개 변수 목록의 10 진수) (의 바이트 수입니다.|
|대/소문자 변환 규칙|대/소문자 변환은 수행되지 않습니다.|

사용 하는 [/Gv](../build/reference/gd-gr-gv-gz-calling-convention.md) 컴파일러 옵션을로 컴파일 모듈에서 각 함수 사용 하면 **__vectorcall** 함수 멤버 함수가 아닌 충돌 하는 호출 규칙 특성으로 선언에서는 `vararg` 가변 인수 목록 이름이 또는 `main`합니다.

에 등록 하 여 세 가지 인수를 전달할 수 있습니다 **__vectorcall** 함수: *정수 형식을* 값을 *벡터 형식* 값 및 *균질 벡터 집계* (HVA) 값입니다.

정수 형식은 프로세서의 네이티브 레지스터 크기에 적합하며(예: x86 컴퓨터에서는 4바이트 또는 x64 컴퓨터에서는 8바이트) 레지스터 길이의 정수로 변환한 후 비트 표현을 변경하지 않고 다시 변환하는 두 요구 사항을 충족합니다. 모든 형식으로 승격 될 수 있는 예를 들어 **int** x86 (**long long** x64)-예를 들어를 **char** 또는 **짧은**-으로 캐스팅 될 수 있는 또는 **int** (**long long** x64) 정수 형식이 변경 없이 원래 형식으로 다시 합니다. 포인터, 참조를 포함 하는 정수 형식 및 **구조체** 또는 **union** 유형의 4 바이트 (x64에서는 8 바이트) 이하의 합니다. X64 플랫폼에서 큰 **구조체** 하 고 **union** 형식은 x86; 호출자가 할당 된 메모리에 대 한 참조로 전달 플랫폼으로 전달 될 값 스택에 합니다.

벡터 형식은 부동 소수점 형식-예를 들어, 한 **float** 또는 **double**-또는 SIMD 벡터 형식-예를 들어 **__m128** 또는 **__m256**.

HVA 형식은 동일한 벡터 형식을 갖는 최대 4개의 데이터 멤버로 구성된 복합 형식입니다. HVA 형식은 멤버의 벡터 형식과 맞춤 요구 사항이 동일합니다. HVA 예가 이것이 **구조체** 세 가지 동일한 벡터 형식을 포함 하는 32 바이트 맞춤 정의:

```cpp
typedef struct {
   __m256 x;
   __m256 y;
   __m256 z;
} hva3;    // 3 element HVA type on __m256
```

명시적으로 사용 하 여 함수를 선언 합니다 **__vectorcall** 키워드 별도로 있도록 헤더 파일의 컴파일된 코드 오류 없이 링크를 합니다. 함수를 사용 하 여 있도록 프로토타입화 되어야 **__vectorcall**를 사용할 수 없습니다는 `vararg` 가변 길이 인수 목록입니다.

멤버 함수를 사용 하 여 선언할 수 있습니다 합니다 **__vectorcall** 지정자입니다. 숨겨진 **이** 포인터는 첫 번째 정수 형식 인수 레지스터에 의해 전달 됩니다.

ARM 컴퓨터에서 **__vectorcall** 수락 하 고 컴파일러에서 무시 합니다.

비정적 클래스 멤버 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다. 즉, 클래스 비정적 멤버의 경우 선언하는 동안 지정된 호출 규칙이 정의 시에 가정됩니다. 다음의 클래스 정의를 가정해 봅니다.

```cpp
struct MyClass {
   void __vectorcall mymethod();
};
```

다음 코드는

```cpp
void MyClass::mymethod() { return; }
```

다음 코드 조각과 일치합니다.

```cpp
void __vectorcall MyClass::mymethod() { return; }
```

합니다 **__vectorcall** 호출 규칙 한정자를 지정 해야 합니다는 경우에 대 한 포인터는 **__vectorcall** 함수가 만들어집니다. 다음 예제에서는 만듭니다는 **typedef** 에 대 한 포인터를 **__vectorcall** 4를 사용 하는 함수 **double** 인수 및 반환은 **__m256**값:

```cpp
typedef __m256 (__vectorcall * vcfnptr)(double, double, double, double);
```

이전 버전과 호환성에 대 한 **_vectorcall** 에 대 한 동의어가 **__vectorcall** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md)지정 됩니다.

## <a name="vectorcall-convention-on-x64"></a>x64의 __vectorcall 규칙

합니다 **__vectorcall** 표준 x64 호출 규칙 추가 레지스터를 활용 하기 위해 확장 x64 호출 규칙입니다. 정수 형식 인수와 벡터 형식 인수 모두 인수 목록에 있는 위치를 기반으로 레지스터에 매핑됩니다. HVA 인수는 사용되지 않는 벡터 레지스터에 할당됩니다.

왼쪽에서 오른쪽 순서로 처음 네 개의 인수가 정수 형식 인수인 경우 해당 위치 RCX, RDX, R8 또는 R9에 해당하는 레지스터에서 전달됩니다. 숨겨진 **이** 포인터는 첫 번째 정수 형식 인수로 처리 됩니다. 처음 네 개의 인수 중 하나에 있는 HVA 인수를 사용 가능한 레지스터에서 전달할 수 없을 경우, 그 대신 호출자가 할당한 메모리에 대한 참조를 해당 정수 형식 레지스터에서 전달합니다. 네 번째 매개 변수 위치 뒤에 오는 정수 형식 인수는 스택에서 전달됩니다.

왼쪽에서 오른쪽 순서로 처음 여섯 개의 인수가 벡터 형식 인수인 경우 인수 위치에 따라 0에서 5의 SSE 벡터 레지스터 값에 의해 전달됩니다. 부동 소수점 및 **__m128** 전달 된 형식이 XMM 레지스터에서 및 **__m256** 형식은 YMM에 전달 되므로 등록 합니다. 벡터 형식이 참조가 아닌 값에 의해 전달되고 추가 레지스터가 사용되므로 이는 표준 x64 호출 규칙과 다릅니다. 벡터 형식 인수에 할당 된 섀도 스택 공간은 8 바이트로 고정 되 고 [/homeparams](../build/reference/homeparams-copy-register-parameters-to-stack.md) 옵션이 적용 되지 않습니다. 일곱 번째 이후의 매개 변수 자리에 오는 벡터 형식 인수는 호출자가 할당한 메모리에 대한 참조에 의해 스택에서 전달됩니다.

사용 되지 않는 벡터 레지스터 XMM0 XMM5 오름차순으로 레지스터 벡터 인수에 할당 된 후 HVA 인수의 데이터 멤버를 할당 됩니다 (또는 YMM0에 YMM5에 대 한 **__m256** 형식)로 레지스터가 충분 전체 HVA에 사용할 수 있습니다. 사용할 수 있는 레지스터가 충분하지 않은 경우 HVA 인수는 호출자가 할당한 메모리에 대한 참조에 의해 전달됩니다. HVA 인수에 대한 스택 섀도 공간은 정의되지 않은 내용을 포함하여 8바이트로 고정됩니다. HVA 인수는 매개 변수 목록의 왼쪽에서 오른쪽 순서로 레지스터에 할당되며 어떤 위치에나 있을 수 있습니다. 벡터 레지스터에 할당되지 않은 처음 네 개의 인수 위치 중 하나에 있는 HVA 인수는 해당 위치에 대응하는 정수 레지스터에서 참조에 의해 전달됩니다. 네 번째 매개 변수 위치 뒤로 참조에 의해 전달된 HVA 인수는 스택에서 푸시됩니다.

결과 **__vectorcall** 함수는 가능 하면 레지스터로 값으로 반환 됩니다. 8바이트 이하의 정수 형식 구조체 또는 공용 구조체를 포함한 정수 형식의 결과는 RAX에 값으로 반환됩니다. 벡터 형식 결과는 크기에 따라 XMM0 또는 YMM0에 값으로 반환됩니다. HVA 결과에는 요소 크기에 따라 레지스터 XMM0:XMM3 또는 YMM0:YMM3에 값으로 반환되는 각 데이터 요소가 있습니다. 해당 레지스터에 맞지 않는 결과 형식은 호출자가 할당한 메모리에 대한 참조로 반환됩니다.

X64에서는 호출자가 스택을 유지 관리 됩니다 구현의 **__vectorcall**합니다. 호출자 프롤로그 및 에필로그 코드는 호출된 함수의 스택을 할당하고 호출합니다. 인수는 오른쪽에서 왼쪽으로 스택에서 푸시되며 섀도 스택 공간에는 레지스터에 의해 전달된 인수가 할당됩니다.

예를 들면 다음과 같습니다.

```cpp
// crt_vc64.c
// Build for amd64 with: cl /arch:AVX /W3 /FAs crt_vc64.c
// This example creates an annotated assembly listing in
// crt_vc64.asm.

#include <intrin.h>
#include <xmmintrin.h>

typedef struct {
   __m128 array[2];
} hva2;    // 2 element HVA type on __m128

typedef struct {
   __m256 array[4];
} hva4;    // 4 element HVA type on __m256

// Example 1: All vectors
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.
// Return value in XMM0.
__m128 __vectorcall
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {
   return d;
}

// Example 2: Mixed int, float and vector parameters
// Passes a in RCX, b in XMM1, c in R8, d in XMM3, e in YMM4,
// f in XMM5, g pushed on stack.
// Return value in YMM0.
__m256 __vectorcall
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {
   return e;
}

// Example 3: Mixed int and HVA parameters
// Passes a in RCX, c in R8, d in R9, and e pushed on stack.
// Passes b by element in [XMM0:XMM1];
// b's stack shadow area is 8-bytes of undefined value.
// Return value in XMM0.
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {
   return b.array[0];
}

// Example 4: Discontiguous HVA
// Passes a in RCX, b in XMM1, d in XMM3, and e is pushed on stack.
// Passes c by element in [YMM0,YMM2,YMM4,YMM5], discontiguous because
// vector arguments b and d were allocated first.
// Shadow area for c is an 8-byte undefined value.
// Return value in XMM0.
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {
   return b;
}

// Example 5: Multiple HVA arguments
// Passes a in RCX, c in R8, e pushed on stack.
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5], each with
// stack shadow areas of an 8-byte undefined value.
// Return value in RAX.
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {
   return c + e;
}

// Example 6: HVA argument passed by reference, returned by register
// Passes a in [XMM0:XMM1], b passed by reference in RDX, c in YMM2,
// d in [XMM3:XMM4].
// Register space was insufficient for b, but not for d.
// Return value in [YMM0:YMM3].
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {
   return b;
}

int __cdecl main( void )
{
   hva4 h4;
   hva2 h2;
   int i;
   float f;
   __m128 a, b, d;
   __m256 c, e;

   a = b = d = _mm_set1_ps(3.0f);
   c = e = _mm256_set1_ps(5.0f);
   h2.array[0] = _mm_set1_ps(6.0f);
   h4.array[0] = _mm256_set1_ps(7.0f);

   b = example1(a, b, c, d, e);
   e = example2(1, b, 3, d, e, 6.0f, 7);
   d = example3(1, h2, 3, 4, 5);
   f = example4(1, 2.0f, h4, d, 5);
   i = example5(1, h2, 3, h4, 5);
   h4 = example6(h2, h4, c, h2);
}
```

## <a name="vectorcall-convention-on-x86"></a>x86의 __vectorcall 규칙

합니다 **__vectorcall** 호출 규칙을 **__fastcall** 32 비트 정수 형식 인수와 벡터 형식 및 HVA 인수에 대 한 SSE 벡터 레지스터 활용에 대 한 규칙입니다.

매개 변수 목록에서 왼쪽에서 오른쪽 순서로 처음 두 개 정수 형식 인수는 각각 ECX 및 EDX에 배치됩니다. 숨겨진 **이** 포인터는 첫 번째 정수 형식 인수로 처리 되 고 ECX에서 전달 됩니다. 처음 여섯 개 벡터 형식 인수는 인수 크기에 따라 0에서 5의 SSE 벡터 레지스터 값에 의해 XMM 또는 YMM 레지스터에서 전달됩니다.

왼쪽에서 오른쪽 순서로 처음 여섯 개 벡터 형식 인수는 0에서 5의 SSE 벡터 레지스터 값에 의해 전달됩니다. 부동 소수점 및 **__m128** 전달 된 형식이 XMM 레지스터에서 및 **__m256** 형식은 YMM에 전달 되므로 등록 합니다. 레지스터에 의해 전달된 벡터 형식 인수에는 섀도 스택 공간이 할당되지 않습니다. 일곱 번째 이후의 벡터 형식 인수는 호출자가 할당한 메모리에 대한 참조에 의해 스택에서 전달됩니다. 컴파일러 오류에 대 한 제한 [C2719](../error-messages/compiler-errors-2/compiler-error-c2719.md) 이러한 인수에 적용 되지 않습니다.

HVA 인수는 멤버는 사용 되지 않는 벡터를 오름차순에 할당 된 데이터를 XMM5 XMM0 등록 레지스터 벡터 인수에 할당 된 후 (또는 YMM0에 YMM5에 대 한 **__m256** 형식)로 레지스터가 충분 전체 HVA에 사용할 수 있습니다. 사용할 수 있는 레지스터가 충분하지 않은 경우 HVA 인수는 호출자가 할당한 메모리에 대한 참조에 의해 스택에서 전달됩니다. HVA 인수에는 스택 섀도 공간이 할당되지 않습니다. HVA 인수는 매개 변수 목록의 왼쪽에서 오른쪽 순서로 레지스터에 할당되며 어떤 위치에나 있을 수 있습니다.

결과 **__vectorcall** 함수는 가능 하면 레지스터로 값으로 반환 됩니다. 4바이트 이하의 정수 형식 구조체 또는 공용 구조체를 포함한 정수 형식의 결과는 EAX에 값으로 반환됩니다. 8바이트 이하의 정수 형식 구조체 또는 공용 구조체는 EDX:EAX에 값으로 반환됩니다. 벡터 형식 결과는 크기에 따라 XMM0 또는 YMM0에 값으로 반환됩니다. HVA 결과에는 요소 크기에 따라 레지스터 XMM0:XMM3 또는 YMM0:YMM3에 값으로 반환되는 각 데이터 요소가 있습니다. 다른 결과 형식은 호출자가 할당한 메모리에 대한 참조로 반환됩니다.

X86 구현의 **__vectorcall** 다음과 같이 호출자에서 호출된 된 함수를 오른쪽에서 왼쪽으로 스택에 푸시한 인수 규칙 스택을 지워 반환 되기 전에 합니다. 레지스터에 배치되지 않은 인수만 스택으로 푸시됩니다.

예를 들면 다음과 같습니다.

```cpp
// crt_vc86.c
// Build for x86 with: cl /arch:AVX /W3 /FAs crt_vc86.c
// This example creates an annotated assembly listing in
// crt_vc86.asm.

#include <intrin.h>
#include <xmmintrin.h>

typedef struct {
   __m128 array[2];
} hva2;    // 2 element HVA type on __m128

typedef struct {
   __m256 array[4];
} hva4;    // 4 element HVA type on __m256

// Example 1: All vectors
// Passes a in XMM0, b in XMM1, c in YMM2, d in XMM3, e in YMM4.
// Return value in XMM0.
__m128 __vectorcall
example1(__m128 a, __m128 b, __m256 c, __m128 d, __m256 e) {
   return d;
}

// Example 2: Mixed int, float and vector parameters
// Passes a in ECX, b in XMM0, c in EDX, d in XMM1, e in YMM2,
// f in XMM3, g pushed on stack.
// Return value in YMM0.
__m256 __vectorcall
example2(int a, __m128 b, int c, __m128 d, __m256 e, float f, int g) {
   return e;
}

// Example 3: Mixed int and HVA parameters
// Passes a in ECX, c in EDX, d and e pushed on stack.
// Passes b by element in [XMM0:XMM1].
// Return value in XMM0.
__m128 __vectorcall example3(int a, hva2 b, int c, int d, int e) {
   return b.array[0];
}

// Example 4: HVA assigned after vector types
// Passes a in ECX, b in XMM0, d in XMM1, and e in EDX.
// Passes c by element in [YMM2:YMM5].
// Return value in XMM0.
float __vectorcall example4(int a, float b, hva4 c, __m128 d, int e) {
   return b;
}

// Example 5: Multiple HVA arguments
// Passes a in ECX, c in EDX, e pushed on stack.
// Passes b in [XMM0:XMM1], d in [YMM2:YMM5].
// Return value in EAX.
int __vectorcall example5(int a, hva2 b, int c, hva4 d, int e) {
   return c + e;
}

// Example 6: HVA argument passed by reference, returned by register
// Passes a in [XMM1:XMM2], b passed by reference in ECX, c in YMM0,
// d in [XMM3:XMM4].
// Register space was insufficient for b, but not for d.
// Return value in [YMM0:YMM3].
hva4 __vectorcall example6(hva2 a, hva4 b, __m256 c, hva2 d) {
   return b;
}

int __cdecl main( void )
{
   hva4 h4;
   hva2 h2;
   int i;
   float f;
   __m128 a, b, d;
   __m256 c, e;

   a = b = d = _mm_set1_ps(3.0f);
   c = e = _mm256_set1_ps(5.0f);
   h2.array[0] = _mm_set1_ps(6.0f);
   h4.array[0] = _mm256_set1_ps(7.0f);

   b = example1(a, b, c, d, e);
   e = example2(1, b, 3, d, e, 6.0f, 7);
   d = example3(1, h2, 3, 4, 5);
   f = example4(1, 2.0f, h4, d, 5);
   i = example5(1, h2, 3, h4, 5);
   h4 = example6(h2, h4, c, h2);
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)