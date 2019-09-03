---
title: __indword
ms.date: 09/02/2019
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: 790b65c8a565124df92b82b7ea17174788086a96
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222110"
---
# <a name="__indword"></a>__indword

**Microsoft 전용**

`in` 명령을 사용 하 여 지정 된 포트에서 한 개의 double 단어로 데이터를 읽습니다.

## <a name="syntax"></a>구문

```C
unsigned long __indword(
   unsigned short Port
);
```

### <a name="parameters"></a>매개 변수

*포트인*\
진행 읽을 포트입니다.

## <a name="return-value"></a>반환 값

포트에서 읽은 단어입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__indword`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
