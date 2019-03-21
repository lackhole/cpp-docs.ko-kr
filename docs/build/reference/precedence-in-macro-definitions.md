---
title: 매크로 정의의 우선 순위
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 38a653a9f460beae81f9f88ea457870d30f25339
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826642"
---
# <a name="precedence-in-macro-definitions"></a>매크로 정의의 우선 순위

NMAKE는 매크로 정의가 여러 개 있으면 우선 순위가 가장 높은 정의 사용 합니다. 다음 목록에는 최고부터 최하까지 우선 순위를 보여 줍니다.

1. 명령줄에서 정의 된 매크로

1. 매크로 메이크파일의 정의 하거나 파일 포함

1. 상속 된 환경 변수 매크로

1. Tools.ini 파일에 정의 된 매크로

1. 미리 정의 된 매크로 같은 [CC](command-macros-and-options-macros.md) 고 [AS](command-macros-and-options-macros.md)

/E 동일한 이름 가진 메이크파일 매크로 재정의 하도록 환경 변수에서 상속 하는 매크로를 사용 합니다. 사용 하 여 **! UNDEF** 명령줄을 재정의 합니다.

## <a name="see-also"></a>참고자료

[NMake 매크로 정의](defining-an-nmake-macro.md)
