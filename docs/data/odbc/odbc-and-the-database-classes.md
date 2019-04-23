---
title: ODBC 및 데이터베이스 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 7692a8128e3dac97c9107e986f6698db76c22c58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025992"
---
# <a name="odbc-and-the-database-classes"></a>ODBC 및 데이터베이스 클래스

MFC ODBC 데이터베이스 클래스는 일반적으로 [CDatabase](../../mfc/reference/cdatabase-class.md) 및 [CRecordset](../../mfc/reference/crecordset-class.md) 클래스의 멤버 함수에서 프로그래머가 직접 만들어야 하는 ODBC API 함수 호출을 캡슐화합니다. 예를 들어, 복잡 한 ODBC 호출 시퀀스, 저장소 위치, 오류 조건 처리 및 기타 작업에 반환된 된 레코드의 바인딩을 관리 하면 데이터베이스 클래스에서. 결과적으로, 레코드를 레코드 집합 개체를 통해 조작에 상당히 단순 클래스 인터페이스를 사용 합니다.

> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC Data Access Object(DAO) 클래스를 통해서도 액세스할 수 있습니다.

데이터베이스 클래스는 ODBC 기능을 캡슐화하지만 ODBC API 함수와의 일대일 매핑을 제공하지는 않습니다. 데이터베이스 클래스는 Microsoft Access 및 Microsoft Visual Basic에서 사용하는 데이터 액세스 개체 모델을 따르는 높은 수준의 추상화를 제공합니다. 자세한 내용은 [ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)를 참조하십시오.

## <a name="see-also"></a>참고자료

