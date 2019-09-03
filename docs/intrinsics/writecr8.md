---
title: __writecr8
ms.date: 09/02/2019
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: c8df13c15b5cd8a51b77d65ad930a1852809ee30
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219239"
---
# <a name="__writecr8"></a>__writecr8

**Microsoft 전용**

CR8 레지스터에 `Data` 값을 씁니다.

## <a name="syntax"></a>구문

```C
void writecr8(
   unsigned __int64 Data
);
```

### <a name="parameters"></a>매개 변수

*데이터로*\
진행 CR8 레지스터에 쓸 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__writecr8`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`__writecr8` 내장 함수는 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
