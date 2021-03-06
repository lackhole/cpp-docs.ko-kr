---
title: MFC ODBC 소비자 마법사
ms.date: 08/29/2019
helpviewer_keywords:
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
ms.openlocfilehash: 84fdc0d180f5b1b0f2e64c3597cb474611ad3914
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177440"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC 소비자 마법사

::: moniker range="vs-2019"

Visual Studio 2019 이상에서는 이 마법사를 사용할 수 없습니다.

::: moniker-end

::: moniker range="<=vs-2017"

이 마법사는 지정 된 데이터 원본에 액세스 하는 데 필요한 ODBC 레코드 집합 클래스 및 데이터 바인딩을 설정 합니다.

## <a name="uielement-list"></a>UI 요소 목록

- **데이터 원본**

  **데이터 원본** 단추를 사용 하 여 지정 된 ODBC 드라이버를 사용 하 여 지정 된 데이터 소스를 설정할 수 있습니다. DSN (데이터 원본 파일)에 대 한 자세한 내용은 ODBC SDK의 [파일 데이터 원본](/sql/odbc/reference/file-data-sources) 을 참조 하세요.

  **데이터 소스 선택** 대화 상자에는 다음과 같은 두 개의 탭이 있습니다.

  - **파일 데이터 원본** 탭:

     **찾는 위치** 상자는 데이터 원본으로 사용할 파일을 선택할 디렉터리를 지정 합니다. 기본값은 Files\Common Files\ODBC\Data Sources입니다. 기존 파일 데이터 원본 (dsn 파일)이 기본 목록 상자에 나타납니다. [ODBC 데이터 원본 관리자](/sql/odbc/admin/odbc-data-source-administrator)의 **파일 DSN** 탭을 사용 하 여 데이터 원본을 미리 설정 하거나이 대화 상자를 사용 하 여 새로 만들 수 있습니다.

     이 대화 상자에서 새 파일 데이터 원본을 만들려면 DSN 이름을 지정 합니다 `New` .를 클릭 하 여 **새 데이터 원본 만들기** 대화 상자를 표시 합니다. **새 데이터 원본 만들기** 대화 상자에서 적절 한 드라이버를 선택 하 고 클릭 `Next`한 다음, **찾아보기**를 클릭 하 고 데이터 원본으로 사용할 파일의 이름을 선택 합니다. .xls 파일과 같은 비 DSN 파일을 보려면 "모든 파일"을 선택 해야 합니다. 을 클릭 한 다음 마침을 클릭 합니다. `Next` DSN이 아닌 파일을 선택한 경우 파일을 DSN으로 변환 하는 "ODBC Microsoft Excel 설치"와 같은 드라이버별 대화 상자가 표시 됩니다.

     > [!NOTE]
     > ODBC 데이터 원본 관리자를 사용 하 여 새 파일 데이터 원본을 미리 만들 수도 있습니다. **시작** 메뉴에서 **설정**, **제어판**, **관리 도구**, **데이터 원본 (odbc)** 및 **odbc 데이터 원본 관리자**를 차례로 선택 합니다.

     **DSN 이름** 상자에서 파일 데이터 원본의 이름을 지정할 수 있습니다. DSN 이름이 Excel 파일의 경우 .xls와 같이 적절 한 파일 확장명으로 끝나는지 또는 Access 파일용 .mdb를 사용 해야 합니다.

     Dsn에 대 한 자세한 내용은 ODBC SDK의 [파일 데이터 원본](/sql/odbc/reference/file-data-sources) 을 참조 하세요.

  - **컴퓨터 데이터 원본** 탭:

     이 탭에는 시스템 및 사용자 데이터 원본이 나열 됩니다. 사용자 데이터 원본은이 컴퓨터의 사용자에 따라 다릅니다. 시스템 데이터 원본은이 컴퓨터의 모든 사용자가 사용 하거나 시스템 전반의 서비스에서 사용할 수 있습니다. ODBC SDK의 [컴퓨터 데이터 원본](/sql/odbc/reference/machine-data-sources) 을 참조 하세요.

     ODBC 데이터 원본에 대 한 자세한 내용은 ODBC SDK의 [데이터 원본](/sql/odbc/reference/data-sources) 을 참조 하세요.

  **확인**을 클릭하여 마칩니다. **데이터베이스 개체 선택** 대화 상자가 나타납니다. 이 대화 상자에서 소비자가 사용할 테이블이 나 뷰를 선택 합니다. 항목을 클릭 하는 동안 컨트롤 키를 누른 상태에서 여러 뷰와 테이블을 선택할 수 있습니다. **확인**을 클릭하여 마칩니다.

- **클래스**

      The name of the consumer class, based by default on the name of the file or machine data source that you selected.

- **.h 파일**

   사용자가 선택한 파일 또는 컴퓨터 데이터 원본의 이름을 기준으로 하는 소비자 클래스 헤더 파일의 이름입니다.

- **.cpp 파일**

   선택한 파일 또는 컴퓨터 데이터 원본의 이름을 기반으로 하는 소비자 클래스 구현 파일의 이름입니다.

- **형식**

   레코드 집합이 다이너셋 (기본값) 인지 스냅숏 인지를 지정 합니다.

   - **다이너셋**: 레코드 집합이 다이너셋 임을 지정 합니다. 다이너셋은 쿼리 된 데이터베이스의 데이터에 인덱싱된 뷰를 제공 하는 쿼리 결과입니다. 다이너셋은 원래 데이터에 대 한 정수 인덱스만 캐시 하므로 스냅숏에 대 한 성능 향상을 제공 합니다. 인덱스는 쿼리 결과로 찾은 각 레코드를 직접 가리키며 레코드가 제거 되었는지 여부를 나타냅니다. 또한 쿼리 된 레코드의 업데이트 된 정보에 액세스할 수 있습니다. 기본값입니다.

   - **스냅숏**: 레코드 집합을 스냅숏으로 지정 합니다. 스냅숏은 쿼리 결과 이며 한 시점에 데이터베이스에 대 한 뷰입니다. 쿼리 결과로 발견 된 모든 레코드는 캐시 되므로 원본 레코드에 대 한 변경 내용이 표시 되지 않습니다.

- **모든 열 바인딩**

   선택한 테이블의 모든 열이 바인딩되는지 여부를 지정 합니다. 이 상자를 선택 하면 (기본값) 모든 열이 바인딩됩니다. 이 확인란을 선택 하지 않으면 열이 바인딩되지 않으며 레코드 집합 클래스에서 수동으로 바인딩해야 합니다.

::: moniker-end

## <a name="see-also"></a>참고자료

[MFC ODBC 사용](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)
