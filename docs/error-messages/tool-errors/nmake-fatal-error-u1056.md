---
title: NMAKE 심각한 오류 U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: b15b14c04dd91ae648ea4311612c122f04f90477
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367267"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE 심각한 오류 U1056

명령 처리기를 찾을 수 없습니다.

명령 프로세서에 지정 된 경로에 없습니다. 합니다 **COMSPEC** 하거나 **경로** 환경 변수입니다.

NMAKE는 COMMAND.COM 또는 cmd.를 사용합니다. Exe 명령을 실행할 때 명령 프로세서로 사용 합니다. 에 설정 된 경로에 명령 프로세서를 먼저 찾고 **COMSPEC**합니다. 하는 경우 **COMSPEC** NMAKE 검색에 지정 된 디렉터리가 존재 하지 않는 **경로**합니다.