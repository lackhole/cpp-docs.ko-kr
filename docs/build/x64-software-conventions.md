---
title: x64 소프트웨어 규칙
ms.date: 12/17/2018
helpviewer_keywords:
- x64 coding conventions
- Visual C++, x64 calling conventions
ms.assetid: 750f3d97-1706-4840-b2fc-41a007329a08
ms.openlocfilehash: 11d29b6c31ccecfe5b9c51c2f9311213bd4a6732
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313857"
---
# <a name="x64-software-conventions"></a>x64 소프트웨어 규칙

이 섹션에서는 설명의 C++ 호출 규칙 x64, x86 64 비트 확장에 대 한 아키텍처입니다.

## <a name="overview-of-x64-calling-conventions"></a>X64 호출 규칙 개요

X86과 x64 간의 두 가지 중요 한 차이점은 64 비트 주소 지정 기능 및 범용 레지스터 16 64 비트의 단순 집합입니다. X64에서는 확장 된 등록 집합에 지정 된 [__fastcall](../cpp/fastcall.md) 호출 규칙 및 RISC 기반 예외 처리 모델입니다. `__fastcall` 규칙 처음 네 개의 인수 및 스택 프레임에 대 한 레지스터를 사용 하 여 추가 인수를 전달 합니다. 호출 규칙, 등록 사용을 비롯 한 x64에 대 한 내용은 stack 매개 변수, 반환 값 및 스택 해제를 참조 하세요 [x64 호출 규칙](x64-calling-convention.md)합니다.

## <a name="enable-optimization-for-x64"></a>X64 최적화를 사용 하도록 설정

다음 컴파일러 옵션을 사용하면 응용 프로그램을 x64에 대해 최적화할 수 있습니다.

- [/favor(아키텍처에 맞게 최적화)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="types-and-storage"></a>형식 및 저장소

이 단원에서는 x64 아키텍처에 대한 데이터 형식의 저장소와 열거형을 설명합니다.

### <a name="scalar-types"></a>스칼라 형식

모든 맞춤을 사용 하 여 데이터에 액세스 하려면 가능한 경우에 성능 손실을 방지 하기 위해 일부 여러는 자연 경계에 데이터를 맞추는 것이 좋습니다에. 열거형 상수 정수 되며 32 비트 정수로 처리 됩니다. 다음 표에서 다음 맞춤 값을 사용 하는 맞춤 관련이 있으므로 형식 정 및 데이터에 대 한 권장 되는 저장소를 설명 합니다.

- 바이트-8 비트

- Word-16 비트

- 워드-32 비트

- 쿼드 워드-64 비트

- Octaword-128 비트

|||||
|-|-|-|-|
|스칼라 형식|C 데이터 형식|저장소 크기 (바이트)|권장 되는 맞춤|
|**INT8**|**char**|1|Byte|
|**UINT8**|**unsigned char**|1|Byte|
|**INT16**|**short**|2|단어|
|**UINT16**|**unsigned short**|2|단어|
|**INT32**|**int**, **long**|4|워드|
|**UINT32**|**부호 없는 int, 부호 없는 long**|4|워드|
|**INT64**|**__int64**|8|쿼드 워드|
|**UINT64**|**unsigned __int64**|8|쿼드 워드|
|**FP32 (단일 전체 자릿수)**|**float**|4|워드|
|**FP64 (전체 자릿수를 두 번)**|**double**|8|쿼드 워드|
|**포인터**|__\*__|8|쿼드 워드|
|**__m64**|**struct __m64**|8|쿼드 워드|
|**__m128**|**struct __m128**|16|Octaword|

### <a name="aggregates-and-unions"></a>집계 및 공용 구조체

배열, 구조체 및 공용 구조체와 같은 다른 형식에는 일관성 있는 집계 및 공용 구조체 저장소 및 데이터 검색을 보장 하는 보다 엄격한 맞춤 요구 사항이 있습니다. 배열, 구조체 및 공용 구조체에 대 한 정의 다음과 같습니다.

- 배열

   인접 한 데이터 개체의 정렬된 된 그룹을 포함합니다. 각 개체는 *요소*합니다. 모든 요소 배열 크기 및 데이터 형식이 동일한 경우

- 구조체

   데이터 개체의 정렬된 된 그룹을 포함합니다. 배열의 요소와 달리 구조체 내의 데이터 개체는 다른 데이터 형식 및 크기를 가질 수 있습니다. 구조의 각 데이터 개체를 *멤버*합니다.

- Union

   명명 된 멤버 집합 중 하나를 포함 하는 개체입니다. 명명된 된 집합의 멤버는 모든 형식일 수 있습니다. 공용 구조체에 할당 된 저장소는 공용 구조체 맞춤에 필요한 안쪽 여백을의 가장 큰 멤버에 필요한 저장소와 동일 합니다.

다음 표에서 강력 하 게 제안 된 스칼라 구조체와 공용 구조체 멤버 맞춤을 보여 줍니다.

||||
|-|-|-|
|스칼라 형식|C 데이터 형식|필요한 맞춤|
|**INT8**|**char**|Byte|
|**UINT8**|**unsigned char**|Byte|
|**INT16**|**short**|단어|
|**UINT16**|**unsigned short**|단어|
|**INT32**|**int**, **long**|워드|
|**UINT32**|**부호 없는 int, 부호 없는 long**|워드|
|**INT64**|**__int64**|쿼드 워드|
|**UINT64**|**unsigned __int64**|쿼드 워드|
|**FP32 (단일 전체 자릿수)**|**float**|워드|
|**FP64 (전체 자릿수를 두 번)**|**double**|쿼드 워드|
|**포인터**|<strong>\*</strong>|쿼드 워드|
|**__m64**|**struct __m64**|쿼드 워드|
|**__m128**|**struct __m128**|Octaword|

다음 집계 맞춤 규칙이 적용 됩니다.

- 맞춤 배열의 배열 요소 중 하나의 맞춤와 같습니다.

- 시작 하는 구조체 또는 공용 구조체의 맞춤은 개별 멤버의 최대 맞춤. 구조체 또는 공용 구조체 내에서 각 멤버는 이전 멤버에 따라 암시적 내부 채우기 필요할 수 있는 이전 테이블에 정의 된 대로 적절 한 맞춤에 배치 되어야 합니다.

- 구조체의 크기가 후 마지막 멤버는 해당 맞춤의 배수가 이어야 합니다. 구조체 및 공용 구조체 배열에 그룹화 할 수 있습니다, 되므로 구조체 또는 공용 구조체의 각 배열 요소 시작 하 고 이전에 결정 하는 적절 한 맞춤에 종료 해야 합니다.

- 보다 커야 맞춤 요구 사항으로 위의 규칙을 준수 하는 방식에 대 한 데이터를 정렬 하는 것이 가능 합니다.

- 개별 컴파일러 크기 이유로 구조체의 압축을 조정할 수 있습니다. 예를 들어 [/Zp (구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md) 구조체의 압축을 조정할 수 있습니다.

### <a name="examples-of-structure-alignment"></a>구조체 맞춤 예제

다음 네 개의 예제에서는 각각 정렬된 구조체 또는 공용 구조체를 선언하고 관련된 그림에서는 메모리에 있는 해당 구조체 또는 공용 구조체의 레이아웃을 보여 줍니다. 그림의 각 열은 메모리의 바이트를 나타내고 열의 숫자는 해당 바이트의 치환을 나타냅니다. 각 그림의 두 번째 행에 있는 이름은 선언에 있는 변수의 이름에 해당합니다. 회색으로 표시된 열은 지정된 맞춤을 달성하기 위해 필요한 여백입니다.

#### <a name="example-1"></a>예제 1

```C
// Total size = 2 bytes, alignment = 2 bytes (word).

_declspec(align(2)) struct {
    short a;      // +0; size = 2 bytes
}
```

![AMD 변환 예제 1 구조체 레이아웃이](../build/media/vcamd_conv_ex_1_block.png "AMD 변환 예제 1 구조 레이아웃")

#### <a name="example-2"></a>예제 2

```C
// Total size = 24 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) struct {
    int a;       // +0; size = 4 bytes
    double b;    // +8; size = 8 bytes
    short c;     // +16; size = 2 bytes
}
```

![AMD 변환 예제 2 구조체 레이아웃이](../build/media/vcamd_conv_ex_2_block.png "AMD 변환 예제 2 구조 레이아웃")

#### <a name="example-3"></a>예제 3

```C
// Total size = 12 bytes, alignment = 4 bytes (doubleword).

_declspec(align(4)) struct {
    char a;       // +0; size = 1 byte
    short b;      // +2; size = 2 bytes
    char c;       // +4; size = 1 byte
    int d;        // +8; size = 4 bytes
}
```

![AMD 변환 예제 2 구조체 레이아웃이](../build/media/vcamd_conv_ex_3_block.png "AMD 변환 예제 2 구조 레이아웃")

#### <a name="example-4"></a>예제 4

```C
// Total size = 8 bytes, alignment = 8 bytes (quadword).

_declspec(align(8)) union {
    char *p;      // +0; size = 8 bytes
    short s;      // +0; size = 2 bytes
    long l;       // +0; size = 4 bytes
}
```

![AMD 변환 예제 4에 대 한 공용 구조체 layouit](../build/media/vcamd_conv_ex_4_block.png "AMD 변환 예제 4에 대 한 공용 구조체 layouit")

### <a name="bitfields"></a>비트 필드

구조 비트 필드는 64 비트 제한 되 고 형식이 될 수 있습니다, 부호 없는 int, int64, 정수나 부호 없는 int64를 서명 합니다. 형식 경계를 교차 하는 비트 필드는 다음 형식 맞춤을 비트 필드에 맞게 비트를 건너뜁니다. 예를 들어 정수 넘어설 수 없습니다는 32 비트 경계입니다.

### <a name="conflicts-with-the-x86-compiler"></a>충돌 x86 컴파일러

4바이트보다 큰 데이터 형식은 x86 컴파일러를 사용하여 응용 프로그램을 컴파일할 때 자동으로 스택에 정렬되지 않습니다. x86 컴파일러의 아키텍처는 4바이트 정렬된 스택이기 때문에 4바이트보다 큰 정수(예: 64비트 정수)는 8바이트 주소에 자동으로 정렬할 수 없습니다.

정렬되지 않은 데이터로 작업하는 데는 두 가지 의미가 있습니다.

- 정렬된 위치에 액세스하는 데 걸리는 시간보다 정렬되지 않은 위치에 액세스하는 데 시간이 오래 걸릴 수 있습니다.

- 정렬되지 않은 위치는 연동된 작업에 사용할 수 없습니다.

더 엄격한 맞춤이 필요한 경우 사용 하 여 `__declspec(align(N))` 프로그램 변수 선언 합니다. 이렇게 하면 컴파일러가 사양에 맞게 스택을 동적으로 정렬하게 됩니다. 그러나 스택을 런타임에 동적으로 조정하면 응용 프로그램의 실행 속도가 느려질 수 있습니다.

## <a name="register-usage"></a>레지스터 사용

부동 소수점에 사용 가능한 16 XMM/YMM 뿐만 아니라 16 범용 레지스터 (이 하 정수 레지스터)에 대 한 아키텍처를 제공 하는 x64를 등록 합니다. 휘발성 레지스터는 호출자가 호출 중에 제거되는 것으로 가정하는 스크래치 레지스터입니다. 함수 호출 중에 값을 유지하려면 비휘발성 레지스터가 필요합니다. 호출 수신자는 비휘발성 레지스터(사용하는 경우)를 저장해야 합니다.

### <a name="register-volatility-and-preservation"></a>등록 변동성 및 보존

다음 테이블에서는 함수 호출에서 각 레지스터가 사용되는 방법을 설명합니다.

||||
|-|-|-|
|레지스터|상태|사용|
|RAX|휘발성|반환 값 레지스터|
|RCX|휘발성|첫 번째 정수 인수|
|RDX|휘발성|두 번째 정수 인수|
|R8|휘발성|세 번째 정수 인수|
|R9|휘발성|네 번째 정수 인수|
|R10:R11|휘발성|호출자가 필요에 따라 보존해야 하며 syscall/sysret 명령에 사용됨|
|R12:R15|비휘발성|호출 수신자가 보존해야 함|
|RDI|비휘발성|호출 수신자가 보존해야 함|
|RSI|비휘발성|호출 수신자가 보존해야 함|
|RBX|비휘발성|호출 수신자가 보존해야 함|
|RBP|비휘발성|프레임 포인터로 사용 가능(호출 수신자가 보존해야 함)|
|RSP|비휘발성|스택 포인터|
|XMM0, YMM0|휘발성|첫 번째 FP 인수(`__vectorcall` 사용 시에는 첫 번째 벡터 형식 인수)|
|XMM1, YMM1|휘발성|두 번째 FP 인수(`__vectorcall` 사용 시에는 두 번째 벡터 형식 인수)|
|XMM2, YMM2|휘발성|세 번째 FP 인수(`__vectorcall` 사용 시에는 세 번째 벡터 형식 인수)|
|XMM3, YMM3|휘발성|네 번째 FP 인수(`__vectorcall` 사용 시에는 네 번째 벡터 형식 인수)|
|XMM4, YMM4|휘발성|호출자가 필요에 따라 보존해야 함(`__vectorcall` 사용 시에는 다섯 번째 벡터 형식 인수)|
|XMM5, YMM5|휘발성|호출자가 필요에 따라 보존해야 함(`__vectorcall` 사용 시에는 여섯 번째 벡터 형식 인수)|
|XMM6:XMM15, YMM6:YMM15|비휘발성(XMM), 휘발성(YMM의 위쪽 절반)|호출 수신자가 유지 되어야 합니다. YMM 레지스터는 호출자가 필요에 따라 보존해야 함|

함수 종료 시 및 C 런타임 라이브러리 호출 및 Windows 시스템 호출 함수 항목에는 CPU에서 방향 플래그 플래그 레지스터는 지울 수 해야 합니다.

## <a name="stack-usage"></a>스택 사용

스택 할당, 맞춤, 함수 형식 및 x64에서 스택 프레임에 대 한 내용은 참조 하세요 [x64 스택 사용](stack-usage.md)합니다.

## <a name="prolog-and-epilog"></a>프롤로그 및 에필로그

스택 공간을 할당, 다른 함수를 호출, 비휘발성 레지스터를 저장 또는 예외 처리를 사용 하는 모든 함수에는 해당 주소 제한에는 에필로그 고 각 함수의 테이블 항목을 사용 하 여 연결 된 해제 데이터에 설명 된 프롤로그가 있어야 합니다. 함수에 각 종료 합니다. 필요한 프롤로그에 대 한 세부 정보 및 에필로그 코드 x64 [x64 프롤로그 및 에필로그](prolog-and-epilog.md)합니다.

## <a name="x64-exception-handling"></a>x64 예외 처리

구조적된 예외 처리를 구현 하는 데 사용 하는 규칙 및 데이터 구조에 대 한 내용은 및 C++ x64에서 예외 처리 동작을 참조 하세요 [x64 예외 처리](exception-handling-x64.md)합니다.

## <a name="intrinsics-and-inline-assembly"></a>내장 및 인라인 어셈블리

x64 컴파일러의 제약 조건 중 하나는 인라인 어셈블러를 지원하지 않는다는 것입니다. 즉, C 또는 C++로 작성할 수 없는 함수는 컴파일러에서 지원하는 내장 함수나 서브루틴으로 작성해야 합니다. 함수에 따라서는 성능에 큰 영향을 미칠 수도 있습니다. 성능에 중요한 부분을 차지하는 함수는 내장 함수로 구현해야 합니다.

컴파일러에서 지원하는 내장 함수에 대한 자세한 내용은 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)를 참조하십시오.

## <a name="image-format"></a>이미지 형식

X64 PE32 + 실행 가능 이미지 형식입니다. 실행 가능 이미지 (Dll과 Exe) 최대 크기가 2gb로 제한 되므로 정적 이미지 데이터를 사용할 수는 32 비트 치환을 사용 하 여 상대 주소를 지정 합니다. 이 데이터 가져오기 주소 테이블, 문자열 상수, 전역 정적 데이터 및 등을 포함합니다.

## <a name="see-also"></a>참고자료

[호출 규칙](../cpp/calling-conventions.md)
