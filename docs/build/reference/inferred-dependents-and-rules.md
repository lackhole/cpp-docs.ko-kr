---
title: 유추된 종속 파일과 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: b9c3055db0cc173999e1737986166eb334dcf96c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827047"
---
# <a name="inferred-dependents-and-rules"></a>유추된 종속 파일과 규칙

NMAKE 유추 해당 규칙이 있는 경우 대상에 대해 유추 된 종속을 가정 합니다. 규칙이 적용 되는 경우:

- *toext* 대상의 확장명과 일치 합니다.

- *fromext* 일치 하는 대상의 기본 이름 및 포함 된 파일의 확장명은 현재 또는 지정 된 디렉터리에 존재 합니다.

- *fromext* 중인 [합니다. 접미사](dot-directives.md); 기타 *fromext* 일치 규칙에는 더 높은 **합니다. 접미사** 우선 순위입니다.

- 없는 명시적 종속 파일에 더 높은 **합니다. 접미사** 우선 순위입니다.

유추 된 종속 예기치 않은 부작용을 일으킬 수 있습니다. NMAKE의 대상의 설명 블록 명령이 포함 된 경우 규칙에 명령 대신 명령을 실행 합니다.

## <a name="see-also"></a>참고자료

[유추 규칙](inference-rules.md)
