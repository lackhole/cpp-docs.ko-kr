---
title: 심각한 오류 C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: b381cc3cfe27d4c4a9d744a6b854a0e43727fe71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243685"
---
# <a name="fatal-error-c1052"></a>심각한 오류 C1052

> 프로그램 데이터베이스 파일에 '*filename*', /debug: fastlink;를 사용 하 여 링커에 의해 생성 된 컴파일러 수 없습니다. 이러한 PDB 파일을 업데이트; 하세요 삭제 하거나 /Fd를 사용 하 여 다른 PDB 파일 이름을 지정 합니다.

컴파일러는 링커에 의해 생성 되는 동일한 프로그램 데이터베이스 (PDB) 파일을 업데이트할 수 없습니다 경우 합니다 [/debug: fastlink](../../build/reference/debug-generate-debug-info.md) 옵션을 지정 합니다. 일반적으로 컴파일러에서 생성 된 파일과 PDB 링커 생성 PDB 파일의 이름이 다. 그러나 동일한 이름을 사용 하도록 설정 하는 경우이 오류가 발생할 수 있습니다.

이 문제를 해결 하려면 다시 컴파일할 전이나 링커 생성 하 고 컴파일러에서 생성 된 PDB 파일에 대해 다른 이름을 만들 수 있습니다 PDB 파일을 명시적으로 삭제할 수 있습니다.

명령줄에서 컴파일러에서 생성 된 PDB 파일 이름을 지정 하려면 사용 합니다 [/Fd](../../build/reference/fd-program-database-file-name.md) 컴파일러 옵션입니다. IDE의 컴파일러에서 생성 된 PDB 파일 이름을 지정 하려면 엽니다는 **속성 페이지** 대화 상자에 프로젝트에 **구성 속성**를 **C /C++**, **출력 파일** 페이지에서 설정 된 **프로그램 데이터베이스 파일 이름** 속성입니다. 이 속성은 기본적으로 `$(IntDir)vc$(PlatformToolsetVersion).pdb`입니다.

또는 링커 생성 PDB 파일 이름을 설정할 수 있습니다. 명령줄에서 링커 생성 PDB 파일 이름을 지정 하려면 사용 합니다 [/PDB](../../build/reference/pdb-use-program-database.md) 링커 옵션입니다. IDE의 링커 생성 PDB 파일 이름을 지정 하려면 엽니다는 **속성 페이지** 대화 상자에 프로젝트에 **구성 속성**를 **링커**를  **디버깅** 페이지에서 설정 된 **프로그램 데이터베이스 파일 생성** 속성입니다. 기본적으로 이 속성은 `$(OutDir)$(TargetName).pdb`로 설정됩니다.
