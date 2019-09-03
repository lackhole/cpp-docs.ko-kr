---
title: __readpmc
ms.date: 09/02/2019
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: af0f1874d991771423ddebfedd4624cd0b71760f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221027"
---
# <a name="__readpmc"></a>__readpmc

**Microsoft 전용**

*카운터에*지정 된 성능 모니터링 카운터를 읽는 명령을생성`rdpmc` 합니다.

## <a name="syntax"></a>구문

```C
unsigned __int64 __readpmc(
   unsigned long counter
);
```

### <a name="parameters"></a>매개 변수

*counter*\
진행 읽을 성능 카운터입니다.

## <a name="return-value"></a>반환 값

지정 된 성능 카운터의 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readpmc`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

내장 함수는 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
