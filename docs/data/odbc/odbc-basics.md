---
title: ODBC 기초
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
ms.openlocfilehash: e14f5d051b9684cd79a34f5fb50feeb785d2f927
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395796"
---
# <a name="odbc-basics"></a>ODBC 기초

이 항목에서는 개방형 데이터베이스 연결 (ODBC)의 기본 사항을 제공 합니다.

- [ODBC는 데이터베이스 클래스를 사용 하 여 작동 하는 방법](../../data/odbc/odbc-and-the-database-classes.md)

- [ODBC 드라이버 다이너셋을 사용 하 여 작동 하는 방법](../../data/odbc/odbc-driver-requirements-for-dynasets.md)

- [ODBC 구성 요소 응용 프로그램과 함께 재배포할 필요](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

관련된 항목을 읽어 하고자 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.

> [!NOTE]
> ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC Data Access Object(DAO) 클래스를 통해서도 액세스할 수 있습니다.

> [!NOTE]
> MFC ODBC 클래스에는 유니코드 지원 및 다중 스레딩 합니다. 다중 스레딩 지원에 대 한 자세한 내용은 참조 하세요. [ODBC 클래스와 스레드](../../data/odbc/odbc-classes-and-threads.md)

ODBC에는 응용 프로그램이 ODBC 드라이버는 모든 데이터베이스 데이터에에서 액세스할 수 있도록 호출 수준 인터페이스입니다. ODBC를 사용 하 여 최종 사용자가 ODBC 드라이버가 있는 모든 데이터베이스에 대 한 액세스를 사용 하 여 데이터베이스 응용 프로그램을 만들 수 있습니다. ODBC 원본 데이터베이스 관리 시스템 (DBMS)에 종속 되지 않는 응용 프로그램을 수 있는 API를 제공 합니다.

ODBC는 데이터베이스 부분의는 Microsoft Windows 열기 Services 아키텍처 (WOSA), Windows 기반 데스크톱 응용 프로그램에서 각 플랫폼에 대 한 응용 프로그램을 다시 작성 하지 않고도 여러 컴퓨팅 환경에 연결할 수 있는 인터페이스입니다.

다음은 ODBC의 구성 요소입니다.

- ODBC API

   라이브러리 함수를 호출, 오류 코드 및 표준 집합이 [SQL](../../data/odbc/sql.md) Dbms의 데이터에 액세스 하기 위한 구문이 있습니다.

- ODBC 드라이버 관리자

   동적 연결 라이브러리 (Odbc32.dll) 응용 프로그램을 대신 하 여 ODBC 데이터베이스 드라이버를 로드 하는 합니다. 응용 프로그램에 투명 합니다.

- ODBC 데이터베이스 드라이버

   특정 Dbms에 대 한 ODBC 함수 호출을 처리 하는 하나 이상의 Dll입니다. 제공 되는 드라이버 목록을 참조 하세요 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.

- [ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)

   동적 연결 라이브러리 (Odbccr32.dll) 드라이버는 ODBC 드라이버 관리자 사이의 있고 데이터를 통해 스크롤 처리 합니다.

- [ODBC 관리자](../../data/odbc/odbc-administrator.md)

   응용 프로그램에 대 한 데이터 원본으로 사용할 수 있도록 하는 DBMS를 구성 하는 데 사용 되는 도구입니다.

응용 프로그램 DBMS와 직접 작업 하지 않고 DBMS 특별히 작성 된 ODBC 드라이버를 통해 작업 하 여 Dbms에서 독립성을 실현 합니다. 드라이버는 개발자의 작업을 단순화 하 고 다양 한 데이터 원본에 사용할 수 있도록 해당 DBMS 사용할 수 명령으로 호출으로 변환 합니다.

데이터베이스 클래스는 ODBC 드라이버가 있는 모든 데이터 소스를 지원 합니다. 여기 들어 예를 들어, 관계형 데이터베이스, 인덱싱된 순차 액세스 메서드 (ISAM) 데이터베이스, Microsoft Excel 스프레드시트 또는 텍스트 파일에 포함 됩니다. ODBC 드라이버로 데이터 원본에 대 한 연결을 관리 하 고 SQL을 사용 하 여 데이터베이스에서 레코드를 선택 합니다.

시각적 개체의이 버전에 포함 된 ODBC 드라이버의 목록은 C++ 추가 드라이버를 얻는 방법에 대 한 자세한 내용은 참조 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)