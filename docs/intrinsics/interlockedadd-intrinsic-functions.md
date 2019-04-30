---
title: _InterlockedAdd Intrinsic Functions
ms.date: 12/17/2018
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
ms.openlocfilehash: 348e936bb05796e36ae45095f25b943076cec464
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349519"
---
# <a name="interlockedadd-intrinsic-functions"></a>_InterlockedAdd Intrinsic Functions

**Microsoft 전용**

이러한 함수는 하는 경우 둘 이상의 스레드가 공유 변수에 대 한 액세스 작업을 성공적으로 완료 되도록 원자성 추가 수행 합니다.

## <a name="syntax"></a>구문

```
long _InterlockedAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_rel(
   long volatile * Addend,
   long Value
);
__int64 _InterlockedAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_nf (
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
```

#### <a name="parameters"></a>매개 변수

*가 수*<br/>
[out에서] 에 추가할 정수에 대 한 포인터 더하기 연산의 결과 바뀝니다.

*값*<br/>
[in] 추가할 값입니다.

## <a name="return-value"></a>반환 값

두 함수는 모두 추가의 결과를 반환합니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_InterlockedAdd`|ARM|
|`_InterlockedAdd_acq`|ARM|
|`_InterlockedAdd_nf`|ARM|
|`_InterlockedAdd_rel`|ARM|
|`_InterlockedAdd64`|ARM|
|`_InterlockedAdd64_acq`|ARM|
|`_InterlockedAdd64_nf`|ARM|
|`_InterlockedAdd64_rel`|ARM|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`_acq` 또는 `_rel` 접미사가 포함된 이러한 함수 버전은 획득 또는 해제 의미 체계 후에 연관 추가를 수행합니다. *의미 체계를 획득* 이상 메모리 읽기 및 쓰기 전에 연산의 결과 모든 스레드와 프로세서에 표시 됩니다 것을 의미 합니다. 취득은 임계 영역을 입력할 때 유용합니다. *의미 체계를 릴리스* 표시 되도록 모든 스레드와 프로세서에 자체 작업의 결과 표시 되기 전에 모든 메모리 읽기 및 쓰기 즉 강제 합니다. 해제는 임계 영역을 벗어날 때 유용합니다. 포함 된 내장 함수는 `_nf` ("no fence") 접미사는 메모리 장벽으로 작동 하지 않습니다.

이러한 루틴은 내장 함수로만 사용할 수 있습니다.

## <a name="example"></a>예제

```cpp
// interlockedadd.cpp
// Compile with: /Oi /EHsc
// processor: ARM
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedAdd)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FF0000;
        long retval;
        retval = _InterlockedAdd(&data1, data2);
        printf("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

## <a name="output"></a>출력

```Output
0xffffff00 0xff0000 0xffffff00
```

## <a name="example"></a>예제

```cpp
// interlockedadd64.cpp
// compile with: /Oi /EHsc
// processor: ARM
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_InterlockedAdd64)

int main()
{
        __int64 data1 = 0x0000FF0000000000;
        __int64 data2 = 0x00FF0000FFFFFFFF;
        __int64 retval;
        cout << hex << data1 << " + " << data2 << " = " ;
        retval = _InterlockedAdd64(&data1, data2);
        cout << data1 << endl;
        cout << "Return value: " << retval << endl;
}
```

## <a name="output"></a>출력

```Output
ff0000000000 + ff0000ffffffff = ffff00ffffffff
Return value: ffff00ffffffff
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[x86 컴파일러와 충돌](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)