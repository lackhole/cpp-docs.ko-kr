---
title: '다중 스레딩: MFC에서 작업자 스레드 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
ms.openlocfilehash: f36e02d1ba6074a7ec8203bea761b3528a120162
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212829"
---
# <a name="multithreading-creating-worker-threads-in-mfc"></a>다중 스레딩: MFC에서 작업자 스레드 만들기

작업자 스레드가 사용자 응용 프로그램을 사용 하 여 계속 되도록 기다릴 필요가 없습니다 백그라운드 작업 처리에 주로 사용 됩니다. 다시 계산 또는 백그라운드 인쇄 등의 작업은 작업자 스레드의 좋은 예입니다. 이 항목에서는 작업자 스레드를 만드는 데 필요한 단계를 자세히 설명 합니다. 다루는 주제는 다음과 같습니다.

- [스레드 시작 하기](#_core_starting_the_thread)

- [제어 함수 구현](#_core_implementing_the_controlling_function)

- [예제](#_core_controlling_function_example)

작업자 스레드를 만드는 비교적 간단한 작업입니다. 두 단계만 수행 하면 스레드를 실행 해야 합니다: 제어 함수를 구현 하 고 스레드를 시작 합니다. 클래스를 파생 하는 데 필요한 아닙니다 [CWinThread](../mfc/reference/cwinthread-class.md)합니다. 특수 버전을 사용 해야 하는 경우에 클래스를 파생 시킬 수도 `CWinThread`, 있지만 대부분의 단순한 작업자 스레드에 대 한 필요는 없습니다. 사용할 수 있습니다 `CWinThread` 수정 하지 않고 있습니다.

##  <a name="_core_starting_the_thread"></a> 스레드 시작 하기

두 가지 오버 로드 된 버전의 `AfxBeginThread`: 하나는 작업자 스레드를 만들 수 있습니다 하 고 다른 하나는 사용자 인터페이스 스레드와 작업자 스레드를 모두 만들 수 있습니다. 첫 번째 오버 로드를 사용 하 여 작업자 스레드 실행을 시작 하려면 호출 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 다음 정보를 제공 합니다.

- 제어 함수 주소입니다.

- 제어 함수에 전달할 매개 변수입니다.

- (선택 사항) 스레드의 원하는 우선 순위입니다. 기본값은 보통 우선 순위입니다. 사용 가능한 우선 순위 수준에 대 한 자세한 내용은 참조 하세요. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK에 있습니다.

- (선택 사항) 스레드의 원하는 스택 크기입니다. 기본값은 만드는 스레드와 스택의 동일한 크기가 있습니다.

- (선택 사항) CREATE_SUSPENDED 스레드를 일시 중단 된 상태로 만들 수 하려는 경우. 기본값은 0 또는 스레드를 정상적으로 시작 합니다.

- (선택 사항) 원하는 보안 특성입니다. 기본값은 부모 스레드와 동일한 액세스 합니다. 이 보안 정보를 형식에 대 한 자세한 내용은 참조 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK에 있습니다.

`AfxBeginThread` 만들고 초기화는 `CWinThread` 개체를 시작 하며 나중에 참조할 수 있도록 주소를 반환 합니다. 검사가 모든 개체가 제대로 할당 해제 생성 부분이 실패 했는지를 전체 프로시저에서 수행 됩니다.

##  <a name="_core_implementing_the_controlling_function"></a> 제어 함수 구현

제어 함수는 스레드를 정의 합니다. 이 함수를 입력 하면 스레드가 시작 되 고이 종료 될 때 스레드가 종료 합니다. 이 함수는 다음과 같은 프로토타입이 있어야 합니다.

```
UINT MyControllingFunction( LPVOID pParam );
```

매개 변수는 단일 값입니다. 함수가이 매개 변수에서 받는 값에는 스레드 개체가 만들어졌을 때 생성자에 전달 된 값이입니다. 제어 함수는 선택한 모든 방법에서이 값을 해석할 수 있습니다. 스칼라 값 또는 여러 매개 변수를 포함 하는 구조체에 대 한 포인터를 처리할 수 있습니다 하거나 무시할 수 있습니다. 매개 변수는 구조체를 가리키는 경우 호출자에서 스레드로 데이터를 전달 하 고 스레드에서 다시 호출자에 게 데이터를 전달 하는 뿐만 구조를 사용할 수 있습니다. 이러한 구조체를 사용 하 여 호출자에 게 데이터를 전달할 경우 스레드가 결과가 준비 되 면 호출자에 게 알림 해야 합니다. 작업자 스레드에서 호출자에 게 통신 하는 방법에 대 한 내용은 [다중 스레딩: 프로그래밍 팁](multithreading-programming-tips.md)합니다.

함수 종료 되 면 종료 이유를 나타내는 UINT 값을 반환 해야 합니다. 일반적으로이 종료 코드는 다양 한 유형의 오류를 나타내는 다른 값을 사용 하 여 성공을 나타내기 위해 0. 이것은 종속 구현 합니다. 일부 스레드는 개체의 사용 횟수를 유지 관리 하 고 사용 하 여 해당 개체의 현재 수를 반환할 수 있습니다. 응용 프로그램에서이 값을 검색 하는 방법을 참조 하세요 [다중 스레딩: 스레드 종료](multithreading-terminating-threads.md)합니다.

MFC 라이브러리를 사용 하 여 작성 된 다중 스레드 프로그램에서 수행할 수 있는 몇 가지 제한이 있습니다. 이러한 제한 및 기타 팁 스레드를 사용 하는 방법에 대 한 설명을 보려면 [다중 스레딩: 프로그래밍 팁](multithreading-programming-tips.md)합니다.

##  <a name="_core_controlling_function_example"></a> 제어 함수 예제

다음 예제에서는 제어 함수를 정의 하 고 프로그램의 다른 부분에서 사용 하는 방법을 보여 줍니다.

```
UINT MyThreadProc( LPVOID pParam )
{
    CMyObject* pObject = (CMyObject*)pParam;

    if (pObject == NULL ||
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))
    return 1;   // if pObject is not valid

    // do something with 'pObject'

    return 0;   // thread completed successfully
}

// inside a different function in the program
.
.
.
pNewObject = new CMyObject;
AfxBeginThread(MyThreadProc, pNewObject);
.
.
.
```

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [다중 스레딩: 사용자 인터페이스 스레드 만들기](multithreading-creating-user-interface-threads.md)

## <a name="see-also"></a>참고자료

[C++ 및 MFC에서 다중 스레딩](multithreading-with-cpp-and-mfc.md)
