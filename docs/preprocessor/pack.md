---
title: pack
ms.date: 12/17/2018
f1_keywords:
- pack_CPP
- vc-pragma.pack
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
ms.openlocfilehash: bf1ae81184d53dd271f63c26e8f9a52a6410b232
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038449"
---
# <a name="pack"></a>pack
구조체, 공용 구조체 및 클래스 멤버에 대한 압축 맞춤을 지정합니다.

## <a name="syntax"></a>구문

```
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )
```

### <a name="parameters"></a>매개 변수

**Show**<br/>
(선택 사항) 압축 맞춤에 대 한 현재 바이트 값을 표시 합니다. 경고 메시지에 값이 표시됩니다.

**push**<br/>
(선택 사항) 현재 압축 맞춤 값 집합에 내부 컴파일러 스택으로 푸시 현재 압축 맞춤 값 *n*합니다. 하는 경우 *n* 지정 하지 않으면 현재 압축 맞춤 값이 푸시됩니다.

**pop**<br/>
(선택 사항) 내부 컴파일러 스택의 맨 위에서 레코드를 제거합니다. 하는 경우 *n* 을 지정 하지 않으면 **pop**, 스택의 맨 위에 결과 레코드와 연결 된 압축 값은 새로운 압축 맞춤 값입니다. 하는 경우 *n* 를 지정 하면 예를 들어 `#pragma pack(pop, 16)`를 *n* 은 새로운 압축 맞춤 값입니다. 팝 하는 경우 *식별자*, 예를 들어 `#pragma pack(pop, r1)`, 포함 된 레코드를 때까지 스택의 모든 레코드가 팝 되 고 그런 다음 *식별자* 를 찾을 수 있습니다. 해당 레코드가 팝되고 스택 맨 위에 있는 결과 레코드와 연결된 압축 값이 새로운 압축 맞춤 값이 됩니다. 팝 하는 경우는 *식별자* 스택의 모든 레코드에 없는 경우 **pop** 무시 됩니다.

*식별자*<br/>
(선택 사항) 와 함께 사용할 때 *푸시*, 내부 컴파일러 스택의 레코드에 이름을 할당 합니다. 와 함께 사용할 때 **pop**, 될 때까지 내부 스택에서 기록을 팝 *식별자* 가 제거 *식별자* 없는 내부 스택에서 아무 것도 팝 합니다.

*n*<br/>
(선택 사항) 압축에 사용 되는 바이트 값을 지정 합니다. 하는 경우 컴파일러 옵션 [/Zp](../build/reference/zp-struct-member-alignment.md) 모듈에 대 한 기본값 설정 되지 않습니다 *n* 8입니다. 유효한 값은 1, 2, 4, 8 및 16입니다. 멤버의 맞춤 됩니다 되었거나 경계에서의 배수 *n* 또는 멤버의 크기의 배수 중 더 작은 값입니다.

`#pragma pack(pop, identifier, n)` 정의 되지 않습니다.

## <a name="remarks"></a>설명

클래스를 압축하는 것은 해당 멤버를 메모리에서 서로 바로 뒤에 두는 것입니다. 이는 일부 또는 모든 멤버가 대상 아키텍처의 기본 맞춤보다 작은 경계에 정렬될 수 있음을 의미할 수 있습니다. **팩** 데이터 선언 수준에서 제어할 수 있습니다. 컴파일러 옵션에서이 반해 [/Zp](../build/reference/zp-struct-member-alignment.md)에 제공 하는 모듈 수준 제어 합니다. **팩** 첫 번째에 적용 됩니다 **구조체**를 **union**, 또는 **클래스** 선언 후, pragma가 표시 합니다. **팩** 정의에 영향이 없습니다. 호출 **pack** 없습니다 인수 집합을 사용 하 여 *n* 컴파일러 옵션에 설정 된 값을 `/Zp`입니다. 컴파일러 옵션이 설정되지 않은 경우 기본값은 8입니다.

구조체의 맞춤을 변경하는 경우 메모리에서 그만큼의 공간을 사용하지 않을 수 있지만, 성능이 저하되거나 정렬되지 않은 액세스에 대해 하드웨어에서 생성된 예외가 발생할 수도 있습니다.  사용 하 여이 예외 동작을 수정할 수 있습니다 [SetErrorMode](https://msdn.microsoft.com/library/windows/desktop/ms680621)합니다.

맞춤을 수정하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.

- [__alignof](../cpp/alignof-operator.md)

- [맞춤](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [구조체 맞춤 예제](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 전용)

   > [!WARNING]
   > Visual Studio 2015 이상에서는 `__alignof` 및 `declspec( align )`와 달리 컴파일러 간에 이식 가능한 표준 alignas 및 alignof 연산자를 사용할 수 있습니다. C + + 표준에서는 압축을 처리 하지을 반드시 사용 해야 하므로 **팩** (또는 다른 컴파일러에서 해당 확장 프로그램)는 대상 아키텍처의 단어 크기 보다 작은 맞춤을 지정 합니다.

## <a name="examples"></a>예제

다음 샘플에서는 사용 하는 **팩** pragma를 구조체의 맞춤을 변경 합니다.

```cpp
// pragma_directives_pack.cpp
#include <stddef.h>
#include <stdio.h>

struct S {
   int i;   // size 4
   short j;   // size 2
   double k;   // size 8
};

#pragma pack(2)
struct T {
   int i;
   short j;
   double k;
};

int main() {
   printf("%zu ", offsetof(S, i));
   printf("%zu ", offsetof(S, j));
   printf("%zu\n", offsetof(S, k));

   printf("%zu ", offsetof(T, i));
   printf("%zu ", offsetof(T, j));
   printf("%zu\n", offsetof(T, k));
}
```

```Output
0 4 8
0 4 6
```

다음 샘플에서는 사용 하는 *푸시*, *pop*, 및 *표시* 구문.

```cpp
// pragma_directives_pack_2.cpp
// compile with: /W1 /c
#pragma pack()   // n defaults to 8; equivalent to /Zp8
#pragma pack(show)   // C4810
#pragma pack(4)   // n = 4
#pragma pack(show)   // C4810
#pragma pack(push, r1, 16)   // n = 16, pushed to stack
#pragma pack(show)   // C4810
#pragma pack(pop, r1, 2)   // n = 2 , stack popped
#pragma pack(show)   // C4810
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)