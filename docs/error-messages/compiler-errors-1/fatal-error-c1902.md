---
title: 심각한 오류 C1902
ms.date: 11/04/2016
f1_keywords:
- C1902
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
ms.openlocfilehash: c425430a6d08ae8a97c4dcd0f5764f44dee43e5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165868"
---
# <a name="fatal-error-c1902"></a>심각한 오류 C1902

프로그램 데이터베이스 관리자 일치 하지 않습니다. 설치를 확인 하십시오

프로그램 데이터베이스 파일 (.pdb)을 최신 버전의 mspdb 사용 하 여 만든*XXX*컴파일러 시스템에서 찾은 것 보다는.dll입니다. 이 오류는 일반적으로 mspdbsrv.exe 또는 mspdbcore.dll이 누락 되거나 mspdb 버전이 서로 다르면 나타냅니다*XXX*.dll입니다. (합니다 *XXX* mspdb 자리 표시자*XXX*각 제품 릴리스를 사용 하 여.dll 파일 이름 변경 합니다. 예를 들어 Visual Studio 2015에 대 한 파일 이름은 mspdb140.dll.)

버전이 일치 하는 mspdbsrv.exe, mspdbcore.dll 및 mspdb 보장*XXX*.dll 시스템에 설치 됩니다. 일치 하지 않는 버전 대상 플랫폼에 대 한 링크 컴파일러와 도구가 포함 된 디렉터리에 복사 하지 않은 것을 확인 합니다. 예를 들어 수 복사한 파일을 설정 하지 않고 명령 프롬프트에서 컴파일러나 링크 도구를 호출할 수 있도록 합니다 **경로** 환경 변수가 적절 하 게 합니다.