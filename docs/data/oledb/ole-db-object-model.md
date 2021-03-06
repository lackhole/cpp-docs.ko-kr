---
title: OLE DB 개체 모델
ms.date: 10/22/2018
helpviewer_keywords:
- rowsets, OLE DB object model
- OLE DB, object model
ms.assetid: 1a274a25-c310-4430-a1ec-bd2bd8120eff
ms.openlocfilehash: 303ad4166f0f1126182956fae9c19f513be7cfb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283848"
---
# <a name="ole-db-object-model"></a>OLE DB 개체 모델

OLE DB 개체 모델은 다음 개체 또는 구성 요소가 구성 되어 있습니다. 첫 번째 4 개 개체 또는 나열 된 구성 요소 (데이터 원본, 세션, 명령 및 행 집합) 사용 하면 데이터 원본에 연결 하 고 볼 수 있습니다. 접근자를부터 나머지 부분에서는 표시 되는 데이터로 작업 관련이 있습니다.

## <a name="data-sources"></a>Data Sources

데이터 원본 개체를 사용 하면 파일 또는 DBMS와 같은 데이터 원본에 연결할 수 있습니다. 데이터 원본 개체를 만듭니다 및 연결 관리 권한 및 인증 정보 (예: 로그인 이름 및 암호)를 포함 합니다. 데이터 원본 개체를 하나 이상의 세션을 만들 수 있습니다.

## <a name="sessions"></a>세션

세션을 쿼리하고 데이터를 검색 하도록 데이터 원본 사용 하 여 특정 상호 작용을 관리 합니다. 각 세션은 하나의 트랜잭션입니다. 트랜잭션은은 ACID 테스트에 의해 정의 된 개별 작업 단위입니다. ACID의 정의 참조 하세요 [트랜잭션을](#vcconoledbcomponents_transactions)합니다.

세션 행 집합을 열고 생성 된 데이터 원본 개체를 반환 하는 등의 중요 한 작업을 수행 합니다. 세션 메타 데이터 또는 (예: 테이블 정보) 데이터 원본 자체에 대 한 정보를 반환할 수도 있습니다.

세션 명령을 하나 이상 만들 수 있습니다.

## <a name="commands"></a>명령

명령에는 SQL 문과 같은 텍스트 명령을 실행 합니다. 텍스트 명령 SQL 같은 행 집합을 지정 하는 경우 **선택** 문, 명령 행 집합을 만듭니다.

명령은 컨테이너를 전달한 소비자에서 데이터 원본 개체에 실행에 대 한 공급자의 내부 데이터 저장소 (예: SQL 문) 문자열 텍스트 명령입니다. 일반적으로 텍스트 명령을 SQL **선택** 문 (때문에 경우에 SQL **선택** 행 집합을 지정 합니다. 명령 행 집합을 자동으로 만듭니다).

## <a name="rowsets"></a>행 집합

행 집합 테이블 형식으로 데이터를 표시합니다. 인덱스는 행 집합의 특수 사례입니다. 세션 또는 명령에서 행 집합을 만들 수 있습니다.

### <a name="schema-rowsets"></a>스키마 행 집합

데이터베이스에 대 한 메타 데이터 (구조적 정보)를가지고 있습니다. 스키마 행 집합은 스키마 정보가 포함 된 행 집합입니다. DBMS에 대 한 일부 OLE DB 공급자는 스키마 행 집합 개체를 지원합니다. 스키마 행 집합에 대 한 자세한 내용은 참조 하세요. [스키마 행 집합을 사용 하 여 메타 데이터 구하기](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) 하 고 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)합니다.

### <a name="view-objects"></a>뷰 개체

뷰 개체를 행과 행 집합의 열 하위 집합을 정의 합니다. 자체의 데이터가 없습니다. 뷰 개체는 여러 행 집합의 데이터를 결합할 수 없습니다.

## <a name="accessors"></a>접근자

OLE DB만 접근자의 개념을 사용 합니다. 접근자는 데이터를 소비자에 저장 되는 방법을 설명 합니다. 행 집합 필드 (열)와 소비자에서를 선언 하는 데이터 멤버 (열 지도) 바인딩 집합이 있습니다.

##  <a name="vcconoledbcomponents_transactions"></a> 트랜잭션

트랜잭션 개체는 커밋 또는 최하위 수준이 아닌에서 중첩 된 트랜잭션을 중단 하는 경우에 사용 됩니다. 트랜잭션은은 ACID 테스트에 의해 정의 된 개별 작업 단위입니다. ACID는를 나타냅니다.

- 원자성을 더 작은 작업 단위로 나눌 수 없습니다.

- 동시성을 한 번에 둘 이상의 트랜잭션이 발생할 수 있습니다.

- 격리 한 트랜잭션이 다른 변경에 대 한 지식을 제한적으로

- 내구성 트랜잭션을 사용 하면 영구적으로 변경

## <a name="enumerators"></a>열거자

열거자는 사용 가능한 데이터 원본 및 다른 열거자에 대 한 검색합니다. 사용할 데이터 소스를 검색 하려면 표시기를 사용 하는 소비자는 특정 데이터 원본에 대 한 사용자 지정 되지 않습니다.

Microsoft Data Access SDK에 제공 하는 루트 열거자를 찾고 데이터 원본과 다른 열거자에 대 한 레지스트리를 통과 합니다. 가 다른 열거자 공급자별 방식에서 레지스트리 또는 검색을 트래버스 합니다.

## <a name="errors"></a>오류

모든 OLE DB 개체의 모든 인터페이스는 오류를 생성할 수 있습니다. 오류의 경우에 선택적 사용자 지정 오류 개체를 포함 한 오류에 대 한 추가 정보. 이 정보는 HRESULT에 저장 됩니다.

## <a name="notifications"></a>알림

알림은 행 집합을 공유 하는 협동 소비자 그룹에서 사용 됩니다 (여기서 공유 의미 소비자가 동일한 트랜잭션 내에서 작동 하 것으로 간주 됩니다). 알림을 사용 수행한 행 집합에 대 한 작업에 대 한 알림을 받을 협동 소비자 행 집합을 공유 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)