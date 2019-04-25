---
title: 데이터 소스 및 세션
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 2c11230d106b50e8120dfa9f4e283e97700d2739
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176010"
---
# <a name="data-sources-and-sessions"></a>데이터 소스 및 세션

다음 그림에 연결 및 데이터 원본에 액세스를 지 원하는 클래스를 보여 줍니다. 각 클래스는 표준 OLE DB 구성 요소 구현을 기반으로 합니다.

![데이터 소스 및 세션 클래스](../../data/oledb/media/vcdatasourcesessionclasses.gif "데이터 소스 및 세션 클래스") <br/>
데이터 소스 및 세션 클래스

클래스는 다음과 같습니다.

- [CDataSource](../../data/oledb/cdatasource-class.md)  이 클래스는 OLE DB 공급자를 통해 데이터 소스에 연결하고 관리하는 데이터 소스 개체를 인스턴스화합니다. 데이터 소스는 데이터 소스 주소와 인증 정보 같은 정보를 연결 문자열 형태로 가지고 있습니다.

   이 클래스는 또한, 연결되기 전에 도우미 클래스 [CEnumerator](../../data/oledb/cenumerator-class.md)가 자주 사용되어 시스템에 등록된 사용 가능한 공급자 목록을 얻을 수 있다는 점에서 주목할 만한 가치가 있습니다. 이렇게 되면 사용자는 공급자를 데이터 소스로서 선택할 수 있게 됩니다. 예를 들어, **데이터 연결 속성** 대화 상자에서는 이 클래스를 사용하여 **공급자** 탭의 공급자 목록을 채웁니다. 이는 `SQLBrowseConnect` 또는 `SQLDriverConnect` 함수에 해당합니다.

- [CSession](../../data/oledb/csession-class.md)  이 클래스는 데이터 소스로의 단일 액세스 세션을 나타내는 세션 개체를 인스턴스화합니다. 그러나 데이터 소스에 여러 세션을 만들 수 있습니다. 각 세션마다 데이터 소스의 데이터에 액세스하기 위해 행 집합, 명령 및 기타 개체를 만들 수 있습니다. 세션은 트랜잭션을 처리합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)