---
title: 'TN047: 데이터베이스 트랜잭션 요구 사항 완화'
ms.date: 11/04/2016
f1_keywords:
- vc.data
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
ms.openlocfilehash: 968420658a90c983d8e6c3eaf1e0c61603fc5441
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305348"
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: 데이터베이스 트랜잭션 요구 사항 완화

MFC ODBC 데이터베이스 클래스의 트랜잭션 요구 사항을 설명 했 듯이이 기술 참고 사항은 이제 사용 되지 않습니다. MFC 4.2 이전 데이터베이스 클래스 필요한 커서 후 레코드 집합에서 유지 하는 **CommitTrans** 또는 **롤백** 작업 합니다. ODBC 드라이버와 DBMS이이 수준의 커서 유지를 지원 하지 않은 경우 데이터베이스 클래스 트랜잭션을 활성화 하지 않은 것입니다.

데이터베이스 클래스는 MFC 4.2 부터는 커서 보존 요구 하는 제한을 완화가입니다. 드라이버를 지 원하는 경우 트랜잭션이 사용 됩니다. 그러나 미치는 이제 확인 해야 합니다는 **CommitTrans** 또는 **롤백** 열기 레코드 집합에 대 한 작업입니다. 멤버 함수를 참조 하세요 [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) 하 고 [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
