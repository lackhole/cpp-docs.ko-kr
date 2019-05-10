---
title: '날짜 및 시간: SYSTEMTIME 지원'
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
ms.openlocfilehash: be8462858585a5530f360dae97e155b4967239b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236413"
---
# <a name="date-and-time-systemtime-support"></a>날짜 및 시간: SYSTEMTIME 지원

합니다 [CTime](../atl-mfc-shared/reference/ctime-class.md) 클래스에는 Win32에서 시스템 및 파일 시간을 허용 하는 생성자가 있습니다. 이러한 용도로 `CTime` 개체를 사용하는 경우 이 문서에서 설명하는 대로 해당 초기화를 적절하게 수정해야 합니다.

SYSTEMTIME 구조체에 대 한 정보를 참조 하세요 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime)합니다. FILETIME 구조체에 대 한 정보를 참조 하세요 [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)합니다.

MFC는 MS-DOS 스타일의 시간 인수를 가져오는 `CTime` 생성자를 계속 제공합니다. 그러나 MFC 버전 3.0부터 `CTime` 클래스는 Win32 `SYSTEMTIME` 구조체를 가져오는 생성자와 Win32 `FILETIME` 구조체를 가져오는 또 다른 생성자도 지원합니다.

새로운 `CTime` 생성자는 다음과 같습니다.

- CTime(const SYSTEMTIME& `sysTime`);

- CTime(const FILETIME& `fileTime`);

*fileTime* 매개 변수는 Win32에 대 한 참조가 `FILETIME` 보다 내부 저장소에 대 한 편리한 형식이 64 비트 값으로 시간을 나타내는 구조체를 `SYSTEMTIME` 구조 및 Win32를 사용 하는 형식을 파일 생성 날짜를 나타냅니다.

시스템 시간을 사용하여 초기화된 `CTime` 개체가 코드에 있으면 Win32에서 `SYSTEMTIME` 생성자를 사용해야 합니다.

대부분의 경우 사용 하지 것입니다 `CTime` `FILETIME` 직접 초기화 합니다. 사용 하는 경우는 `CFile` 파일을 조작 하는 개체 [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) 을 통해 파일 타임 스탬프를 검색 합니다.를 `CTime` 사용 하 여 개체 초기화는 `FILETIME` 구조입니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [일반 날짜 및 시간 프로그래밍 MFC의](../atl-mfc-shared/date-and-time.md)

- [날짜 및 시간 프로그래밍 자동화 지원](../atl-mfc-shared/date-and-time-automation-support.md)

## <a name="see-also"></a>참고자료

[날짜 및 시간](../atl-mfc-shared/date-and-time.md)
