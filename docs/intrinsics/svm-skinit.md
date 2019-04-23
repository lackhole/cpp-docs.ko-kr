---
title: __svm_skinit
ms.date: 11/04/2016
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: 199cba2623f9d8e47c08be642ec485599b87976e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026138"
---
# <a name="svmskinit"></a>__svm_skinit

**Microsoft 전용**

가상 컴퓨터 모니터와 같은 안정성이 확인 된 보안 소프트웨어의 로드를 시작합니다.

## <a name="syntax"></a>구문

```
void __svm_skinit(
   int SLB
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`SLB`|64k 바이트의 32 비트 실제 주소 보안 로더 블록 (SLB).|

## <a name="remarks"></a>설명

`__svm_skinit` 함수는 `SKINIT` 컴퓨터 명령에 해당합니다. 이 함수는 프로세서 및 신뢰할 수 있는 플랫폼 모듈 (TPM)를 사용 하 여 확인 하 고 보안 커널 (SK)를 호출 하는 신뢰할 수 있는 소프트웨어를 로드 하는 보안 시스템의 일부입니다. 가상 컴퓨터 모니터는 보안 커널의 예시입니다. 보안 시스템 프로그램 구성 요소 초기화 프로세스 중에 로드 하 고 컴퓨터가 다중 프로세서 인터럽트, 장치 액세스 또는 다른 응용 프로그램에 의해 변조 되지 않도록 보호 하는 구성 요소를 확인 합니다.

합니다 `SLB` 64k 메모리 블록을 호출의 실제 주소를 지정 하는 매개 변수를 *로더 블록 보안* (SLB). SLB를 컴퓨터에 대 한 운영 환경을 설정 하 고 이후에 보안 커널을 로드 하는 보안 로더를 호출 하는 프로그램을 포함 합니다.

이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 문서에 대해 검색 "AMD64 아키텍처 프로그래머 수동 볼륨 2: 24593, 3.11, 수정 버전 번호를 문서화, system Programming "를 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_skinit`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)