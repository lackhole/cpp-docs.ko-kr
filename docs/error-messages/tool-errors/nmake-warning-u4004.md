---
title: NMAKE 경고 U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: 882f6c98b31d23d283f5e8b32b46a46c543b1a76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298154"
---
# <a name="nmake-warning-u4004"></a>NMAKE 경고 U4004

대상 'targetname'에 대 한 규칙이 너무 많습니다.

둘 이상의 설명 블록 단일 콜론을 사용 하 여 지정된 된 대상에 대해 지정 되었습니다 (**:**) 구분 기호로 합니다. NMAKE는 첫 번째 설명 블록에 있는 명령을 실행 하 고 나머지 블록을 무시 합니다.

동일한 대상에 여러 종속성을 지정 하려면 이중 콜론을 사용 합니다 (`::`) 각 연결선에 구분 기호로 사용 합니다.