---
title: _enable
ms.date: 11/04/2016
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: e1ece6d6f4040b81b55d8400407d46f165b56b53
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024519"
---
# <a name="enable"></a>_enable

**Microsoft 전용**

인터럽트를 사용하도록 설정합니다.

## <a name="syntax"></a>구문

```
void _enable(void);
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_enable`|x86, ARM, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`_enable` 프로세서 인터럽트 플래그를 설정 하도록 지시 합니다. x86 시스템에서 이 함수는 인터럽트 플래그 설정(`sti`) 명령을 생성합니다.

이 함수는 커널 모드에서만 사용할 수 있습니다. 사용자 모드에서 이 함수를 사용하면 권한 있는 명령 예외가 throw됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)