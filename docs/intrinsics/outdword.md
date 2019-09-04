---
title: __outdword
ms.date: 09/02/2019
f1_keywords:
- __outdword
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
ms.openlocfilehash: ce1358e7cef0136ccf7d314038d06d271916e0bc
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221661"
---
# <a name="__outdword"></a>__outdword

**Microsoft 전용**

포트 *포트*에서 더블 워드 *데이터* 를 전송 하는 명령을생성합니다.`out`

## <a name="syntax"></a>구문

```C
void __outdword(
   unsigned short Port,
   unsigned long Data
);
```

### <a name="parameters"></a>매개 변수

*포트인*\
진행 데이터를 보낼 포트입니다.

*데이터로*\
진행 전송할 더블 워드입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__outdword`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
