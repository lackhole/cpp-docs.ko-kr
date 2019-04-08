---
title: 공급자가 지원하지 않는 데이터 변환
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e60f6cd4f7dca1ed3e176cabefc42f69946436a4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033841"
---
# <a name="converting-data-not-supported-by-the-provider"></a>공급자가 지원하지 않는 데이터 변환

공급자가 지원하지 않는 데이터 형식을 소비자가 요청하면 `IRowsetImpl::GetData`에 대한 OLE DB 공급자 템플릿 코드가 Msdadc.dll을 호출하여 데이터 형식을 변환합니다.

`IRowsetChange`와 같이 데이터 변환이 필요한 인터페이스를 구현할 경우에는 Msdaenum.dll을 호출하여 변환할 수 있습니다. Atldb.h에 정의된 `GetData`를 예제로 사용합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)
