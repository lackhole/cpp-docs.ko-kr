---
title: 창 프로시저 진입점
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 6d91e2c432588afc5a84f7189fa87a7fc2531b1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372014"
---
# <a name="window-procedure-entry-points"></a>창 프로시저 진입점

MFC 창 프로시저에는 모듈에 정적으로 링크는 특수 창 프로시저 구현 보호 합니다. 링크는 MFC를 사용 하 여 모듈에 연결 될 때 자동으로 발생 합니다. AFX_MANAGE_STATE 매크로 사용 하 여 제대로 유효한 모듈 상태를 설정 하는이 창 프로시저를 호출 `AfxWndProc`는 다시 위임 합니다 `WindowProc` 적절 한 멤버 함수 `CWnd`-파생 개체입니다.

## <a name="see-also"></a>참고자료

[MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)
