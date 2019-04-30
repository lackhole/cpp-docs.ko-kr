---
title: __writemsr
ms.date: 11/04/2016
f1_keywords:
- __writemsr
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
ms.openlocfilehash: ac57bac1d132c581ee12048b89d13ed1d1fdb7da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389712"
---
# <a name="writemsr"></a>__writemsr

**Microsoft 전용**

모델 특정 레지스터 쓰기 생성 (`wrmsr`) 명령입니다.

## <a name="syntax"></a>구문

```
void __writemsr(
   unsigned long Register,
   unsigned __int64 Value
);
```

#### <a name="parameters"></a>매개 변수

*등록*<br/>
[in] 모델 특정 레지스터입니다.

*값*<br/>
[in] 쓸 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__writemsr`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

커널 모드에서이 함수만 사용할 수 있으며이 루틴은 내장 함수로 사용할 수만 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)