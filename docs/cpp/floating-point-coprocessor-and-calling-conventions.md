---
title: 부동 소수점 보조 프로세서 및 호출 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 7e9184d66bde26ab0e2b345f8f10c2e28619fd2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154245"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>부동 소수점 보조 프로세서 및 호출 규칙

부동 소수점 보조 프로세서의 어셈블리 루틴을 작성하는 경우 (함수가 ST(0)을 반환해야 한다) **float** 또는 **double** 값을 반환 하지 않는한 부동 소수점 제어 워드를 유지하고, 보조 프로세서 스택을 정리해야 합니다.

## <a name="see-also"></a>참조

[호출 규칙](../cpp/calling-conventions.md)