---
title: '방법: 초과 구독을 사용 하 여 대기 시간 오프셋'
ms.date: 11/04/2016
helpviewer_keywords:
- oversubscription, using [Concurrency Runtime]
- using oversubscription [Concurrency Runtime]
ms.assetid: a1011329-2f0a-4afb-b599-dd4043009a10
ms.openlocfilehash: d74a081f71f044cab90a8e6fdc64530eaaf87ed8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159940"
---
# <a name="how-to-use-oversubscription-to-offset-latency"></a>방법: 초과 구독을 사용 하 여 대기 시간 오프셋

초과 구독을 대기 시간이 있는 작업을 포함 하는 일부 응용 프로그램의 전반적인 효율성을 개선할 수 있습니다. 이 항목에서는 초과 구독을 사용 하 여 네트워크 연결에서 데이터 읽기를 통해 발생 하는 대기 시간을 오프셋 하는 방법을 보여 줍니다.

## <a name="example"></a>예제

이 예제에서는 합니다 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) HTTP 서버에서 파일을 다운로드 합니다. `http_reader` 클래스에서 파생 되며 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 및 사용 하 여 메시지를 다운로드할 URL 이름을 비동기적으로 읽는 전달 합니다.

`http_reader` 클래스가 사용 하는 [concurrency:: task_group](reference/task-group-class.md) 클래스를 동시에 각 파일을 읽습니다. 각 작업 호출을 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) 메서드를 `_BeginOversubscription` 매개 변수 설정 **true** 현재 컨텍스트에서 초과 구독을 사용 하도록 설정 합니다. 각 작업 (MFC (Microsoft Foundation 클래스)에 다음 사용 하 여 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 하 고 [CHttpFile](../../mfc/reference/chttpfile-class.md) 클래스 파일을 다운로드 합니다. 마지막으로, 각 작업 호출 `Context::Oversubscribe` 사용 하 여 합니다 `_BeginOversubscription` 매개 변수 설정 **false** 초과 구독을 사용 하지 않도록 설정 합니다.

초과 구독을 사용 하는 경우 런타임은 작업을 실행 하는 하나의 추가 스레드를 만듭니다. 이러한 각 스레드가 현재 컨텍스트에서 초과 구독 하 고 있으므로 추가 스레드를 만들 수 있습니다. 합니다 `http_reader` 클래스가 사용 하는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 응용 프로그램을 사용 하는 스레드 수를 제한 하는 개체입니다. 에이전트는 고정된 된 수의 토큰 값을 사용 하 여 버퍼를 초기화합니다. 각 다운로드 작업에 대 한 에이전트 작업을 시작 하 고 다음이 값이 기록 다시 버퍼에는 작업이 완료 된 후 전에 버퍼에서 토큰 값을를 읽습니다. 버퍼가 비어 있는 경우 에이전트는 버퍼에 값을 다시 쓸 다운로드 작업 중 하나에 대 한 대기 합니다.

다음 예제에서는 사용 가능한 하드웨어 스레드 수가 두 배로 하는 동시 작업 수를 제한 합니다. 이 값은 초과 구독을 테스트할 때 사용할 좋은 출발점입니다. 특정 처리 환경에 적합 한 값을 사용 하거나 동적으로 실제 워크 로드에 응답 하도록이 값을 변경할 수 있습니다.

[!code-cpp[concrt-download-oversubscription#1](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_1.cpp)]

이 예제에는 4 개의 프로세서가 있는 컴퓨터에 다음 출력이 생성 됩니다.

```Output
Downloading http://www.adatum.com/...
Downloading http://www.adventure-works.com/...
Downloading http://www.alpineskihouse.com/...
Downloading http://www.cpandl.com/...
Downloading http://www.cohovineyard.com/...
Downloading http://www.cohowinery.com/...
Downloading http://www.cohovineyardandwinery.com/...
Downloading http://www.contoso.com/...
Downloading http://www.consolidatedmessenger.com/...
Downloading http://www.fabrikam.com/...
Downloading http://www.fourthcoffee.com/...
Downloading http://www.graphicdesigninstitute.com/...
Downloading http://www.humongousinsurance.com/...
Downloading http://www.litwareinc.com/...
Downloading http://www.lucernepublishing.com/...
Downloading http://www.margiestravel.com/...
Downloading http://www.northwindtraders.com/...
Downloading http://www.proseware.com/...
Downloading http://www.fineartschool.net...
Downloading http://www.tailspintoys.com/...
Downloaded 1801040 bytes in 3276 ms.
```

이 예제에서는 다른 작업 잠재 작업이 완료 되기를 기다리는 동안 추가 작업 실행 되기 때문에 초과 사용 하는 경우 더 빠르게 실행할 수 있습니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣습니다 또는 라는 파일에 붙여 `download-oversubscription.cpp` 명령에 다음 중 하나를 실행된 한 다음 고는 **Visual Studio 명령 프롬프트** 창.

**cl.exe /EHsc /MD /D "_AFXDLL" download-oversubscription.cpp**

**cl.exe /EHsc /MT download-oversubscription.cpp**

## <a name="robust-programming"></a>강력한 프로그래밍

더 이상 필요 후에 항상 초과 구독 사용 하지 않도록 설정 합니다. 함수를 다른 함수에 의해 throw 되는 예외를 처리 하지 않는 것이 좋습니다. 초과 구독을 함수 반환 되기 전에 해제 하지 않는 경우 추가 병렬 작업 컨텍스트에 초과 구독도 됩니다.

사용할 수는 *Resource Acquisition Is Initialization* (RAII) 패턴을 지정된 된 범위를 초과 구독을 제한 합니다. RAII 패턴에서 데이터 구조는 스택에 할당 됩니다. 해당 데이터 구조를 초기화 하거나 만들어집니다 및 소멸 또는 데이터 구조 소멸 될 때 해당 리소스를 해제 하는 경우 리소스를 획득 합니다. RAII 패턴 바깥쪽 범위의 종료 되기 전에 소멸자가 호출 되는 것을 보장 합니다. 따라서 리소스를 올바르게 관리할 예외가 throw 될 때 함수를 여러 개 포함 된 경우 `return` 문입니다.

다음 예제에서는 명명 된 구조를 정의 `scoped_blocking_signal`합니다. 생성자는 `scoped_blocking_signal` 구조 초과 구독이 있으며 소멸자 초과 구독을 사용 하지 않도록 설정 합니다.

[!code-cpp[concrt-download-oversubscription#2](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_2.cpp)]

다음 예제에서는 본문을 수정 합니다 `download` RAII 해당 초과 구독을 확인 하는 데 사용할 방법을 함수가 반환 되기 전에 사용 하지 않도록 설정 됩니다. 이 방법을 사용 하면를 `download` 메서드는 예외 로부터 안전 합니다.

[!code-cpp[concrt-download-oversubscription#3](../../parallel/concrt/codesnippet/cpp/how-to-use-oversubscription-to-offset-latency_3.cpp)]

## <a name="see-also"></a>참고자료

[컨텍스트](../../parallel/concrt/contexts.md)<br/>
[Context:: oversubscribe 메서드](reference/context-class.md#oversubscribe)
