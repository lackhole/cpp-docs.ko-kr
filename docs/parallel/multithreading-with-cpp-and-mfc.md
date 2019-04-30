---
title: C++ 및 MFC에서 다중 스레딩
ms.date: 08/27/2018
helpviewer_keywords:
- MFC [C++], multithreading
- threading [C++], MFC
- worker threads [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], about threading
- CWinThread class, purpose of
- multithreading [C++], MFC
- threading [MFC]
- user interface threads [C++]
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
ms.openlocfilehash: bcffc2964d8e15fd47f437366863748175e12622
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407668"
---
# <a name="multithreading-with-c-and-mfc"></a>C++ 및 MFC에서 다중 스레딩

Microsoft Foundation 클래스 (MFC) 라이브러리는 다중 스레드 응용 프로그램에 대 한 지원을 제공합니다. 이 항목에서는 프로세스 및 스레드 및 MFC의 접근 방식 다중 스레딩에 있습니다.

프로세스는 응용 프로그램의 실행 인스턴스입니다. 예를 들어, 메모장 아이콘을 두 번 클릭 하면 메모장을 실행 하는 프로세스를 시작 합니다.

스레드는 프로세스 내에서 실행 경로입니다. 메모장을 시작 하면 운영 체제는 프로세스를 만들고 해당 프로세스의 주 스레드를 실행 하기 시작 합니다. 이 스레드가 종료 되 면 프로세스도 종료 합니다. 주 스레드는 시작 코드에서 함수 주소의 형식에서 운영 체제에 제공 됩니다. 일반적으로 주소는 `main` 또는 `WinMain` 제공 되는 함수입니다.

원하는 경우 응용 프로그램에서 추가 스레드를 만들 수 있습니다. 사용자가 완료 되기를 기다려야 하지 않을 때 백그라운드 또는 유지 관리 태스크를 처리 하는 작업을 수행 하는 것이 좋습니다. MFC 응용 프로그램의 모든 스레드가 표시 됩니다 [CWinThread](../mfc/reference/cwinthread-class.md) 개체입니다. 대부분의 경우에도 필요가 없습니다 명시적으로 이러한 개체를 만들려면 대신 프레임 워크 도우미 함수를 호출 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)를 만들어는 `CWinThread` 개체입니다.

두 가지 유형의 스레드를 구분 하는 MFC: 사용자 인터페이스 스레드와 작업자 스레드입니다. 사용자 인터페이스 스레드 이벤트와 사용자에 의해 생성 된 메시지에 응답 하 고 사용자 입력을 처리 하려면 일반적으로 사용 됩니다. 작업자 스레드 등의 작업을 다시 계산을 사용자 입력 하지 않아도 되는 데 자주 사용 됩니다. 스레드; 유형의 Win32 API를 구분 하지 않습니다. 방금 스레드를 실행할 수 있도록 스레드의 시작 주소를 알고 있어야 합니다. MFC는 사용자 인터페이스에서 이벤트에 대 한 메시지 펌프를 제공 하 여 특별히 사용자 인터페이스 스레드를 처리 합니다. `CWinApp` 파생 되므로 사용자 인터페이스 스레드 개체의 예로 `CWinThread` 이벤트 및 사용자가 생성 하는 메시지를 처리 합니다.

둘 이상의 스레드가 동일한 개체에 액세스 해야 하는 상황에 특별히 주의 해야 합니다. [다중 스레딩: 프로그래밍 팁](multithreading-programming-tips.md) 이러한 상황에서 발생할 수 있는 문제를 해결할 때 사용할 수 있는 기술에 설명 합니다. [다중 스레딩: 동기화 클래스 사용 방법](multithreading-how-to-use-the-synchronization-classes.md) 단일 개체에 여러 스레드의 액세스를에서 동기화에 사용할 수 있는 클래스를 사용 하는 방법에 설명 합니다.

다중 스레드 프로그래밍 작성 및 디버깅 이므로 기본적으로 복잡 하 고 힘든 작업 개체는에 액세스 하지 않도록 둘 이상의 스레드에서 한 번 확인 해야 합니다. 다중 스레딩 항목에서는 다중 스레드 프로그램에서 MFC를 사용 하는 방법만 다중 스레드 프로그래밍의 기본 사항을 대해서도 설명 하지 않습니다. 다중 스레드 MFC 샘플에 포함 된 시각적 개체 C++ 추가 기능 및 MFC;에 포함 되지 않은 Win32 Api에 대 한 몇 가지 다중 스레드를 보여 줍니다. 그러나 이러한는 에서만 시작 지점으로 합니다.

운영 체제 프로세스 및 스레드를 처리 하는 방법에 대 한 자세한 내용은 참조 하세요. [프로세스 및 스레드](/windows/desktop/ProcThread/processes-and-threads) Windows SDK에 있습니다.

MFC 다중 스레딩 지원에 대 한 자세한 내용은 다음 항목을 참조 하세요.

- [다중 스레딩: 사용자 인터페이스 스레드 만들기](multithreading-creating-user-interface-threads.md)

- [다중 스레딩: 작업자 스레드 만들기](multithreading-creating-worker-threads.md)

- [다중 스레딩: 동기화 클래스 사용 방법](multithreading-how-to-use-the-synchronization-classes.md)

- [다중 스레딩: 스레드 종료](multithreading-terminating-threads.md)

- [다중 스레딩: 프로그래밍 팁](multithreading-programming-tips.md)

- [다중 스레딩: 동기화 클래스 사용 시기](multithreading-when-to-use-the-synchronization-classes.md)

## <a name="see-also"></a>참고자료

[레거시 코드에서의 다중 스레드 지원(Visual C++)](multithreading-support-for-older-code-visual-cpp.md)
