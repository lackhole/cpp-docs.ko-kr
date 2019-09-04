---
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: 740c76e5dcc8f94b9257272624a6ad3c1f9726c1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219961"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Microsoft 전용**

전역 인터럽트 플래그를 지웁니다.

## <a name="syntax"></a>구문

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>설명

`__svm_clgi` 함수는 `CLGI` 컴퓨터 명령에 해당합니다. 전역 인터럽트 플래그는 i/o 완료, 하드웨어 온도 경고 또는 디버그 예외 등의 이벤트가 발생 하 여 마이크로프로세서에서 인터럽트를 무시, 연기 또는 처리할지 여부를 결정 합니다.

이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: "시스템 프로그래밍" ( [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트)

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
