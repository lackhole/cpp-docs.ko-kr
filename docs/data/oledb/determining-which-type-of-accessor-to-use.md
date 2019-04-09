---
title: 사용할 접근자 형식 결정
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
ms.openlocfilehash: 98234852d0577e581135980d6b8e525aeead5dc2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031870"
---
# <a name="determining-which-type-of-accessor-to-use"></a>사용할 접근자 형식 결정

컴파일 타임 또는 런타임에 행 집합의 데이터 형식을 확인할 수 있습니다.

정적 접근자를 사용 하 여 컴파일 시간에 데이터 형식을 결정 해야 할 경우 (같은 `CAccessor`). 수동 또는 사용 하 여 데이터 형식을 확인할 수 있습니다 합니다 **ATL OLE DB 소비자 마법사**합니다.

런타임 시 데이터 형식을 결정 해야 할 경우 동적 사용 (`CDynamicAccessor` 또는 하위) 또는 수동 접근자 (`CManualAccessor`). 이러한 경우에 호출할 수 있습니다 `GetColumnInfo` 형식을 결정할 수 있습니다 열 바인딩 정보를 반환 하는 행 집합에 있습니다.

다음 표에서 소비자 템플릿에서 제공 하는 접근자의 목록을 표시 합니다. 각 접근자에는 각각 장단점이 있습니다. 상황에 따라 하나의 접근자 유형이 요구에 맞게 해야 합니다.

|접근자 클래스|바인딩|매개 변수|주석|
|--------------------|-------------|---------------|-------------|
|`CAccessor`|COLUMN_ENTRY 매크로 사용 하 여 사용자 레코드를 만듭니다. 매크로 접근자에 해당 레코드의 데이터 멤버를 바인딩합니다. 행 집합을 만들면 열 바인딩되지 않은 일 수 없습니다.|예, param_map이 있습니다 매크로 항목을 사용 하 여 합니다. 바인딩되면 매개 변수 바인딩을 해제할 수 없습니다.|약간의 코드가 가장 빠른 접근자입니다.|
|`CDynamicAccessor`|자동.|아니요.|행 집합의 데이터 유형을 알 수 없는 경우에 유용 합니다.|
|`CDynamicParameterAccessor`|자동으로 수 있지만 [재정의](../../data/oledb/overriding-a-dynamic-accessor.md)합니다.|예, 공급자가 지 원하는 경우 `ICommandWithParameters`합니다. 매개 변수는 자동으로 바인딩됩니다.|보다 느린 `CDynamicAccessor` 제네릭 프로시저 호출에 유용 합니다.|
|`CDynamicStringAccessor[A,W]`|자동.|아니요.|문자열 데이터를 데이터 저장소에서 액세스 하는 데이터를 검색 합니다.|
|`CManualAccessor`|사용 하 여 수동 `AddBindEntry`합니다.|사용 하 여 수동으로 `AddParameterEntry`합니다.|빠른; 한 번만 매개 변수 및 열 바인딩됩니다. 사용 하 여 데이터의 형식을 결정 합니다. (참조 [DBVIEWER](https://github.com/Microsoft/VCSamples) 예제에 대 한 샘플.) 보다 더 많은 코드가 필요 `CDynamicAccessor` 또는 `CAccessor`합니다. 같은 OLE DB를 직접 호출 하는 것이 더 합니다.|
|`CXMLAccessor`|자동.|아니요.|문자열 데이터로 데이터 저장소에서 액세스 하는 데이터를 검색 하 고 해당 데이터와 XML 태그의 형식을 지정 합니다.|

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)