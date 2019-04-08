---
title: __movsd
ms.date: 11/04/2016
f1_keywords:
- __movsd
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
ms.openlocfilehash: 950e83f2cd03e92bb5a9f953affe8e7ff479a408
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031302"
---
# <a name="movsd"></a>__movsd

**Microsoft 전용**

이동 하는 문자열을 생성 합니다 (`rep movsd`) 명령입니다.

## <a name="syntax"></a>구문

```
void __movsd(
   unsigned long* Dest,
   unsigned long* Source,
   size_t Count
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out] 작업의 대상입니다.

*소스*<br/>
[in] 작업의 원본입니다.

*개수*<br/>
[in] 복사할 2 배 워드 횟수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__movsd`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

결과 첫 번째 `Count` 가리키는 2 배 워드 `Source` 에 복사 됩니다는 `Dest` 문자열입니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```
// movsd.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsd)

int main()
{
    unsigned long a1[10];
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,
                            250, 150, 50};
    __movsd(a1, a2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)