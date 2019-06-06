---
title: 사용자 인터페이스 개체와 관련된 메시지 형식
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.uiobject.msgs
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
ms.openlocfilehash: 37638d12c65986d40e7df9f0fbfdef4b8207e418
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741569"
---
# <a name="message-types-associated-with-user-interface-objects"></a>사용자 인터페이스 개체와 관련된 메시지 형식

다음 표에서는 작업을 하는 개체의 형식과 관련 된 메시지를 보여 줍니다.

### <a name="user-interface-objects-and-associated-messages"></a>사용자 인터페이스 개체 및 관련된 메시지

|개체 ID|메시지|
|---------------|--------------|
|클래스 이름에 포함 된 창을 나타내는|Windows 메시지에 적합 한는 [CWnd](../../mfc/reference/cwnd-class.md)-파생 클래스: 대화 상자, 창, 자식 창, MDI 자식 창 또는 최상위 프레임 창이 있습니다.|
|메뉴 또는 액셀러레이터 키 식별자|명령 메시지 (프로그램 함수를 실행).<br />-UPDATE_COMMAND_UI 메시지 (메뉴 항목을 동적으로 업데이트 함).|
|컨트롤 식별자|선택한 컨트롤 형식에 대 한 알림 메시지를 제어 합니다.|

## <a name="see-also"></a>참고자료

[함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[클래스 구조 탐색](../../ide/navigate-code-cpp.md)
