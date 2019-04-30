---
title: '자동화 서버: 개체 수명 문제'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
ms.openlocfilehash: f9dbc6e4f321ba10fdffa013c158d53b84331e30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392897"
---
# <a name="automation-servers-object-lifetime-issues"></a>자동화 서버: 개체 수명 문제

자동화 클라이언트를 만들거나 OLE 항목을 활성화, 서버 클라이언트 포인터를 전달 개체입니다. 클라이언트가 OLE 함수에 대 한 호출을 통해 개체에 대 한 참조를 설정 [iunknown:: Addref](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)합니다. 클라이언트 호출 될 때까지 적용 되는이 참조가 [iunknown:: Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release)합니다. (Microsoft Foundation Class 라이브러리 OLE 클래스를 사용 하 여 작성 된 클라이언트 응용 프로그램 해야 이러한 호출 하지는 프레임 워크를 수행 합니다.) OLE 시스템 및 서버 자체는 개체에 대 한 참조를 설정할 수 있습니다. 서버 개체에 대 한 외부 참조가 유효으로 개체를 제거 하지 해야 합니다.

파생 된 모든 서버 개체에 대 한 참조 횟수에 대 한 내부 카운트를 유지 하는 프레임 워크 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)합니다. 이 카운트가 때 Automation 클라이언트를 업데이트 또는 다른 엔터티 추가 또는 개체에 대 한 참조를 해제 합니다.

참조 횟수가 0이 되 면 프레임 워크는 가상 함수 호출 [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease)합니다. 이 함수의 기본 구현을 호출 합니다 **삭제** 이 개체를 삭제 하는 연산자입니다.

Microsoft Foundation Class 라이브러리는 외부 클라이언트 응용 프로그램의 개체에 대 한 참조가 있는 경우 응용 프로그램 동작을 제어 하기 위한 추가 기능을 제공 합니다. 각 개체에 대 한 참조 개수를 유지 관리 하는 것 외에도 서버 활성 개체 전역 카운트를 유지 합니다. 전역 함수 [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) 하 고 [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) 활성 개체 응용 프로그램의 개수를 업데이트 합니다. 이 수가 0이 아닌 경우 파일 메뉴에서 종료를 시스템 메뉴에서 닫기를 선택 하면 응용 프로그램 종료 하지 않습니다. 대신, 응용 프로그램의 주 창은 숨겨진 (삭제 되지는 않습니다) 보류 중인 모든 클라이언트 요청이 완료 될 때까지 합니다. 일반적으로 `AfxOleLockApp` 고 `AfxOleUnlockApp` 자동화를 지 원하는 클래스 각각 생성자 및 소멸자에서 호출 됩니다.

경우에 따라 상황 서버는 클라이언트에 아직 개체에 대 한 참조 하는 동안 종료를 강제 합니다. 예를 들어 서버 종속 된 리소스를 사용할 수 없는 서버 오류가 발생 될 수 있습니다. 사용자 개체는 다른 응용 프로그램 참조를 포함 하는 서버 문서를 닫을 수도 있습니다.

Windows SDK에서 참조 하세요 `IUnknown::AddRef` 고 `IUnknown::Release`입니다.

## <a name="see-also"></a>참고자료

[자동화 서버](../mfc/automation-servers.md)<br/>
[AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)
