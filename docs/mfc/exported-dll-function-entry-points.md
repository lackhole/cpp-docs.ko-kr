---
title: 내보낸 DLL 함수 시작 지점
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
ms.openlocfilehash: 129defe39a79fd38211a539a4a85d79d9a3c0998
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405913"
---
# <a name="exported-dll-function-entry-points"></a>내보낸 DLL 함수 시작 지점

DLL의 내보내기 함수를 사용 합니다 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) 매크로 호출 응용 프로그램의 DLL에 대 한 DLL 모듈에서 전환 하는 경우 적절 한 전역 상태를 유지 관리 합니다.

이 매크로 설정 하는 호출 되 면 `pModuleState`에 대 한 포인터는 `AFX_MODULE_STATE` 함수의 포함 하는 범위의 나머지 부분에 대 한 유효한 모듈 상태와 모듈에 대 한 글로벌 데이터를 포함 하는 구조체. 매크로 포함 하는 범위를 벗어나면, 유효한 모듈 상태로 자동으로 복원 됩니다.

이 전환의 인스턴스를 생성 하 여 수행 됩니다는 `AFX_MODULE_STATE` 스택에 클래스입니다. 해당 생성자에서이 현재 모듈 상태에 대 한 포인터를 가져옵니다와이 클래스와 멤버 변수에 저장 설정한 `pModuleState` 새 유효한 모듈 상태입니다. 해당 소멸자에서이 클래스는 유효한 모듈 상태와 해당 멤버 변수에 저장 된 포인터를 복원 합니다.

내보낸된 함수를 DLL의 대화 상자를 시작 하는 것과 같은 경우 함수의 시작 부분에 다음 코드를 추가 해야 합니다.

[!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]

반환 된 상태와 현재 모듈 상태 서로 바뀝니다 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) 현재 범위의 끝까지 합니다.

경우 리소스 Dll에서 문제가 발생 합니다 `AFX_MANAGE_STATE` 매크로 사용 되지 않습니다. 기본적으로 MFC 리소스 템플릿을 로드 하는 기본 응용 프로그램의 리소스 핸들을 사용 합니다. 이 템플릿에 실제로 DLL에 저장 됩니다. 근본 원인은 MFC의 모듈 상태 정보에 의해 교체 되지 않은 `AFX_MANAGE_STATE` 매크로입니다. 리소스 핸들을 MFC 모듈 상태에서 복구 됩니다. 모듈 상태를 전환 하지 않으면 잘못 된 리소스 핸들을 사용 하면 됩니다.

`AFX_MANAGE_STATE` DLL의 모든 함수에 넣이 필요가 없습니다. 예를 들어 `InitInstance` MFC 코드 없는 응용 프로그램에서 호출할 수 있습니다 `AFX_MANAGE_STATE` MFC 모듈 상태 하기 전에 자동으로 이동 하기 때문에 `InitInstance` 한 후 다시 스위치 다음 `InitInstance` 반환 합니다. 모든 메시지 맵 처리기도 마찬가지입니다. 기본 MFC Dll에는 실제로 메시지를 라우팅하기 전에 모듈 상태를 자동으로 전환 하는 특수 마스터 창 프로시저 경우

## <a name="see-also"></a>참고자료

[MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)
