---
title: '날짜 및 시간: 자동화 지원'
ms.date: 11/04/2016
helpviewer_keywords:
- adding dates
- calculating dates and times
- formatting [Visual Studio], dates
- dates, Automation support
- elapsed time, calculating in Automation
- COleDateTime class, Automation date/time support
- COleDateTimeSpan class, Automation date/time support
- Automation, date and time support
- formatting [Visual Studio], time
- calculations, date and time
- time [Visual Studio], Automation support
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
ms.openlocfilehash: c26534189c7b6f904611e78c5d2d6d0b1d6d7382
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750207"
---
# <a name="date-and-time-automation-support"></a>날짜 및 시간: 자동화 지원

이 문서에는 날짜 및 시간 관리와 관련 된 클래스 라이브러리 서비스를 활용 하는 방법을 설명 합니다. 설명 된 절차는 다음과 같습니다.

- [현재 시간 가져오기](../atl-mfc-shared/current-time-automation-classes.md)

- [경과 된 시간 계산](../atl-mfc-shared/elapsed-time-automation-classes.md)

- [날짜/시간의 문자열 표현을 서식 지정](../atl-mfc-shared/formatting-time-automation-classes.md)

합니다 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) 클래스는 날짜 및 시간 정보를 나타내는 방법을 제공 합니다. 더 자세한 세분성 및 보다 큰 범위를 제공 합니다 [CTime](../atl-mfc-shared/reference/ctime-class.md) 클래스입니다. 합니다 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) 클래스 간 차이점과 같은 경과 된 시간을 나타냅니다. `COleDateTime` 개체입니다.

`COleDateTime` 및 `COleDateTimeSpan` 클래스와 사용할 수 있도록 고안 된는 `COleVariant` 자동화 하는 데 사용 합니다. `COleDateTime` 및 `COleDateTimeSpan` MFC 데이터베이스 프로그래밍에도 유용 하지만 날짜 및 시간 값을 조작 하려고 할 때마다 사용할 수 있습니다. 있지만 `COleDateTime` 클래스에는 큰 값의 범위와 보다 세분화 합니다 `CTime` 개체당 보다 더 많은 저장소 필요 클래스 `CTime`. 또한 몇 가지 특별 한 고려 사항이 기본 날짜 형식을 사용 하 여 작업 하는 경우 있습니다. 참조 [날짜 유형](../atl-mfc-shared/date-type.md) 날짜의 구현에 대 한 자세한 내용은 합니다.

`COleDateTime` 9999 100 년 1 월 1 일 및 12 월 31 일 사이의 날짜를 나타내는 개체를 사용할 수 있습니다. `COleDateTime` 개체에 부동 소수점 값을 1 밀리초의 대략적인 해상도 됩니다. `COleDateTime` 에 있는 MFC 설명서에 정의 된 날짜 데이터 형식에 기반 [COleDateTime::operator 날짜](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)합니다. 날짜의 실제 구현은 이러한 범위를 벗어났습니다. `COleDateTime` 구현 클래스를 사용 하 여 작업을 용이 하 게 이러한 경계를 적용 합니다.

`COleDateTime` 율리우스력 날짜를 지원 하지 않습니다. 양력 100 년 1 월 1 일에 다시에서 확장으로 간주 됩니다.

`COleDateTime` 일광 절약 시간 (DST)를 무시합니다. 다음 코드 예제에서는 비교 전환 날짜를 초과 하는 시간 범위를 계산 하는 두 가지 방법: CRT를 사용 하 여 하나의 및를 사용 하 여 다른 `COleDateTime`합니다. DST 전환, 대부분의 로캘에서 4 월에 두 번째 주 및 월의 세 번째입니다.

첫 번째 메서드는 두 개의 설정 `CTime` 개체를 *time1* 및 *time2*, 4 월 5 및 6 년 4 월 각각 표준 C 형식 구조를 사용 하 여 `tm` 및 `time_t`합니다. 코드 표시 *time1* 하 고 *time2* 및 이들 간의 시간 범위입니다.

두 번째 메서드 두 개를 만듭니다 `COleDateTime` 개체를 `oletime1` 하 고 `oletime2`와 동일한 날짜를 설정 합니다 *time1* 및 *time2*합니다. 표시 `oletime1` 고 `oletime2` 및 이들 간의 시간 범위입니다.

CRT는 올바르게 23 시간 차이 계산합니다. `COleDateTimeSpan` 24 시간 차이 계산합니다.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

## <a name="see-also"></a>참고자료

[날짜 및 시간](../atl-mfc-shared/date-and-time.md)
