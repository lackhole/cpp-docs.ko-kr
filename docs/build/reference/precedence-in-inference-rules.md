---
title: 유추 규칙의 우선 순위
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: ca24134fd1829ad3d97ca67b8c30aae3af4109ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319683"
---
# <a name="precedence-in-inference-rules"></a>유추 규칙의 우선 순위

NMAKE 유추 규칙을 여러 번 정의 된 경우 우선 순위가 가장 높은 정의 사용 합니다. 다음은 순위가 가장 높은 우선 순위를 보여 줍니다.

1. 메이크파일의; 정의 유추 규칙 이후 정의 하 고 순위가 키를 누릅니다.

1. Tools.ini;에 정의 된 유추 규칙 이후 정의 하 고 순위가 키를 누릅니다.

1. 미리 정의 된 유추 규칙입니다.

## <a name="see-also"></a>참고자료

[유추 규칙](inference-rules.md)
