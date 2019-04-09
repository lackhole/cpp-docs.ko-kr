---
title: _ReturnAddress
ms.date: 11/04/2016
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: e5013b20f9e7ed0349d940d9be61cc1b4afc95d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041139"
---
# <a name="returnaddress"></a>_ReturnAddress

## <a name="microsoft-specific"></a>Microsoft 전용

`_ReturnAddress` 내장 컨트롤 호출자에 게 반환 된 후 실행 되는 함수 호출에서 명령의 주소를 제공 합니다.

다음 프로그램 및 디버거에서 단계별로 진행을 빌드하십시오. 프로그램을 단계별로 확인에서 반환 되는 주소 `_ReturnAddress`합니다. 함수에서 반환 된 후 즉시 다음 여기서 `_ReturnAddress` 사용 되는, 열기를 [방법: 디스어셈블리 창 사용](/visualstudio/debugger/how-to-use-the-disassembly-window) 실행할 다음 명령의 주소에서 반환 하는 주소와 일치 하는지 확인 하 고 `_ReturnAddress`입니다.

인라인 월 같은 최적화 반송 주소에 영향을 줍니다. 예를 들어 아래 샘플 프로그램을 사용 하 여 컴파일된 [/Ob1](../build/reference/ob-inline-function-expansion.md)를 `inline_func` 호출 하는 함수를 인라인 처리 되지 `main`합니다. 따라서 호출 `_ReturnAddress` 에서 `inline_func` 고 `main` 동일한 값이 각 생성 됩니다.

때 `_ReturnAddress` 로 컴파일된 프로그램에서 사용 됩니다 [/clr](../build/reference/clr-common-language-runtime-compilation.md)를 포함 하는 함수는 `_ReturnAddress` 네이티브 함수로 호출 컴파일됩니다. 포함 하는 함수에 대 한 호출은 관리 되는 함수를 컴파일할 때 `_ReturnAddress`, `_ReturnAddress` 예상 대로 작동 하지 않을 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더 파일** \<intrin.h >

## <a name="example"></a>예제

```
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

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[키워드](../cpp/keywords-cpp.md)