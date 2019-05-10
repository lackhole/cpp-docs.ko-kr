---
title: __movsq
ms.date: 11/04/2016
f1_keywords:
- __movsq
helpviewer_keywords:
- __movsq intrinsic
- rep movsq instruction
- movsq instruction
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
ms.openlocfilehash: 4e4908cd5ffc28840b5a48b735048cccb557e97c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263169"
---
# <a name="movsq"></a>__movsq

**Microsoft 전용**

반복 되는 이동 문자열 생성 (`rep movsq`) 명령입니다.

## <a name="syntax"></a>구문

```
void __movsq(
   unsigned char* Dest,
   unsigned char* Source,
   size_t Count
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out] 작업의 대상입니다.

*소스*<br/>
[in] 작업의 원본입니다.

*개수*<br/>
[in] 복사할 (쿼드 워드)의 수입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__movsq`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

결과 첫 번째 `Count` (쿼드 워드)로 가리키는 `Source` 에 복사 됩니다는 `Dest` 문자열입니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```
// movsq.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsq)

int main()
{
    unsigned __int64 a1[10];
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,
                               150, 50};
    __movsq(a1, a2, 10);

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