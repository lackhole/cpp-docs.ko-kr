---
title: '다중 스레딩: MFC 사용자 인터페이스 스레드 만들기'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
ms.openlocfilehash: ac22fad95041b07e132d31a2d246e58c3b40d30c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212911"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>다중 스레딩: MFC 사용자 인터페이스 스레드 만들기

사용자 인터페이스 스레드를 응용 프로그램의 다른 부분을 실행 하는 스레드 독립적으로 사용자 이벤트에 응답 하 고 사용자 입력을 처리 하려면 일반적으로 사용 됩니다. 주 응용 프로그램 스레드 (나오는 `CWinApp`-파생 클래스) 이미 생성 되어 시작 합니다. 이 항목에서는 추가 사용자 인터페이스 스레드를 만드는 데 필요한 단계를 설명 합니다.

가장 먼저 해야 할 사용자 인터페이스 스레드를 만드는 경우에서 클래스를 파생 됩니다 [CWinThread](../mfc/reference/cwinthread-class.md)합니다. 선언 하 고이 구현 해야 클래스를 사용 하는 [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) 하 고 [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) 매크로입니다. 이 클래스는 일부 함수를 재정의 해야 하며 다른 사용자가 재정의할 수 있습니다. 이러한 함수 및 수행 해야 할 작업은 다음 표에 표시 됩니다.

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>사용자 인터페이스 스레드를 만들 때 재정의 하려면 함수

|함수|용도|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|스레드가 종료 되 면 정리를 수행 합니다. 일반적으로 재정의 합니다.|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|스레드 인스턴스 초기화를 수행 합니다. 재정의 해야 합니다.|
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)|스레드별 유휴 시간 처리를 수행 합니다. 일반적으로 재정의 되지 않습니다.|
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|디스패치 되기 전에 메시지를 필터링 `TranslateMessage` 고 `DispatchMessage`입니다. 일반적으로 재정의 되지 않습니다.|
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|스레드의 메시지 및 명령 처리기에서 throw 된 처리 되지 않은 예외를 가로챕니다. 일반적으로 재정의 되지 않습니다.|
|[실행](../mfc/reference/cwinthread-class.md#run)|스레드에 대 한 함수를 제어 합니다. 메시지 펌프를 포함합니다. 재정의 된 경우는 거의 없습니다.|

MFC는 매개 변수 오버로드를 통해 `AfxBeginThread`의 두 가지 버전을 제공합니다. 하나는 작업자 스레드만 만들 수 있고, 다른 하나는 사용자 인터페이스 스레드 또는 작업자 스레드를 만들 수 있습니다. 사용자 인터페이스 스레드를 시작 하려면 두 번째 오버 로드를 호출 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 다음 정보를 제공 합니다.

- 합니다 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) 에서 파생 된 클래스의 `CWinThread`합니다.

- (선택 사항) 원하는 우선 순위 수준입니다. 기본값은 보통 우선 순위입니다. 사용 가능한 우선 순위 수준에 대 한 자세한 내용은 참조 하세요. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK에 있습니다.

- (선택 사항) 스레드의 원하는 스택 크기입니다. 기본값은 만드는 스레드와 스택의 동일한 크기가 있습니다.

- (선택 사항) CREATE_SUSPENDED 스레드를 일시 중단 된 상태로 만들 수 하려는 경우. 기본값은 0 또는 스레드를 정상적으로 시작 합니다.

- (선택 사항) 원하는 보안 특성입니다. 기본값은 부모 스레드와 동일한 액세스 합니다. 이 보안 정보를 형식에 대 한 자세한 내용은 참조 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK에 있습니다.

`AfxBeginThread` 대부분의 작업을 수행 합니다. 클래스의 새 개체를 만들고, 사용자가 제공한 정보 및 호출을 사용 하 여 초기화 [CWinThread::CreateThread](../mfc/reference/cwinthread-class.md#createthread) 스레드 실행을 시작 하도록 합니다. 검사가 모든 개체가 제대로 할당 해제 생성 부분이 실패 했는지를 전체 프로시저에서 수행 됩니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [다중 스레딩: 스레드 종료](multithreading-terminating-threads.md)

- [다중 스레딩: 작업자 스레드 만들기](multithreading-creating-worker-threads.md)

- [프로세스 및 스레드](/windows/desktop/ProcThread/processes-and-threads)

## <a name="see-also"></a>참고자료

[C++ 및 MFC에서 다중 스레딩](multithreading-with-cpp-and-mfc.md)
