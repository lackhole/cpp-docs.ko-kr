---
title: __outbyte
ms.date: 09/02/2019
f1_keywords:
- __outbyte
helpviewer_keywords:
- out instruction
- __outbyte intrinsic
ms.assetid: c4cd1a34-8a02-4e37-993d-3201bc17901a
ms.openlocfilehash: 18792010c45ffb648e9555ccb73f8614c3e3e6ea
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217200"
---
# <a name="__outbyte"></a>__outbyte

**Microsoft 전용**

`out` 로 지정`Port`된 i/o 포트에서 `Data` 지정 된 1 바이트를 전송 하는 명령을 생성 합니다.

## <a name="syntax"></a>구문

```C
void __outbyte(
   unsigned short Port,
   unsigned char Data
);
```

### <a name="parameters"></a>매개 변수

*포트인*\
진행 데이터를 보낼 포트입니다.

*데이터로*\
진행 지정 된 포트에서 전송 될 바이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__outbyte`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
