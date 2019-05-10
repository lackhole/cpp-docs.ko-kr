---
title: '다중 스레딩: MFC 동기화 클래스를 사용 하는 경우'
ms.date: 08/27/2018
helpviewer_keywords:
- threading [MFC], synchronization classes
- resources [C++], multithreading
- synchronization classes [C++]
- synchronization [C++], multithreading
- controlled resource access [C++]
- synchronization access classes [C++]
- threading [C++], synchronization
- multithreading [C++], synchronization classes
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
ms.openlocfilehash: 72cf5310704c1ae959cc012146a03dd32cff4068
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407655"
---
# <a name="multithreading-when-to-use-the-mfc-synchronization-classes"></a>다중 스레딩: MFC 동기화 클래스를 사용 하는 경우

MFC와 함께 제공 되는 다중 스레드 클래스 두 가지 범주로 나뉩니다: 동기화 개체 ([CSyncObject](../mfc/reference/csyncobject-class.md)를 [CSemaphore](../mfc/reference/csemaphore-class.md)를 [CMutex](../mfc/reference/cmutex-class.md), [ CCriticalSection](../mfc/reference/ccriticalsection-class.md), 및 [CEvent](../mfc/reference/cevent-class.md)) 및 동기화 액세스 개체 ([CMultiLock](../mfc/reference/cmultilock-class.md) 하 고 [CSingleLock](../mfc/reference/csinglelock-class.md)).

동기화 클래스는 리소스의 무결성을 보장 하는 리소스에 대 한 액세스 제어 해야 하는 경우에 사용 됩니다. 동기화 액세스 클래스는 이러한 리소스에 대 한 액세스 권한을 얻으려고 사용 됩니다. 이 항목에서는 각 클래스를 사용 하는 경우를 설명 합니다.

사용 해야 하는 동기화 클래스를 확인 하려면 다음 일련의 질문을 요청 합니다.

1. 응용 프로그램 특정 작업이 실행 되는 리소스에 액세스 하기 전에 대기 하는 (예를 들어 데이터에서에서 받아야 하는 통신 포트 파일에 쓸 수 전에)?

   그렇다면 사용 `CEvent`합니다.

2. 수 이상의 스레드가 동일한 응용 프로그램 액세스 내에서이 리소스 한 번에 (예를 들어, 응용 프로그램 허용 같은 문서에 뷰를 사용 하 여 최대 5 개의 창이)?

   그렇다면 사용 `CSemaphore`합니다.

3. 이 리소스를 사용 하 여 둘 이상의 응용 프로그램 수 있습니다 (예를 들어이 리소스는 DLL)?

   그렇다면 사용 `CMutex`합니다.

   그렇지 않은 경우 사용 하 여 `CCriticalSection`입니다.

`CSyncObject` 직접 사용 되지 않습니다. 다른 4 개의 동기화 클래스에 대 한 기본 클래스입니다.

## <a name="example-1-using-three-synchronization-classes"></a>예제 1: 세 가지 동기화 클래스 사용

예를 들어 연결 된 계정 목록을 유지 관리 하는 응용 프로그램을 사용 합니다. 이 응용 프로그램에서는 별도 창에서 검사할 최대 3 개의 계정만 허용 하지만 특정 시점에 하나만 업데이트할 수 있습니다. 계정을 업데이트 되 면 업데이트 된 데이터를 데이터 보관을 네트워크를 통해 전송 됩니다.

이 예제 응용 프로그램에는 세 가지 유형의 동기화 클래스를 모두 사용합니다. 사용 하 여 최대 3 개의 계정을 한 번에 검사할 수 있으므로, `CSemaphore` 3 개의 뷰 개체에 대 한 액세스를 제한 합니다. 보려는 시도가 네 번째 계정 발생 하면 처음 세 창 중 하나가 종료 되거나 실패할 때까지 기다리거나 응용 프로그램입니다. 응용 프로그램에 사용 하 여 계정을 업데이트 되 면 `CCriticalSection` 를 한 번에 하나의 계정만 업데이트 되도록 합니다. 업데이트에 성공한 후 신호를 보냅니다. `CEvent`, 신호를 받을 이벤트를 기다리는 스레드를 해제 합니다. 이 스레드는 데이터 보관 파일에는 새 데이터를 보냅니다.

## <a name="example-2-using-synchronization-access-classes"></a>예제 2: 동기화 액세스 클래스를 사용 하 여

훨씬 간단한 동기화 액세스 클래스를 사용 하 여 선택 합니다. 응용 프로그램 제어 된 단일 리소스에만 액세스와 관련 된 경우 사용 하 여 `CSingleLock`입니다. 사용 하 여 다양 한 제어 된 리소스 중 하나에 대 한 액세스를 해야 하는 경우 `CMultiLock`합니다. 예제 1에서는 `CSingleLock` 사용 되었을, 각각의 경우에서 하나의 리소스에만 특정 시간에 필요 하므로 합니다.

동기화 클래스를 사용 하는 방법에 대 한 자세한 내용은 [다중 스레딩: 동기화 클래스 사용 방법](multithreading-how-to-use-the-synchronization-classes.md)합니다. 동기화에 대 한 자세한 내용은 [동기화](/windows/desktop/Sync/synchronization) Windows SDK에 있습니다. MFC에서 다중 스레딩 지원에 대 한 자세한 내용은 [스레딩 C++ 및 MFC](multithreading-with-cpp-and-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[C++ 및 MFC에서 다중 스레딩](multithreading-with-cpp-and-mfc.md)
