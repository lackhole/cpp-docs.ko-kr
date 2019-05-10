---
title: __alignof 연산자
ms.date: 12/17/2018
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 96c85db83c133af6f1712baa8597ed3360277854
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258254"
---
# <a name="alignof-operator"></a>__alignof 연산자

C + + 11 소개 합니다 **alignof** 바이트 단위로 지정 된 형식의 맞춤을 반환 하는 연산자입니다. 최대 이식성을 제공하려면 Microsoft 전용 __alignof 연산자가 아닌 alignof 연산자를 사용해야 합니다.

**Microsoft 전용**

형식의 값을 반환 `size_t` 형식의 맞춤 요구 사항인 합니다.

## <a name="syntax"></a>구문

```cpp
  __alignof( type )
```

## <a name="remarks"></a>설명

예를 들어:

|식|값|
|----------------|-----------|
|**__alignof( char )**|1|
|**__alignof( short )**|2|
|**__alignof( int )**|4|
|**__alignof( \__int64 )**|8|
|**__alignof( float )**|4|
|**__alignof( double )**|8|
|**__alignof( char\* )**|4|

합니다 **__alignof** 값에 대 한 값으로 동일 `sizeof` 기본 형식에 대 한 합니다. 그러나 다음과 같은 예제를 고려해야 합니다.

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

이 경우에 **__alignof** 값은 구조에서 가장 큰 요소의 맞춤 요구 합니다.

마찬가지로

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)`가 `32`와 같은 경우

에 대 한 한 가지 용도 **__alignof** 고유한 메모리 할당 루틴 중 하나를 매개 변수로 것입니다. 예를 들어, 다음의 정의된 구조인 `S`가 지정된 경우 `aligned_malloc`이라는 메모리 할당 루틴을 호출하여 특정한 할당 경계에서 메모리를 할당할 수 있습니다.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

이전 버전과 호환성에 대 한 **_alignof** 에 대 한 동의어가 **__alignof** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 는 지정 합니다.

맞춤 수정에 대한 자세한 내용은 다음을 참조하세요.

- [pack](../preprocessor/pack.md)

- [align(C++)](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp(구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)

- [구조체 맞춤 예제](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 전용)

X86 및 x64 관련 코드에서 맞춤의 차이점에 대한 자세한 내용은 다음을 참조하세요.

- [x86 컴파일러와 충돌](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)