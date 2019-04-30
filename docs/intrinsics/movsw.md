---
title: __movsw
ms.date: 11/04/2016
f1_keywords:
- __movsw
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
ms.openlocfilehash: 3d584300b514ec3e79c44a2943b3fb8a79495df4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263206"
---
# <a name="movsw"></a>__movsw

**Microsoft 전용**

이동 하는 문자열을 생성 합니다 (`rep movsw`) 명령입니다.

## <a name="syntax"></a>구문

```
void __movsw(
   unsigned short* Dest,
   unsigned short* Source,
   size_t Count
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out] 작업의 대상입니다.

*소스*<br/>
[in] 작업의 원본입니다.

*개수*<br/>
[in] 복사 하는 단어의 수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__movsw`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

결과 첫 번째 `Count` 가리키는 단어 `Source` 에 복사 됩니다는 `Dest` 문자열입니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```
// movsw.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsw)

int main()
{
    unsigned short s1[10];
    unsigned short s2[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    __movsw(s1, s2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", s1[i]);
    printf_s("\n");
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)