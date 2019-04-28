---
title: 다중 스레드 Win32 프로그램 작성
ms.date: 11/04/2016
helpviewer_keywords:
- thread stacks [C++]
- resources [C++], multithreading
- stacks [C++]
- shared resources [C++]
- threading [C++], sharing common resources
- multithreading [C++], thread stacks
- multithreading [C++], sharing common resources
- mutual exclusion [C++]
- communications [C++], between threads
- mutex [C++]
- threading [C++], thread stacks
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
ms.openlocfilehash: c8536505882ca9a87aec385ca1c42d652ea84ff7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205519"
---
# <a name="writing-a-multithreaded-win32-program"></a>다중 스레드 Win32 프로그램 작성

여러 스레드를 사용 하 여 프로그램을 작성 하는 경우에 해당 동작을 조정 해야 하 고 [프로그램의 리소스 사용](#_core_sharing_common_resources_between_threads)합니다. 각 스레드에 있는지 확인 해야 [스레드 스택](#_core_thread_stacks)합니다.

##  <a name="_core_sharing_common_resources_between_threads"></a> 스레드 간에 공용 리소스 공유

> [!NOTE]
>  MFC의 관점에서 유사한 내용은 참조 하세요. [다중 스레딩: 프로그래밍 팁](multithreading-programming-tips.md) 고 [다중 스레딩: 동기화 클래스를 사용 하는 경우](multithreading-when-to-use-the-synchronization-classes.md)합니다.

각 스레드가 자체 스택 및 CPU의 자체 복사본을 등록 합니다. 힙 메모리, 파일 및 정적 데이터 등의 다른 리소스는 프로세스의 모든 스레드에 의해 공유 됩니다. 이러한 공용 리소스를 사용 하 여 스레드를 동기화 되어야 합니다. Win32는 세마포, 중요 섹션, 이벤트 및 뮤텍스를 비롯 한 리소스를 동기화 하는 여러 방법을 제공 합니다.

다중 스레드 정적 데이터를 액세스 하는 경우 프로그램은 리소스 충돌에 제공 해야 합니다. 한 스레드가 포함 하는 정적 데이터 구조를 업데이트 하는 프로그램을 고려해 보십시오 *x*를*y* 다른 스레드에 의해 표시할 항목에 대 한 좌표입니다. 업데이트 스레드를 변경 하는 경우는 *x* 조정 하 고 변경 하기 전에 선점 될 합니다 *y* 좌표 인 표시 스레드 수 앞에 예약할 수는 *y* 좌표는 업데이트 합니다. 잘못 된 위치에 항목이 표시 됩니다. 구조에 대 한 액세스를 제어 하려면 세마포를 사용 하 여이 문제를 방지할 수 있습니다.

뮤텍스 (짧은 *mut*ual *ex*clusion) 방법이 서로 비동기적으로 실행 되는 프로세스 또는 스레드 간에 통신 합니다. 이 통신은 일반적으로 잠금 및 잠금 리소스를 해제 하 여 공유 리소스에 대 한 액세스를 제어 하 여 일반적으로 여러 스레드 또는 프로세스의 활동을 조정 하기 위해 사용 됩니다. 이 해결 하기 위해 *x*를*y* 좌표 업데이트 문제, 업데이트 스레드 업데이트를 수행 하기 전에 사용 중인 데이터 구조를 나타내는 뮤텍스를 설정 합니다. 좌표가 모두 처리 된 후 뮤텍스를 지워집니다. 디스플레이 업데이트 하기 전에 지워질 뮤텍스에 대 한 표시 스레드가 대기 해야 합니다. 이 프로세스는 뮤텍스를 기다리는 프로세스 액세스가 차단 되 고 뮤텍스를 지울 때까지 계속할 수 없습니다 때문에 뮤텍스를 차단 이라고 합니다.

Bounce.c 프로그램 에서처럼 [샘플 다중 스레드 C 프로그램](sample-multithread-c-program.md) 명명 된 뮤텍스를 사용 하 여 `ScreenMutex` 화면 업데이트를 조정 합니다. 호출 될 때마다 표시 스레드 중 하나는 화면에 작성할 준비가 되셨나요 `WaitForSingleObject` 에 대 한 핸들을 사용 하 여 `ScreenMutex` 및 나타내는 상수 무한은 `WaitForSingleObject` 호출 제한 시간이 없음을 확인 하 고 뮤텍스에서 차단 해야 합니다. 경우 `ScreenMutex` 분명 대기 함수는 뮤텍스를 다른 스레드에 표시를 방해할 수 없도록 설정 하 고 스레드 실행을 계속 합니다. 그렇지 않으면 스레드가 뮤텍스를 지울 때까지 차단 합니다. 뮤텍스를 호출 하 여 해제 스레드 표시 업데이트가 완료 되 면 `ReleaseMutex`합니다.

화면 표시 하 고 정적 데이터 두 가지 유형만 신중한 관리가 요구 하는 리소스의 키를 누릅니다. 예를 들어 프로그램에 동일한 파일에 액세스 하는 여러 스레드가 있을 수 있습니다. 다른 스레드가 파일 포인터를 이동 했을 수 있으므로 각 스레드는 읽기 또는 쓰기 전에 파일 포인터를 다시 설정 해야 합니다. 또한 각 스레드는 포인터를 배치에 파일을 액세스 하는 시간 사이의 선취 되지 않습니다는 확인 해야 합니다. 이러한 스레드 세마포를 사용 하 여 각 파일 액세스를 사용 하 여 괄호를 사용 하 여 파일에 대 한 액세스를 조정 하기 위해 해야 `WaitForSingleObject` 고 `ReleaseMutex` 호출 합니다. 다음 코드 예제에서는이 기술을 보여 줍니다.

```
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);

WaitForSingleObject( hIOMutex, INFINITE );
fseek( fp, desired_position, 0L );
fwrite( data, sizeof( data ), 1, fp );
ReleaseMutex( hIOMutex);
```

##  <a name="_core_thread_stacks"></a> 스레드 스택

응용 프로그램의 기본 스택 공간을 모두 스레드 1 이라고 하는 실행의 첫 번째 스레드에 할당 됩니다. 결과적으로, 얼마나 많은 메모리를 할당할 추가 각 스레드에 대해 별도 스택에 대 한 프로그램을 지정 해야 합니다. 필요한 경우 운영 체제 스레드의 추가 스택 공간을 할당 하지만 기본 값을 지정 해야 합니다.

첫 번째 인수는 `_beginthread` 호출에 대 한 포인터입니다는 `BounceProc` 스레드를 실행 하는 함수입니다. 두 번째 인수는 스레드에 대 한 기본 스택 크기를 지정합니다. 마지막 인수에 전달 되는 ID 번호는 `BounceProc`합니다. `BounceProc` ID 번호를 사용 하 여 난수 생성기의 초기값으로 및 스레드의 색 특성을 선택 하 고 문자를 표시 합니다.

C 런타임 라이브러리와 Win32 API를 호출 하는 스레드 라이브러리 및 API 함수를 호출 하는 충분 한 스택 공간을 허용 해야 합니다. C `printf` 함수 500 바이트 보다 큰 스택 공간을 차지 하며 Win32 API 루틴을 호출할 때 사용 가능한 스택 공간 2k 있어야 합니다.

각 스레드가 자체 스택, 때문에 거의 정적 데이터를 최대한으로 사용 하 여 데이터 항목에 대 잠재적 충돌을 방지할 수 있습니다. 모든 데이터는 스레드에 private 일 수에 대 한 자동 스택 변수를 사용 하기 위해 프로그램을 디자인 합니다. Bounce.c 프로그램에서 유일한 전역 변수는 뮤텍스 또는 초기화 이후 변경 되지 않는 변수입니다.

또한 Win32 스레드 로컬 저장소 (TLS) 스레드별 데이터 저장을 제공 합니다. 자세한 내용은 [스레드 로컬 저장소 (TLS)](thread-local-storage-tls.md)합니다.

## <a name="see-also"></a>참고자료

[C 및 Win32를 사용한 다중 스레딩](multithreading-with-c-and-win32.md)
