---
title: 공급자 마법사가 생성하는 파일
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 0638680482546f56f26b70660ab43bd9848438a3
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707480"
---
# <a name="provider-wizard-generated-files"></a>공급자 마법사가 생성하는 파일

::: moniker range="vs-2019"

Visual Studio 2019 이상에서는 ATL OLE DB 공급자 마법사를 사용할 수 없습니다.

::: moniker-end

::: moniker range="<=vs-2017"

**ATL OLE DB 공급자 마법사**는 다음 파일을 생성합니다. 다음 항목에서는 짧은 이름인 *Custom*을 사용하지만, 정확한 파일 이름은 공급자를 만들 때 선택한 내용에 따라 결정됩니다.

|파일 이름|설명|
|---------------|-----------------|
|*Custom*RS.cpp|명령 도우미 `Execute` 메서드와 공급자 열 맵을 포함합니다.|
|*Custom*DS.h|데이터 소스 개체를 구현합니다. 이 헤더 파일에는 데이터 소스 속성의 속성 맵이 포함되어 있습니다.|
|*Custom*RS.h|명령과 행 집합 개체를 구현합니다. 이 헤더 파일에는 행 집합 및 명령 속성의 속성 맵이 포함되어 있습니다.|
|*Custom*Sess.h|세션 개체를 구현합니다. 이 헤더 파일에는 세션 속성의 속성 맵이 포함되어 있습니다.|
|*Custom*.rgs|**OLE DB 공급자 마법사**에서 생성된, 등록된 개체를 포함합니다.|

::: moniker-end

## <a name="see-also"></a>참고 항목

[OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)<br/>
