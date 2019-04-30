---
title: OLE DB에서 트랜잭션 지원
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
ms.openlocfilehash: 3c71200e39641a69443599e0445f89f469aceeda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389270"
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB에서 트랜잭션 지원

A [트랜잭션](../../data/transactions-mfc-data-access.md) 그룹 또는 일괄 처리에 일련의 데이터 원본에 대 한 업데이트 없음 커밋됩니다 (경우 중 하나가 실패할) 하거나 모두 실패 하 고 한 번에 커밋됩니다 있도록 하는 방법 및 전체 트랜잭션이 롤백됩니다. 이 프로세스 데이터 원본에 대 한 결과의 무결성을 보장 합니다.

OLE DB는 다음 세 가지 메서드를 사용 하 여 트랜잭션을 지원합니다.

- [ITransactionLocal::StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85))

- [ITransaction::Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))

- [ITransaction::Abort](/previous-versions/windows/desktop/ms709833(v=vs.85))

## <a name="relationship-of-sessions-and-transactions"></a>세션 및 트랜잭션과의 관계

단일 데이터 원본 개체를 내부 또는 지정된 된 시간에 트랜잭션 범위 외부의 수는 각각 하나 이상의 세션 개체를 만들 수 있습니다.

세션에 트랜잭션이 입력 하지, 각 메서드 호출에서 데이터 저장소에서 해당 세션 내에서 수행 하는 모든 작업 즉시 커밋됩니다. (이 라고도 암시적 모드나 자동 커밋 모드입니다.)

세션의 트랜잭션을 들어가면 데이터 저장소에서 해당 세션 내에서 수행 하는 모든 작업 해당 트랜잭션의 일부인 및 커밋 또는 중단 단일 단위로 합니다. (이 경우에 따라 라고 수동 커밋 모드로.)

트랜잭션 지원은 공급자별으로 다릅니다. 트랜잭션을 지 원하는 세션 개체를 사용 하는 공급자가 지 원하는 경우 `ITransaction` 고 `ITransactionLocal` (중첩 되지 않은) 트랜잭션을 입력할 수 있습니다. OLE DB 템플릿 클래스 [CSession](../../data/oledb/csession-class.md) 시각적 개체의 트랜잭션 지원을 구현 하는 권장된 방법은 이러한 인터페이스를 지원 하며, C++합니다.

## <a name="starting-and-ending-the-transaction"></a>시작 하 고 트랜잭션이 종료

호출 된 `StartTransaction`, `Commit`, 및 `Abort` 소비자에서 행 집합 개체에서 메서드.

호출 `ITransactionLocal::StartTransaction` 새 로컬 트랜잭션을 시작 합니다. 트랜잭션을 시작 하는, 트랜잭션을 커밋할 때까지 이후 작업에서 지정한 모든 변경 내용은 데이터 저장소에 적용 되지 않습니다.

호출 `ITransaction::Commit` 또는 `ITransaction::Abort` 트랜잭션을 종료 합니다. `Commit` 모든 변경 내용을 데이터 저장소에 적용할 트랜잭션의 범위 내에서 발생 합니다. `Abort` 원인 취소할 트랜잭션 및 데이터 저장소의 범위 내에서 모든 변경 내용을 상태의 왼쪽은 트랜잭션이 시작 되기 전에 했습니다.

## <a name="nested-transactions"></a>중첩 된 트랜잭션

A [트랜잭션 중첩](/previous-versions/windows/desktop/ms716985(v=vs.85)) 세션에 활성 트랜잭션이 이미 있는 경우 새 로컬 트랜잭션을 시작할 때 발생 합니다. 현재 트랜잭션 아래 중첩 트랜잭션으로 새 트랜잭션이 시작 됩니다. 공급자는 중첩 된 트랜잭션을 지원 하지 않으면, 호출 `StartTransaction` 세션에 활성 트랜잭션이 이미 있을 때 XACT_E_XTIONEXISTS를 반환 합니다.

## <a name="distributed-transactions"></a>분산 트랜잭션

분산된 데이터를 업데이트 하는 트랜잭션이 분산된 트랜잭션 둘 이상의 네트워크에 연결 된 컴퓨터 시스템에는 데이터입니다. 분산된 시스템을 통해 트랜잭션을 지원 하려는 경우 OLE DB 트랜잭션 지원이 아닌.NET Framework를 사용 해야 합니다.

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)