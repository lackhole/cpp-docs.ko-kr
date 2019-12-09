---
title: __based 문법
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: a8c923b5a111144c539b5bea1b2f47eb58dd1fbd
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857647"
---
# <a name="__based-grammar"></a>__based 문법

**Microsoft 전용**

기반 주소 지정은 개체가 할당된(정적 및 동적 기반 데이터) 세그먼트를 정밀하게 제어해야 할 때 유용합니다.

기반 주소 지정의 32 비트 및 64 비트 컴파일 허용 되는 "포인터 기반" 유일한 형식에 따라 또는 32 비트 또는 64 비트 자료에는 32 비트 또는 64 비트 치환을 포함 하는 형식 정의 하는 **void**합니다.

## <a name="grammar"></a>문법

*범위 기반-한정자*: **__based (** *자료 식* **)**

*base-expression*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*based-variable*: *identifier*

*based-abstract-declarator*: *abstract-declarator*

*base-type*: *type-name*

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[기반 포인터](../cpp/based-pointers-cpp.md)