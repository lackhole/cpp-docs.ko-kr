---
title: 컴파일러 경고(수준 1) C4799
ms.date: 11/04/2016
f1_keywords:
- C4799
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
ms.openlocfilehash: 475451b47d461e7ea1428eb715a876fb023694d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152218"
---
# <a name="compiler-warning-level-1-c4799"></a>컴파일러 경고(수준 1) C4799

> 함수의 끝에 EMMS 없는 '*함수*'

함수에 MMX 명령이 하나 이상 없는 `EMMS` 명령입니다. 멀티미디어 명령을 사용 하는 경우는 `EMMS` 명령 또는 `_mm_empty` 내장도 MMX 코드의 끝에서 멀티미디어 태그 단어의 선택을 취소 합니다.

C4799 반환 하기 전에 emms 실행 코드를 제대로 사용 하지 않음을 나타내는 않아 c를 사용 하 여 발생할 수 있습니다. 이러한 헤더에 대해 false 경고입니다. 해제할 수 있습니다 이러한 _SILENCE_IVEC_C4799 않아 c에서 정의 하 여 합니다. 그러나 주의 하십시오이 또한 유지 하는 컴파일러에서이 형식의 올바른 경고를 제공 합니다.

관련 정보를 참조 하세요 [Intel의 MMX 명령 집합](../../assembler/inline/intel-s-mmx-instruction-set.md)합니다.