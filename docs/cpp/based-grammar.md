---
title: __based 문법
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 8dec9b0bcc7db25e2ec4c39b9d907922691bfc05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393950"
---
# <a name="based-grammar"></a>__based 문법

## <a name="microsoft-specific"></a>Microsoft 전용

기반 주소 지정은 개체가 할당된(정적 및 동적 기반 데이터) 세그먼트를 정밀하게 제어해야 할 때 유용합니다.

기반 주소 지정의 32 비트 및 64 비트 컴파일 허용 되는 "포인터 기반" 유일한 형식에 따라 또는 32 비트 또는 64 비트 자료에는 32 비트 또는 64 비트 치환을 포함 하는 형식 정의 하는 **void**합니다.

## <a name="grammar"></a>문법

*based-range-modifier*: **__based (***base-expression***)**

*base-expression*: *based-variablebased-abstract-declaratorsegment-namesegment-cast*

*based-variable*: *identifier*

*based-abstract-declarator*: *abstract-declarator*

*base-type*: *type-name*

**Microsoft 전용 종료**

## <a name="see-also"></a>참고

[기반 포인터](../cpp/based-pointers-cpp.md)