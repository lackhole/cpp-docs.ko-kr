---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c3a04f68b7fd17b2b6459c219a98fd99ec2d62d4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397250"
---
# <a name="local-masm"></a>LOCAL (MASM)

첫 번째 지시문의 매크로 내에서 **로컬** 은 매크로의 각 인스턴스에 고유한 레이블을 정의 합니다.

## <a name="syntax"></a>구문

> **로컬** *localname* ⟦, *localname* ... ⟧
>
> **LOCAL** *label* ⟦ __\[__ *count* __]__ ⟧ ⟦ __:__ *type*⟧ ⟦ __,__ *label* ⟦ __\[__ *count* __]__ ⟧ ⟦*type*⟧ ... ⟧

## <a name="remarks"></a>주의

두 번째 지시문의 프로시저 정의 (**PROC**) 내에서 **로컬** 은 프로시저 기간 동안 존재 하는 스택 기반 변수를 만듭니다. *레이블은* 단순 변수 이거나 *count* 요소를 포함 하는 배열일 수 있습니다.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)
