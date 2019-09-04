---
title: __readcr4
ms.date: 09/02/2019
f1_keywords:
- __readcr4
helpviewer_keywords:
- __readcr4 intrinsic
ms.assetid: b841a27b-fe0d-4ee9-b76b-f91d3eb061fa
ms.openlocfilehash: 4d43b5204d412de40284f89cfd4d74f1c1f9d86d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216724"
---
# <a name="__readcr4"></a>__readcr4

**Microsoft 전용**

CR4 레지스터를 읽고 해당 값을 반환 합니다.

## <a name="syntax"></a>구문

```C
unsigned __int64 __readcr4(void);
```

## <a name="return-value"></a>반환 값

CR4 레지스터의 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readcr4`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

내장 함수는 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
