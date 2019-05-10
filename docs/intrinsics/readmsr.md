---
title: __readmsr
ms.date: 11/04/2016
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 2c866213c452f3b8791bf0fe031a43bb024e91fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262777"
---
# <a name="readmsr"></a>__readmsr

**Microsoft 전용**

생성 된 `rdmsr` 로 지정 된 모델 특정 레지스터 읽기는 명령 `register` 하 고 해당 값을 반환 합니다.

## <a name="syntax"></a>구문

```
__int64 __readmsr(
   int register
);
```

#### <a name="parameters"></a>매개 변수

*register*<br/>
[in] 읽기 모델 특정 레지스터입니다.

## <a name="return-value"></a>반환 값

지정된 된 레지스터의 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readmsr`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 함수는 커널 모드에서 사용할 수만 및 루틴은 내장 함수로 사용할 수만 있습니다.

자세한 내용은 AMD 설명서를 참조 하십시오.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)