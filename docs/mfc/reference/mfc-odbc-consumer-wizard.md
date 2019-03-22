---
title: MFC ODBC 소비자 마법사
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.class.mfc.consumer.overview
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
ms.openlocfilehash: b6009a1e6b6100eabaa2ed05404217c0d2906be0
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328651"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC 소비자 마법사

> [!WARNING]
> Visual Studio 2017 버전 15.9에서 이 코드 마법사는 더 이상 사용되지 않으므로 Visual Studio의 이후 버전에서 제거됩니다. 이 마법사는 거의 사용되지 않습니다. 이 마법사가 제거되더라도 ATL 및 MFC에 대한 일반 지원은 그대로 유지됩니다. 이 지원 중단에 대한 의견을 공유하려면 [이 설문 조사](https://www.surveymonkey.com/r/QDWKKCN)를 완료하세요. 여러분의 의견은 소중합니다.

이 마법사는 지정 된 데이터 원본에 액세스 하는 데 필요한 ODBC 레코드 집합 클래스와 데이터 바인딩을 설정 합니다.

## <a name="uielement-list"></a>UI 요소 목록

- **데이터 원본**

  합니다 **데이터 원본** 단추 지정된 된 ODBC 드라이버를 사용 하 여 지정 된 데이터 소스를 설정할 수 있습니다. 데이터 원본 파일 (DSN)에 대 한 자세한 내용은 참조 하세요. [파일 데이터 원본을](/sql/odbc/reference/file-data-sources) ODBC SDK에 있습니다.

  합니다 **데이터 원본 선택** 대화 상자에 두 개의 탭이 있습니다.

  - **파일 데이터 원본** 탭:

     합니다 **찾는 위치** 상자에서 데이터 원본으로 사용 될 파일을 선택할 수 있는 디렉터리를 지정 합니다. 기본값은 \Program Files\Common Files\ODBC\Data 원본입니다. 기존 파일 데이터 원본 (.dsn 파일) 기본 목록 상자에 표시 합니다. 데이터 원본 사용 하 여 미리 구성 하거나 설정할 수 있습니다는 **파일 DSN** 탭의 [ODBC 데이터 원본 관리자](/sql/odbc/admin/odbc-data-source-administrator), 또는이 대화 상자를 사용 하 여 새 보고서 만들기.

     이 대화 상자에서 새 파일 데이터 원본을 만들려면 `New` ; DSN 이름을 지정 하는 **새 데이터 원본 만들기** 대화 상자가 나타납니다. 에 **새 데이터 원본 만들기** 대화 상자는 적절 한 드라이버를 선택 하 고 클릭 `Next`; 클릭 **찾아보기**, 선택한 (선택 해야 모든 파일을 데이터 소스로 사용할 파일의 이름 보기 DSN이 아닌 파일과 같은 파일을.xls); 클릭 `Next`를 클릭 하 고 **완료**합니다. (DSN이 아닌 파일을 선택 하면 드라이버 관련 대화 상자에서 "ODBC Microsoft Excel 설정" 파일 DSN을 변환 하는 등.)

     > [!NOTE]
     > 또한 미리 ODBC 데이터 원본 관리자를 사용 하 여 파일 데이터 소스를 새로 만들 수 있습니다. **시작** 메뉴에서 **설정**를 **제어판**, **관리 도구**, **데이터 원본 (ODBC)**, 차례로 **ODBC 데이터 원본 관리자**합니다.

     합니다 **DSN 이름을** 상자를 사용 하는 파일 데이터 원본에 대 한 이름을 지정할 수 있습니다. 예: Excel 파일에 대 한.xls 또는.mdb 파일 액세스에 대 한 적절 한 파일 확장명을 사용 하 여 DSN 이름을 끝나도록 해야 합니다.

     Dsn에 대 한 자세한 내용은 참조 하세요. [파일 데이터 원본을](/sql/odbc/reference/file-data-sources) ODBC SDK에 있습니다.

  - **데이터 소스 컴퓨터** 탭:

     이 탭에는 시스템 및 사용자 데이터 원본을 나열합니다. 사용자 데이터 원본은이 컴퓨터에서 사용자와 관련이 있습니다. 시스템 데이터 원본 또는 시스템 전반에 걸쳐 서비스를이 컴퓨터에서 모든 사용자가 사용할 수 있습니다. 참조 [데이터 원본 컴퓨터](/sql/odbc/reference/machine-data-sources) ODBC sdk

     ODBC 데이터 원본에 대 한 자세한 내용은 참조 하세요. [데이터 원본](/sql/odbc/reference/data-sources) ODBC SDK에 있습니다.

  클릭 **확인** 완료 합니다. 합니다 **데이터베이스 개체 선택** 대화 상자가 나타납니다. 이 대화 상자에서 테이블을 선택 하거나 소비자가 사용할 보고 합니다. 참고 항목을 클릭 하는 동안 컨트롤 키를 눌러 여러 뷰 및 테이블과 선택할 수 있습니다. 클릭 **확인** 완료 합니다.

- **클래스**

      The name of the consumer class, based by default on the name of the file or machine data source that you selected.

- **.h 파일**

   선택한 파일 또는 시스템 데이터 원본의 이름을 기본적으로 하는 소비자 클래스 헤더 파일의 이름입니다.

- **.cpp 파일**

   선택한 파일 또는 시스템 데이터 원본의 이름을 기본적으로 하는 소비자 클래스 구현 파일의 이름입니다.

- **Type**

   레코드 집합이 다이너셋 (기본값) 또는 스냅숏 인지 여부를 지정 합니다.

   - **다이너셋**: 레코드 집합이 다이너셋 임을 지정 합니다. 다이너셋에 인덱싱된 뷰를 쿼리 하는 데이터베이스의 데이터를 제공 하는 쿼리 결과입니다. 다이너셋 원본 데이터에 정수 인덱스만 캐시 및 스냅숏에 대 한 성능이 향상 합니다. 각 레코드에 직접 인덱스 지점 쿼리 결과로 있으며 레코드 제거 되는 경우를 나타냅니다. 또한 업데이트 된 정보를 액세스할 쿼리 한 레코드의 수 있습니다. 이 값이 기본값입니다.

   - **스냅숏**: 레코드 집합을 스냅숏 임을 지정 합니다. 스냅숏으로 쿼리의 결과 이며 특정 시점의 데이터베이스에 대 한 보기. 쿼리의 결과로 검색 된 모든 레코드가 자격 증명이 캐시 되므로 원본 레코드에 변경한 보이지 않습니다.

- **모든 열 바인딩**

   선택한 테이블의 모든 열을 바인딩한 여부를 지정 합니다. 이 상자 (기본값)을 선택 하면 모든 열이 바인딩됩니다. 이 확인란을 선택 하면 열이 바인딩되지 및 레코드 집합 클래스에 수동으로 바인딩해야 합니다.

## <a name="see-also"></a>참고자료

[MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)
