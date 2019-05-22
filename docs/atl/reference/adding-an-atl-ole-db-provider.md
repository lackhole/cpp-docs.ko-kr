---
title: ATL OLE DB 공급자 추가
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB, adding ATL OLE DB provider to projects
- ATL projects, adding ATL OLE DB providers
- ATL OLE DB providers
ms.assetid: 26fba1e3-880f-4bc6-90e5-2096a48a3a6c
ms.openlocfilehash: 36c07da6249a106836433e127f95258d4ed5b509
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65706938"
---
# <a name="adding-an-atl-ole-db-provider"></a>ATL OLE DB 공급자 추가

::: moniker range="vs-2019"

Visual Studio 2019 이상에서는 ATL OLE DB 공급자 마법사를 사용할 수 없습니다.

::: moniker-end

::: moniker range="<=vs-2017"

이 마법사를 사용하여 프로젝트에 ATL OLE DB 공급자를 추가할 수 있습니다. ATL OLE DB 공급자는 데이터 소스, 세션, 명령 및 행 집합 클래스로 구성됩니다. 프로젝트는 ATL COM 애플리케이션으로 생성된 것이어야 합니다.

## <a name="to-add-an-atl-ole-db-provider-to-your-project"></a>프로젝트에 ATL OLE DB 공급자를 추가하려면 다음을 수행합니다.

1. **클래스 뷰**에서 프로젝트를 마우스 오른쪽 단추로 클릭합니다. 바로 가기 메뉴에서 **추가**를 클릭한 다음, **클래스 추가**를 클릭합니다.

1. **Visual C++** 폴더에서 **ATL OLE DB 공급자** 아이콘을 두 번 클릭하거나 아이콘을 선택하고 **열기**를 클릭합니다.

   ATL OLE DB 공급자 마법사가 열립니다.

1. [ATL OLE DB 공급자 마법사](../../atl/reference/atl-ole-db-provider-wizard.md)에 설명된 대로 설정을 정의합니다.

1. **마침**을 클릭하여 마법사를 닫습니다. 새로 만든 OLE DB 공급자 코드가 프로젝트에 삽입됩니다.

::: moniker-end

## <a name="see-also"></a>참고 항목

[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)
