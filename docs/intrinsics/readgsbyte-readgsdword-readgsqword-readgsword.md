---
title: __readgsbyte, __readgsdword, __readgsqword, __readgsword
ms.date: 11/04/2016
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
ms.openlocfilehash: a677b96975e0d2adcc7e548992a12bd597bea6a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396472"
---
# <a name="readgsbyte-readgsdword-readgsqword-readgsword"></a>__readgsbyte, __readgsdword, __readgsqword, __readgsword

**Microsoft 전용**

GS 세그먼트의 시작을 기준으로 오프셋으로 지정 된 위치에서 메모리를 읽습니다.

## <a name="syntax"></a>구문

```
unsigned char __readgsbyte(
   unsigned long Offset
);
unsigned short __readgsword(
   unsigned long Offset
);
unsigned long __readgsdword(
   unsigned long Offset
);
unsigned __int64 __readgsqword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>매개 변수

*Offset*<br/>
[in] 시작 부분 으로부터의 오프셋 `GS` 에서 읽을 수 있습니다.

## <a name="return-value"></a>반환 값

메모리 내용의 바이트, word, 2 배 워드를 또는 쿼드 워드 (호출 함수의 이름으로 표시) 하는 대로 위치 `GS:[Offset]`합니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readgsbyte`|X64|
|`__readgsdword`|X64|
|`__readgsqword`|X64|
|`__readgsword`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이러한 루틴은 내장 함수로 사용할 수만 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
