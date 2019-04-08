---
title: __wbinvd
ms.date: 11/04/2016
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: 99c7a452e063dea328e4aa1362aae8783929deb0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039269"
---
# <a name="wbinvd"></a>__wbinvd

**Microsoft 전용**

다시 작성 및 캐시 무효화를 생성 (`wbinvd`) 명령입니다.

## <a name="syntax"></a>구문

```
void __wbinvd(void);
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__wbinvd`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 함수는 0의 권한 수준 (CPL)를 사용 하 여 커널 모드에서 사용할 수만 및 루틴은 내장 함수로 사용할 수만 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)