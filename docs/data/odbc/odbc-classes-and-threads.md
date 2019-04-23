---
title: ODBC 클래스와 스레드
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: 2d11cdab632e916f548011462f9738bc267fc730
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023532"
---
# <a name="odbc-classes-and-threads"></a>ODBC 클래스와 스레드

MFC 4.2 부터는 경우 MFC ODBC 클래스에 대 한 다중 스레딩 지원 하지만 참고, 해당 MFC 지원을 제공 하지 않습니다 다중 스레딩 DAO 클래스에 대 한 합니다.

ODBC 클래스에 대 한 다중 스레드 지원에는 몇 가지 제한 사항이 있습니다. 이러한 클래스는 ODBC API를 래핑할 때문에 작성 된 구성 요소는 다중 스레드 지원 제한 됩니다. 예를 들어, 대부분의 ODBC 드라이버는 스레드로부터 안전 하지 따라서 MFC ODBC 클래스는 이러한 드라이버 중 하나를 사용 하 여 사용 하는 경우 스레드 안전 하지 않습니다. 특정 드라이버는 스레드로부터 안전 여부를 확인 해야 합니다.

다중 스레드 응용 프로그램을 만들 때 여러 스레드를 사용 하 여 동일한 개체를 조작 하는 주의 해야 합니다. 예를 들어, 동일한를 사용 하 여 `CRecordset` 두 스레드에서 개체 데이터를 검색할 때 문제가 발생할 수 있습니다; 페치된 스레드와 다른 스레드에서 인출 된 데이터를 덮어쓸 수 있습니다. 별도 스레드에서 MFC ODBC 클래스의 보다 일반적인 사용 개방적이 고 공유 하는 것 `CDatabase` 별도 같은 ODBC 연결을 사용 하는 스레드 간에 개체 `CRecordset` 각 스레드에 개체입니다. 열려 있지 않은 전달 해서는 안 참고 `CDatabase` 개체는 `CRecordset` 다른 스레드에서 개체입니다.

> [!NOTE]
>  여러 스레드가 동일한 개체를 조작 해야 하는 경우 중요 섹션 등 적절 한 동기화 메커니즘을 구현 해야 합니다. 주의 특정 작업을 같은 `Open`, 보호 되지 않습니다. 이러한 작업 호출 되지 것입니다 동시에 별도 스레드에서 있을 수 있습니다.

다중 스레드 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [다중 스레딩 항목](../../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[데이터 액세스 프로그래밍 (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)