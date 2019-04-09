---
title: __stosw
ms.date: 11/04/2016
f1_keywords:
- __stosw
helpviewer_keywords:
- stosw instruction
- __stosw intrinsic
- rep stosw instruction
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
ms.openlocfilehash: c203973a79c2c3b1094ad8a5351db0999a56bf19
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035759"
---
# <a name="stosw"></a>__stosw

**Microsoft 전용**

저장소 문자열 명령 생성 (`rep stosw`).

## <a name="syntax"></a>구문

```
void __stosw(
   unsigned short* Dest,
   unsigned short Data,
   size_t Count
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out] 작업의 대상입니다.

*데이터*<br/>
[in] 데이터 저장소입니다.

*개수*<br/>
[in] 쓸 단어 블록의 길이입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__stosw`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

결과 단어 `Data` 블록으로 기록 됩니다 `Count` 에서 단어를 `Dest` 문자열입니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

## <a name="example"></a>예제

```
// stosw.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosw)

int main()
{
    unsigned short val = 128;
    unsigned short a[100];
    memset(a, 0, sizeof(a));
    __stosw(a+10, val, 2);
    printf_s("%u %u %u %u", a[9], a[10], a[11], a[12]);
}
```

```Output
0 128 128 0
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)