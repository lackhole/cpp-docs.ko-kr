---
title: '연습: 에이전트 기반 응용 프로그램 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 1d55c9879a3dd90bb4a40b61a3bf958dbe960bc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378065"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>연습: 에이전트 기반 응용 프로그램 만들기

이 항목에서는 기본 에이전트 기반 응용 프로그램을 만드는 방법을 설명 합니다. 이 연습에서는 텍스트 파일에서 데이터를 비동기적으로 읽어는 에이전트를 만들 수 있습니다. 응용 프로그램의 해당 파일의 내용 체크섬을 계산 하 Adler-32 체크섬 알고리즘을 사용 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료 하려면 다음 항목을 이해 해야 합니다.

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)

- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> 섹션

이 연습에서는 다음 작업을 수행 하는 방법에 설명 합니다.

- [콘솔 응용 프로그램 만들기](#createapplication)

- [File_reader 클래스 만들기](#createagentclass)

- [File_reader 클래스를 사용 하 여 응용 프로그램에서](#useagentclass)

##  <a name="createapplication"></a> 콘솔 응용 프로그램 만들기

이 섹션에는 시각적 개체를 만드는 방법을 보여 줍니다 C++ 콘솔 응용 프로그램에서 사용할 헤더 파일을 참조 하는 프로그램입니다.

#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>시각적 개체를 만들려면 C++ Win32 콘솔 응용 프로그램 마법사를 사용 하 여 응용 프로그램

1. 에 **파일** 메뉴에서 클릭 **새로 만들기**를 클릭 하 고 **프로젝트** 표시할 합니다 **새 프로젝트** 대화 상자.

1. 에 **새 프로젝트** 대화 상자에서를 **Visual C++**  에 노드를 **프로젝트 형식** 창과 선택 **Win32 콘솔 응용 프로그램** 에 **템플릿** 창입니다. 예를 들어, 프로젝트 이름을 입력 `BasicAgent`를 클릭 하 고 **확인** 표시할 합니다 **Win32 콘솔 응용 프로그램 마법사**합니다.

1. 에 **Win32 콘솔 응용 프로그램 마법사** 대화 상자, 클릭 **마침**합니다.

1. Stdafx.h에서 다음 코드를 추가 합니다.

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   기능을 포함 하는 헤더 파일 agents.h 합니다 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 클래스입니다.

1. 응용 프로그램을 빌드하고 실행 하 여 만들어졌는지 확인 합니다. 응용 프로그램을 작성 하는 **빌드** 메뉴에서 클릭 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면 클릭 하 여 응용 프로그램 실행 **디버깅 시작** 에 **디버그** 메뉴.

[[맨 위로 이동](#top)]

##  <a name="createagentclass"></a> File_reader 클래스 만들기

이 섹션에는 만드는 방법을 보여 줍니다는 `file_reader` 클래스입니다. 런타임 자체 컨텍스트에서 작업을 수행 하려면 각 에이전트를 예약 합니다. 따라서 작업을 동기적으로 수행 하지만 비동기적으로 다른 구성 요소와 상호 작용 하는 에이전트를 만들 수 있습니다. `file_reader` 클래스가 지정된 된 입력된 파일에서 데이터를 읽고 지정 된 대상 구성 요소에 해당 파일에서 데이터를 보냅니다.

#### <a name="to-create-the-filereader-class"></a>File_reader 클래스를 만들려면

1. 새 C++ 헤더 파일을 프로젝트입니다. 이렇게 하려면 마우스 오른쪽 단추로 클릭 합니다 **헤더 파일** 노드에서 **솔루션 탐색기**, 클릭 **추가**를 클릭 하 고 **새 항목**. 에 **템플릿을** 창 **헤더 파일 (.h)** 합니다. 에 **새 항목 추가** 대화 상자에서 `file_reader.h` 에 **이름** 상자 하 고 클릭 **추가**합니다.

1. File_reader.h에서 다음 코드를 추가 합니다.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. File_reader.h, 라는 클래스를 만듭니다 `file_reader` 에서 파생 되는 `agent`합니다.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. 다음 데이터 멤버를 추가 합니다 `private` 클래스의 섹션입니다.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` 멤버는 에이전트에서 읽는 파일 이름입니다. 합니다 `_target` 멤버를 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) 에이전트 파일의 내용을 쓰도록 개체입니다. `_error` 멤버는 에이전트의 수명 동안 발생 하는 모든 오류를 저장 합니다.

1. 에 다음 코드를 추가 합니다 `file_reader` 생성자를 `public` 섹션은 `file_reader` 클래스.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   설정 하는 각 생성자 오버 로드는 `file_reader` 데이터 멤버입니다. 두 번째 및 세 번째 생성자 오버 로드를 통해 에이전트를 사용 하 여 특정 스케줄러를 사용 하도록 응용을 프로그램을 수 있습니다. 에이전트를 사용 하 여 기본 스케줄러를 사용 하는 첫 번째 오버 로드 합니다.

1. 추가 된 `get_error` 의 public 섹션에는 메서드를 `file_reader` 클래스입니다.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` 메서드는 에이전트의 수명 동안 발생 하는 모든 오류를 검색 합니다.

1. 구현 된 [concurrency::agent::run](reference/agent-class.md#run) 에서 메서드를 `protected` 클래스의 섹션.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` 메서드 파일을 열고 여기에서 데이터를 읽습니다. `run` 메서드 예외 처리를 사용 하 여 파일 처리 중 발생 하는 모든 오류를 캡처합니다.

   호출 될 때마다가이 메서드는 파일에서 데이터를 읽고 합니다 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) 대상 버퍼에 해당 데이터를 보내는 함수입니다. 처리의 끝을 나타내는 대상 버퍼에 빈 문자열을 보냅니다.

다음 예제에서는 file_reader.h의 전체 내용을 보여 줍니다.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[맨 위로 이동](#top)]

##  <a name="useagentclass"></a> File_reader 클래스를 사용 하 여 응용 프로그램에서

이 섹션에서는 사용 하는 `file_reader` 텍스트 파일의 내용을 읽을 수 있는 클래스입니다. 또한 만드는 방법을 보여 줍니다는 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 이 파일 데이터를 받고 해당 Adler-32 체크섬을 계산 하는 개체입니다.

#### <a name="to-use-the-filereader-class-in-your-application"></a>응용 프로그램에서 file_reader 클래스를 사용 하려면

1. BasicAgent.cpp에서 다음을 추가 `#include` 문입니다.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. BasicAgent.cpp에서 다음을 추가 `using` 지시문입니다.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. 에 `_tmain` 함수를 만들기는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 개체 처리의 끝을 알리는 합니다.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. 만들기는 `call` 데이터를 받을 때 체크섬을 업데이트 하는 개체입니다.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   이 `call` 개체도 설정 하는 `event` 처리의 끝을 알리기 위해 빈 문자열을 받으면 개체입니다.

1. 만들기는 `file_reader` test.txt 파일을 읽고 해당 파일의 내용을 기록 하는 개체는 `call` 개체입니다.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. 에이전트를 시작 하 고 완료 될 때까지 기다립니다.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. 대기는 `call` 모든 데이터를 수신 하 고 완료 하는 개체입니다.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. 오류에 대 한 파일 판독기를 확인 합니다. 오류가 발생 하지 않으면 최종 Adler-32 합계를 계산 하 고 콘솔에 합계를 인쇄 합니다.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

다음 예제에서는 전체 BasicAgent.cpp 파일을 보여 줍니다.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[맨 위로 이동](#top)]

## <a name="sample-input"></a>샘플 입력

다음은 샘플 입력된 파일 text.txt 내용의입니다.

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>샘플 출력

샘플 입력을 사용 하는 경우이 프로그램에는 다음 출력이 생성 됩니다.

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>강력한 프로그래밍

데이터 멤버에 대 한 동시 액세스를 방지 하려면 작업을 수행 하는 메서드를 추가 하는 권장 합니다 `protected` 또는 `private` 클래스의 섹션입니다. 와 에이전트에서 메시지 송신 또는 수신 하는 메서드를 추가는 `public` 클래스의 섹션입니다.

항상 호출 합니다 [concurrency:: agent:: 수행](reference/agent-class.md#done) 에이전트가 완료 된 상태로 전환 하는 방법입니다. 반환 하기 전에 일반적으로이 메서드를 호출 합니다 `run` 메서드.

## <a name="next-steps"></a>다음 단계

에이전트 기반 응용 프로그램의 다른 예제를 보려면 [연습: 교착 상태 방지 조인을 사용 하 여](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)입니다.

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)<br/>
[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)<br/>
[연습: 조인을 사용하여 교착 상태 방지](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
