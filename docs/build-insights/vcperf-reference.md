---
title: 'C++빌드 정보: vcperf 참조'
description: 명령줄 유틸리티 vcperf에 대 한 참조입니다.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 195d115edae9947b39795440894e4f6bf0ee485e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73633221"
---
# <a name="c-build-insights-vcperfexe-reference"></a>C++빌드 정보: vcperf 참조

::: moniker range="<=vs-2017"

C++ Build Insights 도구는 Visual Studio 2019에서 사용할 수 있습니다. 해당 버전에 대 한 설명서를 보려면이 문서에 대 한 Visual Studio 버전 선택기 컨트롤을 Visual Studio 2019로 설정 합니다.

::: moniker-end
::: moniker range="vs-2019"

이 문서에서는 *vcperf*에서 사용할 수 있는 명령과이를 사용 하는 방법을 나열 하 고 설명 합니다.

## <a name="commands-to-start-and-stop-traces"></a>추적을 시작 및 중지 하는 명령

*중요: 다음 명령에는 모두 관리 권한이 필요 합니다.*

| 옵션           | 인수 및 설명 |
|------------------|---------------------------|
| `/start`         | `[/nocpusampling]` `<sessionName>` |
|                  | 지정 된 세션 이름으로 추적을 시작 하도록 *vcperf* 에 지시 합니다. 지정 된 컴퓨터에서 한 번에 하나의 활성 세션만 있을 수 있습니다. <br/><br/> `/nocpusampling` 옵션이 지정 된 경우 *vcperf* 는 CPU 샘플을 수집 하지 않습니다. Windows 성능 분석기에서 CPU 사용 (샘플링) 보기를 사용할 수 없게 하지만 수집 된 추적을 더 작게 만듭니다. <br/><br/> 추적이 시작 되 면 *vcperf* 가 즉시 반환 됩니다. 이벤트는 시스템 전체에서 실행 되는 모든 프로세스에 대해 수집 됩니다. 즉, *vcperf*를 실행 하는 데 사용한 것과 동일한 명령 프롬프트에서 프로젝트를 빌드할 필요가 없습니다. 예를 들어 Visual Studio에서 프로젝트를 빌드할 수 있습니다. |
| `/stop`          | `<sessionName>` `<outputFile.etl>` |
|                  | 지정 된 세션 이름으로 식별 된 추적을 중지 합니다. 추적에 대해 후 처리 단계를 실행 하 여 Windows 성능 분석기 (WPA)에서 볼 수 있는 파일을 생성 합니다. 최상의 보기 환경을 위해 C++ Build Insights 추가 기능을 포함 하는 WPA 버전을 사용 합니다. 자세한 내용은 빌드 정보를 [사용 하 여 C++ 시작](get-started-with-cpp-build-insights.md)을 참조 하세요. `<outputFile.etl>` 매개 변수는 출력 파일을 저장할 위치를 지정 합니다. |
| `/stopnoanalyze` | `<sessionName>` `<rawOutputFile.etl>` |
|                  | 지정 된 세션 이름으로 식별 된 추적을 중지 하 고 지정 된 출력 파일에 처리 되지 않은 원시 데이터를 씁니다. 결과 파일은 WPA에서 볼 수 없습니다. <br/><br/> `/stop` 명령과 관련 된 사후 처리 단계는 때때로 길어질 수 있습니다. `/stopnoanalyze` 명령을 사용 하 여이 후 처리 단계를 연기할 수 있습니다. Windows 성능 분석기에서 볼 수 있는 파일을 생성할 준비가 되 면 `/analyze` 명령을 사용 합니다. |

## <a name="miscellaneous-commands"></a>기타 명령

| 옵션     | 인수 및 설명 |
|------------|---------------------------|
| `/analyze` | `<rawInputFile.etl> <outputFile.etl>` |
|            | `/stopnoanalyze` 명령으로 생성 된 원시 추적 파일을 허용 합니다. 이 추적에 대해 사후 처리 단계를 실행 하 여 Windows 성능 분석기에서 볼 수 있는 파일을 생성 합니다. 최상의 보기 환경을 위해 C++ Build Insights 추가 기능을 포함 하는 WPA 버전을 사용 합니다. 자세한 내용은 빌드 정보를 [사용 하 여 C++ 시작](get-started-with-cpp-build-insights.md)을 참조 하세요. |

## <a name="see-also"></a>참조

[빌드 Insights를 C++ 사용 하 여 시작](get-started-with-cpp-build-insights.md)\
[Windows 성능 분석기 기본 사항](wpa-basics.md)\
[Windows Performance Analyzer 뷰 참조](wpa-views-reference.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
