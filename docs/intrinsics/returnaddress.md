---
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: 2a830ff1e8a2c9551dec52cf10a3d5cf126bde3b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218051"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Microsoft 전용**

`_ReturnAddress` 내장 함수는 컨트롤이 호출자에 게 반환 된 후 실행 되는 호출 함수에 있는 명령의 주소를 제공 합니다.

다음 프로그램을 빌드하고 디버거에서 단계별로 실행 합니다. 프로그램을 단계별로 실행 하는 동안에서 `_ReturnAddress`반환 된 주소를 확인 합니다. 그런 다음를 사용 `_ReturnAddress` [하는 함수에서 반환 된 직후에는 방법: 디스어셈블리 창을](/visualstudio/debugger/how-to-use-the-disassembly-window) 사용 하 여 실행할 다음 명령의 주소가에서 `_ReturnAddress`반환 된 주소와 일치 하는지 확인 합니다.

인라인 등의 최적화는 반환 주소에 영향을 줄 수 있습니다. 예를 들어 아래 샘플 프로그램이 [/ost1](../build/reference/ob-inline-function-expansion.md) `inline_func` 로 컴파일된 경우는 호출 함수 `main`에 인라인 됩니다. 따라서 및 `_ReturnAddress` 에서`main` 를 호출 하면 각각 동일한 값이 생성 됩니다. `inline_func`

[/Clr](../build/reference/clr-common-language-runtime-compilation.md) 을 사용하여 컴파일된 프로그램에서 `_ReturnAddress`을 사용하는 경우 호출 `_ReturnAddress`을 포함하는 함수가 네이티브 함수로 컴파일됩니다. 관리 되는 함수로 컴파일된 함수가를 포함 하 `_ReturnAddress`는 함수를 호출 하면가 `_ReturnAddress` 예상 대로 작동 하지 않을 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더 파일** \<intrin.h >

## <a name="example"></a>예제

```cpp
// compiler_intrinsics__ReturnAddress.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_ReturnAddress)

__declspec(noinline)
void noinline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

__forceinline
void inline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

int main(void)
{
   noinline_func();
   inline_func();
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());

   return 0;
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)\
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[C++ 키워드](../cpp/keywords-cpp.md)
