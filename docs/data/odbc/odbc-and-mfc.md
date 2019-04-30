---
title: ODBC 및 MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
ms.openlocfilehash: 9b7d04e2eb8bbb1adf96e05282861ef33e20434a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395874"
---
# <a name="odbc-and-mfc"></a>ODBC 및 MFC

> [!NOTE]
>  MFC 데이터베이스 클래스를 사용 하려면 데이터 원본에 대 한 적절 한 ODBC 드라이버가 있어야 합니다. SQL Server에 대 한 최신 Microsoft ODBC 드라이버가 [Microsoft ODBC Driver 13 for SQL Server](https://www.microsoft.com/download/details.aspx?id=50420)합니다. 대부분의 데이터베이스 공급 업체는 Windows에 대 한 ODBC 드라이버를 제공합니다.

이 항목에서는 Microsoft Foundation 클래스 (MFC) 라이브러리의 데이터베이스 ODBC 기반 클래스의 기본 개념을 소개 하 고 클래스를 함께 사용 하는 방법을 간략하게 설명 합니다. ODBC 및 MFC에 대 한 자세한 내용은 다음 항목을 참조 하세요.

- [데이터 소스에 연결](connecting-to-a-data-source.md)

- [레코드 선택 및 조작](selecting-and-manipulating-records.md)

- [폼에서 데이터의 표시와 조작](displaying-and-manipulating-data-in-a-form.md)

- [문서 및 뷰 작업](working-with-documents-and-views.md)

- [ODBC 및 SQL 액세스](access-to-odbc-and-sql.md)

- [MFC ODBC 클래스에 대한 추가 정보](further-reading-about-the-mfc-odbc-classes.md)

ODBC를 기반으로 MFC 데이터베이스 클래스는 ODBC 드라이버를 사용할 수 있는 모든 데이터베이스에 대 한 액세스를 제공 하도록 설계 되었습니다. 클래스는 ODBC를 사용 하므로 여러 다른 데이터 형식 및 다른 로컬/원격 구성에는 데이터 응용 프로그램에 액세스할 수 있습니다. 다른 Dbms (데이터베이스 관리 시스템)를 처리 하는 특별 한 경우 코드를 작성할 필요가 없습니다. 사용자가 액세스 하려는 데이터에 대 한 적절 한 ODBC 드라이버와 저장 된 테이블의 데이터를 조작 하려면 프로그램을 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](open-database-connectivity-odbc.md)