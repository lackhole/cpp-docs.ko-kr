---
title: _CIsqrt
ms.date: 11/04/2016
apiname:
- _CIsqrt
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _CIsqrt
- CIsqrt
helpviewer_keywords:
- CIsqrt intrinsic
- _CIsqrt intrinsic
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
ms.openlocfilehash: 5042be822df7789d30d2b4ea2d5be6cf8a081ef9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749388"
---
# <a name="cisqrt"></a>_CIsqrt

스택 상위 값의 제곱근을 계산합니다.

## <a name="syntax"></a>구문

```
void __cdecl _CIsqrt();
```

## <a name="remarks"></a>주의

이 버전의 `sqrt` 함수는 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다. 복사본이 생성되지 않도록 하며 레지스터 할당을 돕기 때문에 실행 속도를 높입니다.

결과 값이 스택의 맨 위에 푸시됩니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** x86

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)
