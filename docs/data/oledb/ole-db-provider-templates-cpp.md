---
title: OLE DB 공급자 템플릿(C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: 793aa08630ec92f99c33c2a4f3688e78630a6c58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361258"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB 공급자 템플릿(C++)

OLE DB는 Microsoft Universal Data Access 전략의 중요 한 부분입니다. OLE DB의 디자인은 데이터 소스의 고성능 데이터 액세스를 허용 합니다. 모든 테이블 형식 데이터는 데이터베이스에서 인지에 관계 없이 OLE DB를 통해 볼 수 있습니다. 유연성은 뛰어난 성능 제공합니다.

에 설명 된 대로 [OLE DB 소비자 및 공급자](../../data/oledb/ole-db-consumers-and-providers.md), OLE DB 소비자 및 공급자의 개념을 사용 합니다. 소비자가 데이터에 대 한 요청 공급자는 소비자에 게 테이블 형식으로 데이터를 반환합니다. 프로그래밍 관점에서이 모델의 가장 중요 한 의미는 공급자는 소비자가 만드는 모든 호출은 구현 해야 하는입니다.

## <a name="what-is-a-provider"></a>공급자란?

OLE DB 공급자는 소비자에 게 영구 원본 (데이터 저장소 라고 함)에서 테이블 형식으로 데이터를 전송 소비자 개체의 인터페이스 호출을 처리 하는 COM 개체의 집합.

공급자는 간단 하거나 복잡할 수 있습니다. 공급자는 더 많은 인터페이스를 구현 하 여 최소한의 기능 또는 본격적인 프로덕션 품질 공급자를 지원할 수 있습니다. 공급자는 테이블을 반환 하 고 클라이언트가 해당 테이블의 형식을 결정 하도록 하 고 해당 데이터에 대 한 작업을 수행할 수 있습니다.

각 공급자는 클라이언트에서 요청을 처리 하는 COM 개체의 표준 집합을 구현, 즉 모든 OLE DB 표준 소비자에서에서 액세스할 수 있습니다 데이터 언어에 관계 없이 모든 공급자 (같은 C++ 및 기본).

각 COM 개체 중 일부는 필요 하 고 선택 사항 중 일부는 여러 인터페이스를 포함 합니다. 공급자는 필수 인터페이스를 구현 하 여 최소 수준의 모든 클라이언트가 사용할 수 있는 기능 (요건)를 보장 합니다. 공급자는 추가 기능을 제공 하는 선택적 인터페이스를 구현할 수 있습니다. 합니다 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md) 이러한 인터페이스에 자세히 설명 합니다. 클라이언트는 항상 호출 해야 `QueryInterface` 공급자는 특정된 인터페이스를 지원 하는지 확인 하 합니다.

## <a name="ole-db-specification-level-support"></a>OLE DB 사양에 대 한 수준 지원

OLE DB 공급자 템플릿 OLE DB 버전 2.7 사양을 지원 합니다. OLE DB 공급자 템플릿을 사용 하는 수준 0 규격 공급자를 구현할 수 있습니다. `Provider` 샘플 예를 들어, 파일 시스템을 쿼리 하는 DOS DIR 명령을 실행 하는 non-MS-DOS 명령 서버를 구현 하는 템플릿을 사용 합니다. `Provider` 샘플 테이블 형식 데이터를 반환 하는 것에 대 한 표준 OLE DB 메커니즘 행 집합의 디렉터리 정보를 반환 합니다.

가장 단순한 유형의 OLE DB 템플릿에서 지 원하는 공급자는 명령이 없거나 읽기 전용 공급자. 책갈피 및 읽기/쓰기 기능으로 명령 사용 하 여 공급자도 지원 됩니다. 추가 코드를 작성 하 여 읽기/쓰기 공급자를 구현할 수 있습니다. 동적 행 집합과 트랜잭션이 현재 버전에서 지원 되지 않지만 원하는 경우 추가할 수 있습니다.

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>OLE DB 공급자를 만들 해야 하는 경우는 있습니다?

사용자 고유의 공급자를 만들 필요가 항상 Microsoft에서 여러 미리 패키지 된, 표준 공급자를 제공 합니다 **데이터 연결 속성** 시각적 개체의 대화 상자 C++합니다. OLE DB 공급자를 만들어야 하는 주된 이유 범용 데이터 액세스 전략을 활용 하는 것입니다. 이렇게 하면의 장점 중 일부 다음과 같습니다.

- 와 같은 모든 언어를 통해 데이터 액세스 C++, Basic 및 Visual Basic Scripting Edition. 사용할 언어의 관계 없이 동일한 방법으로 동일한 데이터에 액세스 하려면 조직에서 다른 프로그래머가 허용 합니다.

- SQL Server, Excel 및 Access와 같은 다른 데이터 원본에 데이터를 엽니다. 이 다른 형식 간에 데이터를 전송 하려는 경우에 유용할 수 있습니다.

- (다른 유형의) 간 데이터 원본 작업에 참여. 데이터 웨어하우징 편리할 수 있습니다. OLE DB 공급자를 사용 하 여 네이티브 형식으로 데이터를 유지 하 고 간단한 작업으로 액세스할 수 수 있습니다.

- 쿼리 처리와 같은 데이터에 추가 기능을 추가합니다.

- 조작 방법을 제어 하 여 데이터 액세스 성능 향상.

- 견고성을 향상 합니다. 독점적 데이터 형식이 있는 경우 해당 하나만 프로그래머에 액세스할 수 있습니다, 위험에 노출 됩니다. OLE DB 공급자를 사용 하는 독점적 형식의 모든 프로그래머에 게 열 수 있습니다.

## <a name="read-only-and-updatable-providers"></a>읽기 전용 및 업데이트할 수 있는 공급자

공급자는 복잡성 및 기능에 크게 달라질 수 있습니다. 읽기 전용 공급자 및 업데이트할 수 있는 공급자에 공급자를 분류 하는 것이 유용 합니다.

- Visual C++ 6.0 읽기 전용 공급자만 지원 합니다. [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md) 읽기 전용 공급자를 만드는 방법에 설명 합니다.
- Visual C++ 업데이트할 수는 업데이트할 수 있는 공급자 지원 (쓸) 데이터 저장소입니다. 업데이트할 수 있는 공급자에 대 한 자세한 내용은 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md); [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 샘플은 업데이트할 수 있는 공급자의 예입니다.

자세한 내용은 다음을 참조하세요.

- [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)

- [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)

- [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>참고자료

[데이터 액세스](../data-access-in-cpp.md)<br/>
[OLE DB SDK 설명서](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[OLE DB 프로그래머 참조](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)<br/>
