---
title: NMAKE 심각한 오류 U1064
ms.date: 11/04/2016
f1_keywords:
- U1064
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
ms.openlocfilehash: 71213391032989e5faf8889761b29194928125a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367410"
---
# <a name="nmake-fatal-error-u1064"></a>NMAKE 심각한 오류 U1064

MAKEFILE을 찾을 수 및 지정 된 대상이 없습니다.

NMAKE 명령줄 메이크파일을 나 대상을 지정 하지 않았습니다 고 메이크파일 라는 파일을 현재 디렉터리에 없는 합니다.

NMAKE는 메이크파일 또는 명령줄 대상 (또는 둘 다)에 필요합니다. 메이크파일을 사용할 수 있도록 NMAKE를 /F 옵션을 지정 하거나 현재 디렉터리에서 메이크파일을 라는 파일을 배치 합니다. NMAKE는 메이크파일 제공 하지 않으면 유추 규칙을 사용 하 여 명령줄 대상을 만들 수 있습니다.