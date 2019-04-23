---
title: 고객에게 ODBC 구성 요소 재배포
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
ms.openlocfilehash: 1a6ec6f5fdd3c32080d357ca58d31ccea271b7a4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040097"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>고객에게 ODBC 구성 요소 재배포

응용 프로그램을 ODBC 관리자 프로그램의 기능을 통합 하는 경우 배포 해야 합니다도 사용자에 게 이러한 프로그램을 실행 하는 파일입니다. ODBC 파일 이러한 시각적 개체의 \OS\System 디렉터리에 있는 C++ CD-ROM 합니다. Redistrb.wri 파일과 동일한 디렉터리에 사용권 계약에는 재배포할 수 있는 ODBC 파일의 목록을 포함 합니다.

제공 하려는 모든 ODBC 드라이버 설명서를 참조 하세요. Dll 및 기타 파일을 확인 해야 합니다. 또한 읽어야 [고객에 게 ODBC 구성 요소 재배포](../../data/odbc/redistributing-odbc-components-to-your-customers.md), ODBC 구성 요소를 재배포 하는 방법을 설명 합니다.

또한 대부분의 경우에 다른 하나의 파일을 포함 해야 합니다. Odbccr32.dll는 ODBC 커서 라이브러리입니다. 이 라이브러리는 수준 1 드라이버 앞으로 및 뒤로 스크롤 하는 기능을 제공 합니다. 또한 스냅숏 지원 기능을 제공 합니다. ODBC 커서 라이브러리에 대 한 자세한 내용은 참조 하세요. [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.

다음 항목에서는 ODBC 데이터베이스 클래스를 사용 하는 방법에 대 한 자세한 정보를 제공 합니다.

- [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC 데이터 소스 구성](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API 함수 직접 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>참고자료

[ODBC 기본 사항](../../data/odbc/odbc-basics.md)<br/>
[ODBC 관리자](../../data/odbc/odbc-administrator.md)