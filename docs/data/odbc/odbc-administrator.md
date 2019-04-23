---
title: ODBC 관리자
ms.date: 11/04/2016
helpviewer_keywords:
- installing ODBC
- ODBC data sources [C++], ODBC Administrator
- ODBC drivers [C++], installing
- ODBC [C++], ODBC Administrator
- Administrator in ODBC
- administration ODBC Administrator
- ODBC Administrator [C++]
- drivers [C++], ODBC
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
ms.openlocfilehash: ac893981ff8c697dc090f1e6ad5ac61886a69f99
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035866"
---
# <a name="odbc-administrator"></a>ODBC 관리자

ODBC 관리자를 등록 하 고 구성 합니다 [데이터 원본](../../data/odbc/data-source-odbc.md) 할 수 있는 로컬 또는 네트워크를 통해. 마법사는 사용자가 데이터 원본에 연결 하는 응용 프로그램에서 코드를 만들려면 ODBC 관리자에 의해 제공 되는 정보를 사용 합니다.

MFC ODBC 클래스 또는 MFC 데이터 액세스 개체 (DAO) 클래스 사용에 대 한 ODBC 데이터 소스를 설정 하려면 먼저 등록 하 고 데이터 원본을 구성 합니다. ODBC 관리자를 사용 하 여 추가 하 고 데이터 원본을 제거 합니다. ODBC 드라이버에 따라 새 데이터 원본을 만들 수도 있습니다.

ODBC 관리자는 설치 하는 동안 설치 됩니다. 했다면 **사용자 지정** 설치에서 ODBC 드라이버를 선택 하지 않은 합니다 **데이터베이스 옵션** 다시 설정을 실행 하는 데 필요한 파일을 설치 해야 하는 대화 상자.

설치 중 설치 하려면 ODBC 드라이버를 선택할 수 있습니다. 시각적 개체를 사용 하 여 나중에 제공 되는 추가 드라이버를 설치할 수 있습니다 C++ 시각적 개체를 사용 하 여 C++ 설치 프로그램입니다.

시각적 개체를 사용 하 여 제공 하지 마십시오. ODBC 드라이버를 설치 하려는 경우 C++에서 드라이버와 함께 제공 되는 설치 프로그램을 실행 해야 합니다.

#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>시각적 개체를 사용 하 여 제공 되는 ODBC 드라이버를 설치 하려면C++

1. 시각적 개체에서 설치 프로그램을 실행 C++ 배포 CD 합니다.

   여는 설치 프로그램에서 대화 상자를 표시 합니다.

1. 클릭 **다음** 도달할 때까지 각 대화 상자에는 **설치 옵션** 대화 상자. 선택 **사용자 지정**를 클릭 하 고 **다음**합니다.

1. 모든 확인란의 선택을 취소 합니다 **Microsoft Visual C++ 설치** 제외 하 고 대화 상자를 **데이터베이스 옵션** 확인란을 선택한 다음 클릭 **세부 정보** 합니다 표시할 **데이터베이스 옵션** 대화 상자.

1. 선택을 취소 합니다 **Microsoft Data Access Objects** 확인란을 선택 합니다 **Microsoft ODBC Driver** 확인란을 선택한 다음 클릭 **세부 정보**합니다.

   합니다 **Microsoft ODBC Driver** 대화 상자가 나타납니다.

1. 드라이버를 설치 하 고 클릭 하려는 선택 **확인** 두 번입니다.

1. 클릭 **다음** 설치를 시작 하려면 나머지 대화 상자에서. 설치 프로그램은 설치가 완료 되 면이 알려 줍니다.

드라이버를 설치 하는 경우에 ODBC 관리자를 사용 하 여 데이터 소스를 구성할 수 있습니다. 제어판의 ODBC 아이콘을 찾을 수 있습니다.

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)