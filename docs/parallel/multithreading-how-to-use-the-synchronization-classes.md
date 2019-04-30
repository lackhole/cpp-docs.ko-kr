---
title: '다중 스레딩: MFC 동기화 클래스 사용 방법'
ms.date: 08/27/2018
helpviewer_keywords:
- MFC [C++], multithreading
- threading [MFC], synchronization classes
- resources [C++], multithreading
- thread-safe classes [C++]
- synchronization classes [C++]
- synchronization [C++], multithreading
- threading [MFC], thread-safe class design
- threading [C++], synchronization
- multithreading [C++], synchronization classes
- threading [C++], thread-safe class design
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
ms.openlocfilehash: 6115d942abc61fbfc9d60ca1ccf97d4b423ff7c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407694"
---
# <a name="multithreading-how-to-use-the-mfc-synchronization-classes"></a>다중 스레딩: MFC 동기화 클래스 사용 방법

다중 스레드 응용 프로그램을 작성할 때 일반적인 문제는 스레드 간에 리소스 액세스를 동기화 합니다. 두 개 이상 있는 스레드가 동시에 액세스 동일한 데이터를 원치 않는 및 예기치 않은 결과가 발생할 수 있습니다. 예를 들어, 하나의 스레드를 업데이트할 수 있습니다 구조체의 내용을 다른 스레드가 동일한 구조체의 내용을 읽는 동안. 이 알 수 없는 데이터 읽기 스레드에 받을: 이전 데이터를 새로 작성된 된 데이터 또는 둘 모두 수 있습니다. MFC는 다양 한 동기화 및이 문제를 해결 하기 위해 동기화 액세스 클래스를 제공 합니다. 이 항목에서는 사용할 수 있는 클래스 및 클래스를 만드는 스레드 안전 일반적인 다중 스레드 응용 프로그램에서 사용 하는 방법을 설명 합니다.

일반적인 다중 스레드 응용 프로그램에 스레드 간에 공유 되는 리소스를 나타내는 클래스입니다. 올바르게 설계 된 완벽 하 게 스레드로부터 안전한 클래스를 모든 동기화 함수를 호출할 필요가 없습니다. 모든 작업은 손상 가져올 수 있습니다 하는 방법에 대 한 하지는 클래스를 효율적으로 사용 하는 방법에 집중할 수 있도록 클래스를 내부적으로 처리 됩니다. 완전 한 스레드 안전 클래스 만들기에 대 한 효율적인 방법은 리소스 클래스에는 동기화 클래스를 병합 하는 것입니다. 동기화 클래스는 공유 클래스로 병합 프로세스는 매우 간단 합니다.

예를 들어 연결 된 계정 목록을 유지 관리 하는 응용 프로그램을 사용 합니다. 이 응용 프로그램에서는 별도 창에서 검사할 최대 3 개의 계정만 허용 하지만 특정 시점에 하나만 업데이트할 수 있습니다. 계정을 업데이트 되 면 업데이트 된 데이터를 데이터 보관을 네트워크를 통해 전송 됩니다.

이 예제 응용 프로그램에는 세 가지 유형의 동기화 클래스를 모두 사용합니다. 사용 하 여 최대 3 개의 계정을 한 번에 검사할 수 있으므로 [CSemaphore](../mfc/reference/csemaphore-class.md) 3 개의 뷰 개체에 대 한 액세스를 제한 합니다. 보려는 시도가 네 번째 계정 발생 하면 처음 세 창 중 하나가 종료 되거나 실패할 때까지 기다리거나 응용 프로그램입니다. 응용 프로그램에 사용 하 여 계정을 업데이트 되 면 [CCriticalSection](../mfc/reference/ccriticalsection-class.md) 를 한 번에 하나의 계정만 업데이트 되도록 합니다. 업데이트에 성공한 후 신호를 보냅니다 [CEvent](../mfc/reference/cevent-class.md), 신호를 받을 이벤트를 기다리는 스레드를 해제 합니다. 이 스레드는 데이터 보관 파일에는 새 데이터를 보냅니다.

##  <a name="_mfc_designing_a_thread.2d.safe_class"></a> 스레드로부터 안전한 클래스 디자인

클래스를 만들려면 완전 한 스레드 안전, 먼저 적절 한 동기화 클래스 공유 클래스 구성원으로 추가 데이터입니다. 이전 계정 관리 예제에서는 `CSemaphore` 데이터 멤버 뷰 클래스에 추가 되는 `CCriticalSection` 데이터 멤버는 연결 된 목록 클래스에 추가 됩니다 및 `CEvent` 데이터 멤버를 데이터 저장소 클래스에 추가 됩니다.

그런 다음 클래스의 데이터를 수정 하거나 제어 리소스에 액세스 하는 모든 멤버 함수에 대 한 동기화 호출을 추가 합니다. 각 함수를 만들어야 하거나를 [CSingleLock](../mfc/reference/csinglelock-class.md) 하거나 [CMultiLock](../mfc/reference/cmultilock-class.md) 개체와 해당 개체의 호출 `Lock` 함수입니다. 개체의 소멸자가 호출 하는 잠금 개체 범위를 벗어나면 제거를 `Unlock` , 리소스를 해제 합니다. 호출할 수는 물론, `Unlock` 직접 하려는 경우.

이 방식으로 스레드 안전 클래스 디자인 다중 스레드 응용 프로그램으로 스레드로부터 안전한 클래스 하지만 높은 수준의 보안을 쉽게 사용할 수 있습니다. 리소스 클래스에는 동기화 개체와 동기화 액세스 개체를 캡슐화 하는 단점은 동기화 코드를 유지 관리 하지 않는 완전 한 스레드 안전 프로그래밍의 이점을 제공 합니다.

다음 코드 예제는 데이터 멤버를 사용 하 여이 메서드를 보여 줍니다 `m_CritSection` (형식의 `CCriticalSection`), 공유 리소스 클래스에서 선언 된 및 `CSingleLock` 개체입니다. 공유 리소스에 대 한 동기화 (에서 파생 된 `CWinThread`) 만들어 시도 `CSingleLock` 의 주소를 사용 하 여 개체를 `m_CritSection` 개체입니다. 리소스 잠금 하려고 시도 하 고 공유 개체에서 작업이 수행 되기를 가져올 때. 작업이 완료 되 면 리소스를 호출 하 여 잠긴 없는 `Unlock`합니다.

```
CSingleLock singleLock(&m_CritSection);
singleLock.Lock();
// resource locked
//.usage of shared resource...

singleLock.Unlock();
```

> [!NOTE]
> `CCriticalSection`를 다른 MFC 동기화 클래스와 달리 없는 시간이 지정된 된 잠금 요청 수입니다. 대기 기간을 스레드에 대 한 유한 하지 않습니다.

이 방식의 단점은 클래스 되도록 동일한 클래스 보다 약간 느리지만 추가 동기화 개체가 없는 경우 또한 둘 이상의 스레드가 개체를 삭제할 수 있습니다 수 있으면 병합된 방법이 될 수 있습니다 항상 작동 하지. 이 경우 별도 동기화 개체를 유지 하는 것이 좋습니다.

다양 한 상황에서 사용 하 여 동기화 클래스를 결정 하는 방법에 대 한 내용은 [다중 스레딩: 동기화 클래스를 사용 하는 경우](multithreading-when-to-use-the-synchronization-classes.md)합니다. 동기화에 대 한 자세한 내용은 참조 하세요. [동기화](/windows/desktop/Sync/synchronization) Windows SDK에 있습니다. MFC에서 다중 스레드 지원에 대 한 자세한 내용은 참조 하세요. [스레딩 C++ 및 MFC](multithreading-with-cpp-and-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[C++ 및 MFC에서 다중 스레딩](multithreading-with-cpp-and-mfc.md)
