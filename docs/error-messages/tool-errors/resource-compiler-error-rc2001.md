---
title: 리소스 컴파일러 오류 RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: f4755e04a744d94636b4b37aaf727e0d733008ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346693"
---
# <a name="resource-compiler-error-rc2001"></a>리소스 컴파일러 오류 RC2001

상수에 줄 바꿈

문자열 상수는 백슬래시 없이 두 번째 줄에서 계속 되었습니다 (**\\**) 또는 결산 잔액과 큰따옴표를 개시 (**"**).

소스 파일에서 두 줄에는 문자열 상수를 중단 하려면 다음 중 하나를 수행 합니다.

- 첫 번째 줄은 줄 연속 문자, 백슬래시를 사용 하 여 종료 합니다.

- 큰따옴표를 사용 하 여 첫 번째 줄에서 문자열을 닫고 다른 따옴표를 사용 하 여 다음 줄에서 문자열을 엽니다.

\N, 하는 문자열 상수에 줄 바꿈 문자를 포함 하는 것에 대 한 이스케이프 시퀀스를 사용 하 여 첫 번째 줄의 끝에 충분 하지 않습니다.