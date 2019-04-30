---
title: 공급자에 속성 설정
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: 2cbb334ab15912fdcf6980461016976d869f5a84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404509"
---
# <a name="setting-properties-in-your-provider"></a>공급자에 속성 설정

원하는 속성에 대 한 속성 그룹 및 속성 ID를 찾습니다. 자세한 내용은 [OLE DB 속성](/previous-versions/windows/desktop/ms722734(v=vs.85)) 에 **OLE DB Programmer's Reference**합니다.

마법사에서 생성 된 공급자 코드에서 속성 그룹에 해당 하는 속성 맵을 찾습니다. 일반적으로 속성 그룹의 이름을 해당 개체의 이름을 합니다. 명령 또는 행 집합에서 명령 및 행 집합 속성을 찾을 수 있습니다. 데이터 원본 개체에서 데이터 원본 및 초기화 속성을 찾을 수 있습니다.

속성 구조에서 추가 된 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) 매크로입니다. PROPERTY_INFO_ENTRY_EX 네 개의 매개 변수를 사용 합니다.

- 속성에 해당 속성 ID입니다. 속성 이름의 앞에서 처음 7 자로 ("DBPROP_")를 제거 합니다. 예를 들어 추가 하려는 `DBPROP_MAXROWS`, 전달 `MAXROWS` 첫 번째 요소로 합니다. 사용자 지정 속성의 경우 전체 GUID 이름을 전달 (예를 들어 `DBMYPROP_MYPROPERTY`).

- Variant 형식의 속성 (에서 [OLE DB 속성](/previous-versions/windows/desktop/ms722734(v=vs.85)) 에 **OLE DB Programmer's Reference**). VT_ 형식 (예: VT_BOOL 또는 VT_I2) 해당 데이터 형식으로 입력 합니다.

- 읽고 쓸 수 있는 속성 인지 및 속해 있는 그룹을 나타내는 플래그입니다. 예를 들어, 다음 코드는 행 집합 그룹에 속하는 읽기/쓰기 속성을 나타냅니다.

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- 속성의 기본 값입니다. 때문일 `VARIANT_FALSE` 정수 형식, 예를 들어 0 또는 부울 값을 입력 합니다. 속성을 변경 하지 않으면이 값을 있습니다.

    > [!NOTE]
    > 일부 속성 연결 되거나, 책갈피 또는 업데이트와 같은 다른 속성에 연결 합니다. 하나의 속성이 true로 설정 하는 소비자, 다른 속성 설정 해야 합니다. OLE DB 공급자 템플릿 메서드를 통해이 지 원하는 [cutlprops:: Onpropertychanged](../../data/oledb/cutlprops-onpropertychanged.md)합니다.

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB 공급자가 무시 되는 속성

Microsoft OLE DB 공급자는 다음 OLE DB 속성을 무시합니다.

- `DBPROP_MAXROWS` 읽기 전용 공급자에만 (즉, `DBPROP_IRowsetChange` 하 고 `DBPROP_IRowsetUpdate` 됩니다 **false**); 그렇지 않은 경우이 속성이 지원 되지 않습니다.

- `DBPROP_MAXPENDINGROWS` 설정은 무시 됩니다. 공급자는 한계를 지정 합니다.

- `DBPROP_MAXOPENROWS` 설정은 무시 됩니다. 공급자는 한계를 지정 합니다.

- `DBPROP_CANHOLDROWS` 설정은 무시 됩니다. 공급자는 한계를 지정 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)