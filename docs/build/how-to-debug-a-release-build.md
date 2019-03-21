---
title: '방법: 릴리스 빌드 디버깅'
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
ms.openlocfilehash: 6d93fac4e980085c322acb55e6f8758e6cea0a00
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57828082"
---
# <a name="how-to-debug-a-release-build"></a>방법: 릴리스 빌드 디버깅

응용 프로그램의 릴리스 빌드를 디버그할 수 있습니다.

### <a name="to-debug-a-release-build"></a>릴리스 빌드를 디버깅 하려면

1. 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](working-with-project-properties.md)합니다.

1. 클릭 합니다 **C/c + +** 노드. 설정 **디버그 정보 형식** 하 [C7 호환 (/ Z7)](reference/z7-zi-zi-debug-information-format.md) 하거나 **프로그램 데이터베이스 (/Zi)** 합니다.

1. 확장 **링커** 을 클릭 합니다 **일반** 노드. 설정 **증분 링크 사용** 하 [없음 (/ /INCREMENTAL: NO)](reference/incremental-link-incrementally.md)합니다.

1. 선택 된 **디버깅** 노드. 설정할 **디버그 정보 생성** 하 [예 (/debug)](reference/debug-generate-debug-info.md)합니다.

1. 선택 된 **최적화** 노드. 설정 **참조** 하 [/opt: ref](reference/opt-optimizations.md) 하 고 **COMDAT 정리 사용** 에 [/opt: icf](reference/opt-optimizations.md)합니다.

1. 이제 릴리스 빌드 응용 프로그램을 디버깅할 수 있습니다. 오류가 발생 한 위치를 찾을 때까지 문제가 코드 (또는 디버깅 사용 Just In Time)를 단계별로 찾아 다음 잘못 된 매개 변수 또는 코드를 확인 합니다.

   응용 프로그램 디버그 빌드에서 작동 하지만 릴리스 빌드에 실패 하는 경우 소스 코드에 결함이 있는 경우일 수 컴파일러 최적화 기능 중 하나입니다. 문제를 격리 하려면 파일 및 문제의 원인이 되는 최적화를 찾을 때까지 각 소스 코드 파일에 대 한 선택한 최적화를 비활성화 합니다. (프로세스를 신속 하 게 나누고 수 있습니다 파일 두 그룹으로, 하나의 그룹에 대 한 최적화를 사용 하지 않도록 설정 그룹의 문제를 발견 하는 경우 문제가 있는 파일을 격리 될 때까지 계속 합니다.)

   사용할 수 있습니다 [/RTC](reference/rtc-run-time-error-checks.md) 디버그 빌드에서 이러한 버그를 노출 하려고 합니다.

   자세한 내용은 [코드 최적화](optimizing-your-code.md)합니다.

## <a name="see-also"></a>참고자료

[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
