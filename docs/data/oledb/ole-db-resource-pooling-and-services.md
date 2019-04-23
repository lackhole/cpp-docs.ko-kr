---
title: OLE DB 리소스 풀링 및 서비스
ms.date: 10/29/2018
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: f46c6f493ae41570c75c384fcc836707faeab99f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023752"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB 리소스 풀링 및 서비스

OLE DB 풀링, 또는 모든 OLE DB 서비스를 사용 하 여 제대로 작동 하려면 공급자에 게 모든 개체의 집계를 지원 해야 합니다. 모든 OLE DB 1.5 또는 이상 공급자의 요구 사항입니다. 중요 한 서비스를 활용 하는 것입니다. 집계를 지원 하지 않는 공급자는 풀링 될 수 없습니다 하 고 추가 서비스가 제공 됩니다.

공급자는 풀링할 수 자유 스레드 모델을 지원 해야 합니다. 리소스 풀 DBPROP_THREADMODEL 속성에 따라 공급자의 스레드 모델을 결정합니다.

공급자 데이터 원본이 초기화 상태인 동안 변경 될 수 있는 전역 연결 상태에 있는 경우 새 DBPROP_RESETDATASOURCE 속성을 지원 해야 합니다. 이 속성은 연결을 다시 사용 되는 공급자가 다음 사용 하기 전에 상태를 정리할 수 있도록 전에 호출 됩니다. 공급자 없습니다 연결과 관련 된 일부 상태를 정리 하면 DBPROPSTATUS_NOTSETTABLE 속성에 대해 반환할 수 있습니다 하 고 연결을 재사용할 수 없는 합니다.

원격 데이터베이스에 연결 하 고 해당 연결 손실 될 지 여부를 검색할 수 있는 공급자 DBPROP_CONNECTIONSTATUS 속성을 지원 해야 합니다. 이 속성은 OLE DB 서비스 하지 않은 연결을 검색 하 고 해당 풀으로 반환 되지 있는지 확인 하는 기능을 제공 합니다.

마지막으로, 자동 트랜잭션 인 리스트 먼 트 일반적으로 작동 하지 풀링 발생 하는 동일한 수준에서 구현 됩니다. 자동 트랜잭션 인 리스트 먼 트를 지 원하는 공급자는 DBPROP_INIT_OLEDBSERVICES 속성을 노출 하 고는 DBPROPVAL_OS_TXNENLISTMENT 선택이 취소 되는 경우 인 리스트 먼 트를 사용 하지 않도록 설정 하 여이 인 리스트 먼이 트를 비활성화를 지원 해야 합니다.

## <a name="see-also"></a>참고자료

[고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)