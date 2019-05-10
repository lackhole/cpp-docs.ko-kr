---
title: 데이터 소스(ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: b435c65bab565e109d37e1dd24e051993cbb30c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397915"
---
# <a name="data-source-odbc"></a>데이터 소스(ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

데이터베이스 용어에서 데이터 원본 집합이 특정 데이터를 해당 데이터와 데이터 원본 이름을 사용 하 여 표현할 수 있는 데이터 원본의 위치에 액세스 하는 데 필요한 정보입니다. 클래스를 사용 하려면 [CDatabase](../../mfc/reference/cdatabase-class.md), 데이터 원본 열기 데이터베이스 연결 (ODBC) 관리자를 통해 구성한 하나 여야 합니다. 데이터 원본의 예로 네트워크 또는 로컬 디렉터리에서 Microsoft Access 파일에서 Microsoft SQL Server에서 실행 되는 원격 데이터베이스입니다. 응용 프로그램에서 ODBC 드라이버가 권한이 있는 모든 데이터 원본에 액세스할 수 있습니다.

하나 이상의 데이터 소스를 한 번에 응용 프로그램에서 활성화를 할 수 있습니다, 각각 나타내는 `CDatabase` 개체입니다. 모든 데이터 원본에 여러 개의 동시 연결을 수도 수 있습니다. 원격으로 설치한 드라이버 및 ODBC 드라이버의 기능에 따라 로컬 데이터 원본에 연결할 수 있습니다. 데이터 원본 및 ODBC 관리자에 대 한 자세한 내용은 참조 하세요. [ODBC](../../data/odbc/odbc-basics.md) 하 고 [ODBC 관리자](../../data/odbc/odbc-administrator.md)합니다.

다음 항목에서는 데이터 원본에 대 한 더 설명합니다.

- [데이터 소스: 연결 관리(ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [데이터 소스: 데이터 소스의 스키마 확인(ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)