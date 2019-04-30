---
title: BSCMAKE에서 .Bsc 파일을 빌드하는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 6f721641e021396f112bfe4c075ca0f524100d1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291160"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE에서 .Bsc 파일을 빌드하는 방법

BSCMAKE 빌드하거나 가능한 가장 효율적인 방식으로.bsc 파일을 다시 빌드합니다. 가 잠재적인 문제를 방지 하려면 빌드 프로세스를 이해 해야 합니다.

BSCMAKE에서 찾아보기 정보 파일을 빌드할 때.sbr 파일을을 길이 0으로 잘립니다. 다음에 동일한 파일을 빌드하는 동안 빈 (또는 비어 있는).sbr 파일은 BSCMAKE.sbr 파일에 없는 새 기여 하도록 지시 합니다. BSCMAKE를 하는지 파악할 수 있고 파일의 해당 부분을 업데이트 하는 필요 하지 않습니다. 증분 빌드 충분할 수 있습니다. 모든 빌드 중 (하지 않는 한 /n 옵션을 지정 하 고), BSCMAKE 변경 된.sbr 파일만을 사용 하 여 파일을 증분 방식으로 업데이트 하려면 먼저 시도 합니다.

BSCMAKE /o 옵션으로 지정한 이름을 가진.bsc 파일을 찾습니다. /O 지정 하지 않으면, BSCMAKE.bsc 확장 프로그램을 첫 번째.sbr 파일의 기본 이름을 가진 파일을 찾습니다. 파일이 있으면 BSCMAKE만 영향을 주는.sbr 파일을 사용 하 여 찾아보기 정보 파일의 증분 빌드를 수행 합니다. 파일이 없으면 BSCMAKE 모든.sbr 파일을 사용 하 여 전체 빌드를 수행 합니다. 빌드에 대 한 규칙 아래와 같습니다.

- 성공 하려면 전체 빌드를 모두 지정.sbr 파일이 있어야 하며 잘리지 않아야 합니다. .Sbr 파일 잘리는 경우 BSCMAKE를 실행 하기 전에 다시 컴파일하거나) (에서 다시 만들어야 합니다.

- 성공 하려면 증분 빌드는.bsc 파일이 존재 해야 합니다. 모든.sbr 파일이, 빈 파일에도, 존재 해야 하며 BSCMAKE 명령줄에서 지정 해야 합니다. 명령줄에서.sbr 파일을 생략 하면 BSCMAKE 기여 파일에서 제거 합니다.

## <a name="see-also"></a>참고자료

[.Bsc 파일 빌드](building-a-dot-bsc-file.md)
