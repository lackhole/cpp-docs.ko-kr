---
title: '다중 스레딩: MFC의 스레드를 종료합니다.'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
helpviewer_keywords:
- premature thread termination
- starting threads
- threading [MFC], terminating threads
- multithreading [C++], terminating threads
- threading [C++], stopping threads
- terminating threads
- stopping threads
- AfxEndThread method
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
ms.openlocfilehash: dd11f5db646e172d7ea2c2cc646841249d95ef31
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407733"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>다중 스레딩: MFC의 스레드를 종료합니다.

두 가지 일반적인 문제 때문 스레드가 종료: 제어 함수가 끝나거나 스레드 실행을 완료할 수 없습니다. 워드 프로세서 백그라운드 인쇄를 위해 스레드를 사용 하는 경우 제어 함수는 성공적으로 완료 된 인쇄 하는 경우 정상적으로 종료 됩니다. 그러나 사용자가 인쇄 작업을 취소 합니다는 백그라운드 인쇄 스레드가 완전 종료 되어야 합니다. 이 항목에서는 각 상황을 구현 하는 방법 및 종료 된 후 스레드의 종료 코드를 가져오는 방법을 모두 설명 합니다.

- [정상적인 스레드 종료](#_core_normal_thread_termination)

- [스레드 완전 종료](#_core_premature_thread_termination)

- [스레드의 종료 코드를 검색합니다.](#_core_retrieving_the_exit_code_of_a_thread)

##  <a name="_core_normal_thread_termination"></a> 정상적인 스레드 종료

작업자 스레드의 경우 정상적인 스레드 종료는 간단 합니다. 제어 함수를 종료 하 고 종료 이유를 나타내는 값을 반환 합니다. 하나를 사용 합니다 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) 함수 또는 **반환** 문입니다. 일반적으로 성공적으로 완료 되 면 0을 사용 하지만 사용자의 몫입니다.

사용자 인터페이스 스레드, 프로세스는 간단 합니다:에서 호출에 사용자 인터페이스 스레드 내에서 [PostQuitMessage](/windows/desktop/api/winuser/nf-winuser-postquitmessage) Windows SDK에 있습니다. 유일한 매개 변수는 `PostQuitMessage` 는 스레드의 종료 코드입니다. 작업자 스레드와 마찬가지로 0을 사용 하 여 성공적으로 완료 된 경우를 나타냅니다.

##  <a name="_core_premature_thread_termination"></a> 스레드 완전 종료

스레드를 완전히 종료 하는 것은 간단 합니다. 호출 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) 에서 스레드 내에서. 원하는 종료 코드를 유일한 매개 변수로 전달 합니다. 이 스레드의 실행을 중지, 스레드의 스택이 할당을 취소, 분리는 스레드에 연결 된 모든 Dll 및 스레드 개체가 메모리에서 삭제 합니다.

`AfxEndThread` 종료 될 스레드 내에서 호출 되어야 합니다. 다른 스레드에서 스레드를 종료 하려는 경우 두 스레드 사이 통신 방법을 설정 해야 합니다.

##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> 스레드의 종료 코드를 검색합니다.

작업자 또는 사용자 인터페이스 스레드의 종료 코드를 가져오려면 호출 합니다 [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread) 함수입니다. 이 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요. 이 함수는 스레드에 핸들을 사용 (에 저장 합니다 `m_hThread` 데이터 멤버의 `CWinThread` 개체) 및 DWORD의 주소입니다.

스레드가 여전히 활성 상태 이면 `GetExitCodeThread` 제공 된 DWORD 주소; STILL_ACTIVE 배치 종료 코드는이 주소에 있는 고, 그렇지 합니다.

검색의 종료 코드 [CWinThread](../mfc/reference/cwinthread-class.md) 개체는 추가 단계를 사용 합니다. 기본적으로 때를 `CWinThread` 스레드가 종료 되 면 스레드 개체는 삭제 합니다. 즉, 액세스할 수 없습니다는 `m_hThread` 데이터 멤버 때문에 `CWinThread` 개체가 더 이상 존재 합니다. 이 상황을 방지 하려면 다음 중 하나를 수행 합니다.

- 설정 된 `m_bAutoDelete` 데이터 멤버 FALSE입니다. 따라서는 `CWinThread` 스레드가 종료 된 후 계속 유지 될 개체입니다. 액세스할 수 있습니다는 `m_hThread` 스레드가 종료 된 후 데이터 멤버입니다. 하지만이 기법을 사용 담당 제거는 `CWinThread` 프레임 워크는 삭제 하지 않으므로 자동으로 사용자에 대 한 개체입니다. 이것은 기본적으로 사용되는 방법입니다.

- 스레드 핸들을 개별적으로 저장 합니다. 스레드를 만든 후 복사 해당 `m_hThread` 데이터 멤버 (사용 하 여 `::DuplicateHandle`) 다른 변수에 해당 변수를 통해 액세스 합니다. 이러한 방식으로 개체는 종료할 때 확인할 수 있습니다도 스레드가 종료 된 이유 자동으로 삭제 됩니다. 핸들을 복제 하기 전에 스레드가 종료 되지 않도록 주의 해야 합니다. 이 작업을 수행 하는 가장 안전한 방법은 CREATE_SUSPENDED를 전달 하는 것 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 핸들을 저장 하 고 다음 호출 하 여 스레드를 다시 시작 [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread)합니다.

두 방법 중 하나를 사용 하면 이유를 확인 하려면을 `CWinThread` 종료 하는 개체입니다.

## <a name="see-also"></a>참고자료

[C++ 및 MFC에서 다중 스레딩](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread)
