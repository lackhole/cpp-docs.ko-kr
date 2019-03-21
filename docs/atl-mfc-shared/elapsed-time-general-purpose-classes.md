---
title: '경과 시간: 범용 클래스'
ms.date: 11/04/2016
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
ms.openlocfilehash: 5990f6f5db0270c8d24ff35b5c9bbea5b24e6ed7
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742042"
---
# <a name="elapsed-time-general-purpose-classes"></a>경과 시간: 범용 클래스

다음 절차에 간 차이 계산 하는 방법을 보여 줍니다 `CTime` 개체 및 get을 `CTimeSpan` 결과입니다. 사용 된 `CTime` 및 `CTimeSpan` 경과 된 시간을 다음과 같이 계산 하는 개체:

   [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]

계산 있을 `elapsedTime`의 멤버 함수를 사용할 수 있습니다 `CTimeSpan` 경과 된 시간 값의 구성 요소를 추출 하 합니다.
