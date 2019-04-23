---
title: '데이터 소스: 데이터 원본 (ODBC)의 스키마를 결정합니다.'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
ms.openlocfilehash: c419a3ac2d870e6a85675492ee6c9b726427a0e9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040032"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>데이터 소스: 데이터 원본 (ODBC)의 스키마를 결정합니다.

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

`CRecordset` 개체에서 데이터 멤버를 설정하려면 연결할 데이터 원본의 스키마를 알아야 합니다. 데이터 원본의 스키마를 확인하려면 데이터 원본의 테이블 목록, 각 테이블의 열 목록, 각 열의 데이터 형식, 인덱스의 존재 여부 등에 대한 정보를 가져와야 합니다.

## <a name="see-also"></a>참고자료

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[데이터 소스: 연결 관리 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)