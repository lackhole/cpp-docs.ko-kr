---
title: __readcr0
ms.date: 11/04/2016
f1_keywords:
- __readcr0
helpviewer_keywords:
- __readcr0 intrinsic
ms.assetid: 25bdb093-d83c-48d7-9c0f-224de8e2c61c
ms.openlocfilehash: 09d44e438b4aa99f9be63927a4cf116f12c6e634
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263895"
---
# <a name="readcr0"></a>__readcr0

**Microsoft 전용**

CR0 레지스터를 읽고 해당 값을 반환합니다.

## <a name="syntax"></a>구문

```
unsigned long __readcr0(void);  /* X86 */
unsigned __int64 __readcr0(void);  /* X64 */
```

## <a name="return-value"></a>반환 값

CR0 레지스터의 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readcr0`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수는 커널 모드에서만 사용할 수 있으며 루틴은 내장 함수로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)