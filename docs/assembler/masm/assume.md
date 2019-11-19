---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 4bf8f0c41e9ce3e296cf201efd4fd9be2033cbdb
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73702474"
---
# <a name="assume-32-bit-masm"></a>가정 (32 비트 MASM)

레지스터 값에 대 한 오류 검사를 사용 하도록 설정 합니다. (32 비트 MASM에만 해당)

## <a name="syntax"></a>구문

> *Segregister*:*name* [[, *segregister*:*name*]] ...<br/>
> *Dataregister*:*type* [[, *dataregister*:*type*]] ...<br/>
> *등록*가정: 오류 [[, *등록*: 오류]] ...<br/>
> [[*Register*:]] NOTHING [[, *register*: NOTHING]]을 가정 합니다.

## <a name="remarks"></a>주의

`ASSUME` 적용 된 후 어셈블러는 지정 된 레지스터의 값에 대 한 변경 내용을 감시 합니다. 레지스터를 사용 하는 경우 **오류** 를 생성 합니다. 등록 오류 검사를 제거 하지 **않습니다** . 한 문에서 여러 종류의 가정을 조합할 수 있습니다.

## <a name="see-also"></a>참조

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>