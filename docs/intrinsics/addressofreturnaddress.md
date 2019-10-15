---
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: d705029c30fdbc117c4c6e96923691e43e072e23
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221069"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft 전용**

현재 함수의 반환 주소를 보유 하는 메모리 위치의 주소를 제공 합니다. 이 주소를 사용 하 여 다른 메모리 위치 (예: 함수의 인수)에 액세스할 수 없습니다.

## <a name="syntax"></a>구문

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64, ARM, ARM64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

[/Clr](../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일된 프로그램에서 `_AddressOfReturnAddress`을 사용하는 경우 호출 `_AddressOfReturnAddress`을 포함하는 함수는 네이티브 함수로 컴파일됩니다. 관리 되는 함수로 컴파일된 함수가를 포함 하 `_AddressOfReturnAddress`는 함수를 호출 하면가 `_AddressOfReturnAddress` 예상 대로 작동 하지 않을 수 있습니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[C++ 키워드](../cpp/keywords-cpp.md)
