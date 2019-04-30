---
title: 컴파일러 경고(수준 4) C4960
ms.date: 11/04/2016
f1_keywords:
- C4960
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
ms.openlocfilehash: ff4a9b3d78a108a45abb18c22049b104e630bf15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280246"
---
# <a name="compiler-warning-level-4-c4960"></a>컴파일러 경고(수준 4) C4960

'function'이 너무 커서 프로파일링할 수 없습니다.

[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)를 사용하는 경우 컴파일러에서 65,535개 명령보다 큰 함수를 포함하는 입력 모듈을 발견했습니다. 이렇게 큰 함수는 프로필 기반 최적화에 사용할 수 없습니다.

이 경고를 해결하려면 함수 크기를 줄입니다.