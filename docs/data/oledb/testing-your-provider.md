---
title: 공급자 테스트
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: d7a3adad546834e2bdc80a695f4c3bf2259dc0ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389127"
---
# <a name="testing-your-provider"></a>공급자 테스트

공급자를 해제 하기 전에 표시 된 순서에서 다음 테스트를 수행 해야 합니다. 이러한 테스트의 대부분의 사용자가 제대로 공급자 함수를 보여 줍니다.

1. 테스트를 사용 하 여 공급자를 [소비자](../../data/oledb/creating-an-ole-db-consumer.md) OLE DB 소비자 템플릿을 사용 하 여 작성 된 응용 프로그램입니다. 테스트 소비자 공급자 (모든 코드를 추가 하거나 수정 하는)의 모든 기능 영역을 포함 해야 합니다.

1. ADO를 사용 하 여 작성 한 소비자 응용 프로그램을 사용 하 여 공급자를 테스트 합니다. 대부분의 개발자 (특히: Microsoft Visual Basic 및 Microsoft C# 개발자) 소비자 응용 프로그램에 대 한 ADO 또는 ADO.NET을 사용 합니다. 테스트 소비자는 공급자의 모든 기능 영역을 다루어야 합니다. ADO 소비자 응용 프로그램의 예제를 보려면 [Microsoft Visual Basic의 ADO 코드 예제](https://msdn.microsoft.com/library/ms807514.aspx)합니다.

1. OLE DB 공급자에 대 한 공급자 수준 0 표준을 충족 표시할 (ADO 적합성 테스트 포함) OLE DB 적합성 테스트를 실행 합니다. (수준 0의 설명에 대 한 검색 **OLE DB 수준 0 적합성 테스트** 언제 [OLE DB Programmer's Guide](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). 이러한 테스트와 관련된 설명서에 포함 된 시각적 개체를 사용 하 여 C++ Data Access SDK에 포함 합니다. 이러한 테스트 다른 집계 하는 경우에 공급자 실행 되도록 표시할 도움이 [서비스 공급자](../../data/oledb/ole-db-resource-pooling-and-services.md) 속성을 추가 하거나 수정할 경우 특히 유용 합니다. 규칙 테스트에 대 한 자세한 내용은 Visual Studio Cd 중 하나에 있는 Data Access SDK에 대 한 추가 정보 파일을 참조 하세요.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)