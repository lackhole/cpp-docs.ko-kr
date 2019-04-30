---
title: 마법사를 사용하지 않고 소비자 만들기
ms.date: 10/12/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: 029fe6866df81d366cc3bc15096f638791faa413
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362506"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>마법사를 사용하지 않고 소비자 만들기

다음 예제에서는 기존 ATL 프로젝트에 OLE DB 소비자 지원을 추가 하는 것을 가정 합니다. MFC 응용 프로그램에 OLE DB 소비자 지원을 추가 하려는 경우 실행 해야 합니다 **MFC 응용 프로그램 마법사**, 모든 지원이 필요한 생성 되 고 응용 프로그램을 실행 하는 데 필요한 MFC 루틴을 호출 합니다.

사용 하지 않고 OLE DB 소비자 지원을 추가 하는 **ATL OLE DB 소비자 마법사**:

- Pch.h 파일에 다음 추가 `#include` 문:

    ```cpp
    #include <atlbase.h>
    #include <atldbcli.h>
    #include <atldbsch.h> // if you are using schema templates
    ```

프로그래밍 방식으로 소비자는 일반적으로 다음과 같은 일련의 작업을 수행합니다.

1. 지역 변수 열에 바인딩되는 사용자 레코드 클래스를 만듭니다. 이 예에서 `CMyTableNameAccessor` 는 사용자 레코드 클래스 (참조 [사용자 레코드](../../data/oledb/user-records.md)). 이 클래스에는 열 지도 및 매개 변수 맵을 포함합니다. 열 지도;에서 지정한 각 필드에 대 한 사용자 레코드 클래스의 데이터 멤버를 선언 합니다. 이러한 데이터 멤버의 각각에 대 한 상태 데이터 멤버 및 길이 데이터 멤버를 선언할 수도 있습니다. 자세한 내용은 [마법사 생성 접근자의 필드 상태 데이터 멤버](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)합니다.

    > [!NOTE]
    > 사용자 고유의 소비자를 작성 하는 경우 데이터 변수가 상태 및 길이 변수 앞에 나와야 합니다.

- 데이터 소스 및 세션을 인스턴스화하십시오. 접근자 및 행 집합의 형식을 사용 하 고 다음 사용 하 여 행 집합을 인스턴스화할 결정 [CCommand](../../data/oledb/ccommand-class.md) 하거나 [CTable](../../data/oledb/ctable-class.md):

    ```cpp
    CDataSource ds;
    CSession ss;
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>
    ```

- 호출 `CoInitialize` COM을 초기화 하려면 이 기본 코드에서 호출 됩니다. 예를 들어:

    ```cpp
    HRESULT hr = CoInitialize(NULL);
    ```

- 호출 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 또는 해당 변형 중 하나입니다.

- 데이터 원본에 대 한 연결, 세션을 연 후 열 및 행 집합 초기화 (열고 경우 명령을 실행할 수도):

    ```cpp
    hr = ds.Open();
    hr = ss.Open(ds);
    hr = rs.Open();            // (Open also executes the command)
    ```

- 필요에 따라 행 집합 속성 설정 사용 하 여 `CDBPropSet::AddProperty` 에 대 한 매개 변수로 전달 하 고 및 `rs.Open`합니다. 이렇게 하는 방법의 예제를 참조 하세요 `GetRowsetProperties` 에 [소비자 마법사 생성 메서드](../../data/oledb/consumer-wizard-generated-methods.md)합니다.

- 이제 데이터를 검색/조작 하는 행 집합을 사용할 수 있습니다.

- 응용 프로그램이 완료 되 면 연결, 세션 및 행 집합을 닫습니다.

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   호출 하려는 명령을 사용 하는 경우 `ReleaseCommand` 후 `Close`합니다. 코드 예제 [ccommand:: Close](../../data/oledb/ccommand-close.md) 를 호출 하는 방법을 보여 줍니다 `Close` 고 `ReleaseCommand`입니다.

- 호출 `CoUnInitialize` COM.의 초기화를 취소 하려면 이 기본 코드에서 호출 됩니다.

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer.md)