---
title: 사용자 레코드
ms.date: 10/22/2018
f1_keywords:
- COLUMN_ENTRY_MAP
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
ms.openlocfilehash: 5dd7be3eccd59dc1a5a0dc1cd6932ca1310627c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389049"
---
# <a name="user-records"></a>사용자 레코드

정적 접근자를 사용 하 (접근자에서 파생 되는, `CAccessor`), 소비자 사용자 레코드가 있어야 합니다. 사용자 레코드를 C++ 핸들 입력 또는 출력에 데이터 요소를 포함 하는 클래스입니다. 합니다 **ATL OLE DB 소비자 마법사** 소비자에 대 한 사용자 레코드를 생성 합니다. 명령 처리와 같은 선택적 작업에 대 한 사용자 레코드에 메서드를 추가할 수 있습니다.

다음 코드에서는 명령을 처리 하는 샘플 레코드를 보여 줍니다. 사용자 레코드에서 BEGIN_COLUMN_MAP 공급자에서 소비자에 게 전달 하는 데이터 행 집합을 나타냅니다. BEGIN_PARAM_MAP 명령 매개 변수 집합을 나타냅니다. 사용 하 여이 예제는 [CCommand](../../data/oledb/ccommand-class.md) 명령 매개 변수를 처리 하는 클래스입니다. 맵 항목의 데이터 멤버는 클래스의 각 인스턴스에 대 한 메모리의 한 연속 블록으로 오프셋을 나타냅니다. COLUMN_ENTRY 매크로 공급자 측의 PROVIDER_COLUMN_ENTRY 매크로에 해당합니다.

COLUMN_MAP 및 param_map이 있습니다 매크로 대 한 자세한 내용은 참조 하세요. [OLE DB 소비자 템플릿에 대 한 매크로](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)합니다.

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="wizard-generated-user-records"></a>마법사에서 생성 된 사용자 기록

사용 하는 경우는 **ATL OLE DB 소비자 마법사** 소비자를 생성 하려면 OLE DB 템플릿 또는 OLE DB 특성을 사용 하 여 선택할 수 있습니다. 생성 된 코드는 경우에 따라 다릅니다. 이 코드에 대 한 자세한 내용은 참조 하세요. [소비자 마법사 생성 클래스](../../data/oledb/consumer-wizard-generated-classes.md)합니다.

## <a name="user-record-support-for-multiple-accessors"></a>여러 접근자에 대 한 사용자 레코드 지원

여러 접근자를 사용 해야 하는 시나리오의 자세한 내용은 참조 하세요 [행 집합에서 여러 접근자 사용](../../data/oledb/using-multiple-accessors-on-a-rowset.md)합니다.

다음 예에서는 행 집합에서 여러 접근자를 지원 하도록 수정 사용자 레코드를 표시 합니다. BEGIN_COLUMN_MAP END_COLUMN_MAP를 대신 사용 하 여 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) 하 고 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 각 접근자에 대 한 합니다. BEGIN_ACCESSOR 매크로 접근자 수 (0부터 오프셋) 및 접근자가 자동 여부를 지정 합니다. 자동 호출 `GetData` 에 대 한 호출에 자동으로 데이터를 검색할 [MoveNext](../../data/oledb/crowset-movenext.md)합니다. 자동이 아닌 접근자를 사용 하면 명시적으로 데이터를 검색 해야 합니다. 모든 레코드에 대해 검색 하지 않을 하는 대규모 데이터 필드 (예: 비트맵 이미지)에 바인딩하는 경우: 접근자를 사용 합니다.

```cpp
class CMultiArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor
    COLUMN_ENTRY(1, m_szFirstName)
    COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor
    COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)