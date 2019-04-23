---
title: __inword
ms.date: 11/04/2016
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: f7355f64eeb2ace550d272ac6a9b1414e90eb172
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038598"
---
# <a name="inword"></a>__inword

**Microsoft 전용**

사용 하 여 지정 된 포트에서 데이터를 읽고는 `in` 명령입니다.

## <a name="syntax"></a>구문

```
unsigned short __inword(
   unsigned short Port
);
```

#### <a name="parameters"></a>매개 변수

*포트*<br/>
[in] 포트에서 읽기입니다.

## <a name="return-value"></a>반환 값

읽은 데이터의 단어입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__inword`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)