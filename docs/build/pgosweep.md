---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 3ba31671fc3794e1cc959d86d914ba1eef2e01e4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827427"
---
# <a name="pgosweep"></a>pgosweep

프로필 기반 최적화에서.pgc 파일을 실행 중인 프로그램에서 모든 프로필 데이터를 작성 하는 데 사용 합니다.

## <a name="syntax"></a>구문

> **pgosweep** [*options*] *image* *pgcfile*

### <a name="parameters"></a>매개 변수

*options*<br/>
(선택 사항) 유효한 값은 *옵션* 됩니다.

- **/?** 또는 **/help** 도움말 메시지를 표시 합니다.

- **/noreset** 런타임 데이터 구조에서 카운트를 유지 합니다.

*image*<br/>
사용 하 여 만들어진.exe 또는.dll 파일의 전체 경로 [/GENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)를 [/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), 또는 [/ltcg: pginstrument](reference/ltcg-link-time-code-generation.md) 옵션입니다.

*pgcfile*<br/>
이 명령은 기록 하는 위치 데이터 개수.pgc 파일입니다.

## <a name="remarks"></a>설명

합니다 **pgosweep** 명령을 사용 하 여 작성 된 프로그램에서 작동 합니다 [/GENPROFILE 또는 /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 옵션 또는 사용 되지 않는 [/ltcg: pginstrument](reference/ltcg-link-time-code-generation.md) 옵션입니다. 실행 중인 프로그램을 중단 하 고 새.pgc 파일에 프로필 데이터를 기록 합니다. 명령은 기본적으로 각 쓰기 작업 후 개수를 다시 설정 합니다. 지정 하는 경우는 **/noreset** 옵션을 명령 값을 기록 되지만 실행 중인 프로그램에서 다시 설정 되지 것입니다. 이 옵션은 나중에 프로필 데이터를 검색 하는 경우 중복 데이터를 제공 합니다.

또 다른 용도 **pgosweep** 방금 응용 프로그램의 정상적인 작동에 대 한 프로필 정보를 검색 하는 것입니다. 예를 들어, 실행할 수 있습니다 **pgosweep** 직후 응용 프로그램을 시작 하 고 해당 파일을 삭제 합니다. 이 비용을 시작 하 여 연결 된 프로필 데이터를 삭제 합니다. 그런 다음 실행할 수 있습니다 **pgosweep** 응용 프로그램을 종료 하기 전에 합니다. 이제 수집 된 데이터에 사용자가 프로그램과 상호 작용할 수 시간 에서만에서 프로필 정보가 있습니다.

.Pgc 파일 이름을 하는 경우 (사용 하 여는 *pgcfile* 매개 변수)는 표준 형식으로 사용할 수 있습니다 *appname! n*.pgc. 이 형식을 사용 하는 경우 컴파일러에서이 데이터를 자동으로 찾습니다 합니다 **/LTCG /USEPROFILE** 하거나 **함수가 /ltcg: pgo** 단계입니다. 표준 형식을 사용 하지 않는 경우 사용 해야 [pgomgr](pgomgr.md) .pgc 파일을 병합 합니다.

> [!NOTE]
> Visual Studio 개발자 명령 프롬프트 에서만에서이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.

실행 파일 내에서 프로필 데이터를 캡처하는 방법에 대 한 내용은 참조 하세요 [PgoAutoSweep](pgoautosweep.md)합니다.

## <a name="example"></a>예제

이 예제에서는 명령 **pgosweep** myapp!1.pgc myapp.exe에 대 한 현재 프로필 정보를 씁니다.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>참고자료

[프로필 기반 최적화](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
