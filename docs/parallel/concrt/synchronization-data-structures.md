---
title: 동기화 데이터 구조
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
ms.openlocfilehash: f9b949e7782c4b9ca302e9e623ce5f09061c39ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185960"
---
# <a name="synchronization-data-structures"></a>동기화 데이터 구조

동시성 런타임은 여러 스레드에서 공유 데이터에 대 한 액세스를 동기화 할 수 있는 몇 가지 데이터 구조를 제공 합니다. 이러한 데이터 구조는 공유 데이터를 자주 수정 하는 경우에 유용 합니다. 중요 섹션 예를 들어 개체를 동기화 하면 다른 스레드가 공유 리소스를 사용할 때까지 기다립니다. 따라서 이러한 개체를 사용 하 여 자주 사용 되는 데이터에 대 한 액세스를 동기화 하는 경우 응용 프로그램에서 확장성을 잃을 수 있습니다. 합니다 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 를 제공 합니다 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 사용 하면 여러 스레드 또는 동기화에 대 한 필요 없이 작업 간에 리소스를 공유할 수 있습니다. 에 대 한 자세한 내용은 합니다 `combinable` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다.

##  <a name="top"></a> 섹션

이 항목에서는 비동기 메시지 블록 형식은 자세히 설명합니다.

- [critical_section](#critical_section)

- [reader_writer_lock](#reader_writer_lock)

- [scoped_lock 및 scoped_lock_read](#scoped_lock)

- [event](#event)

##  <a name="critical_section"></a> critical_section

합니다 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 클래스 선점 하는 대신 다른 작업을 생성 하는 협조적 상호 제외 개체를 나타냅니다. 중요 섹션은 여러 스레드가 단독 읽기 및 공유 데이터에 대 한 쓰기 액세스를 필요로 할 때 유용 합니다.

`critical_section` 클래스는 재진입 합니다. 합니다 [critical_section](reference/critical-section-class.md#lock) 형식의 예외를 throw [concurrency:: improper_lock](../../parallel/concrt/reference/improper-lock-class.md) 잠금을 이미 소유한 스레드에 의해 호출 되 면 합니다.

### <a name="methods-and-features"></a>메서드 및 기능

다음 표에서 여 정의 된 중요 한 메서드는 `critical_section` 클래스입니다.

|메서드|설명|
|------------|-----------------|
|[lock](reference/critical-section-class.md#lock)|임계 영역을 가져옵니다. 호출 상황에 맞는 될 때까지 차단 잠금을 획득 합니다.|
|[try_lock](reference/critical-section-class.md#try_lock)|중요 섹션을 가져오려고 시도 하지만 차단 하지 않습니다.|
|[unlock](reference/critical-section-class.md#unlock)|중요 섹션을 해제합니다.|

[[맨 위로 이동](#top)]

##  <a name="reader_writer_lock"></a> reader_writer_lock

합니다 [concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 클래스는 공유 데이터에 스레드로부터 안전한 읽기/쓰기 작업을 제공 합니다. 여러 스레드가 공유 리소스에 대 한 동시 읽기 액세스가 필요 하지만 거의 해당 공유 리소스를 쓸 때 판독기/기록기 잠금을 사용 합니다. 이 클래스 언제 든 지 개체에 하나의 스레드가 쓰기 액세스를 제공 합니다.

`reader_writer_lock` 클래스에서 수행할 수 보다는 `critical_section` 때문에 클래스를 `critical_section` 개체 읽기에 대 한 동시 액세스를 방지 하는 공유 리소스에 단독 액세스를 획득 합니다.

같은 합니다 `critical_section` 클래스는 `reader_writer_lock` 클래스 선점 하는 대신 다른 작업을 생성 하는 협조적 상호 제외 개체를 나타냅니다.

스레드가 공유 리소스에 써야 하는 판독기/기록기 잠금을 획득 하 고 리소스에 액세스 해야 하는 다른 스레드에 작성기 잠금이 해제 될 때까지 차단 됩니다. 합니다 `reader_writer_lock` 클래스의 예로를 *쓰기 우선* 대기 중인 판독기의 차단을 해제 하기 전에 대기 중인 기록기를 차단 해제 하는 잠금의 잠금.

같은 합니다 `critical_section` 클래스는 `reader_writer_lock` 클래스는 재진입 합니다. 합니다 [concurrency::reader_writer_lock::lock](reference/reader-writer-lock-class.md#lock) 하 고 [concurrency::reader_writer_lock::lock_read](reference/reader-writer-lock-class.md#lock_read) 메서드 형식의 예외를 throw `improper_lock` 이미 소유한 스레드에 의해 호출 될 경우 잠금입니다.

> [!NOTE]
>  때문에 `reader_writer_lock` 클래스는 재진입, 읽기 전용 잠금이 판독기/기록기 잠금으로 업그레이드 하거나 읽기 전용 잠금이 판독기/기록기 잠금이 다운 그레이드할 수 없습니다. 이러한 작업 중 하나를 수행 하면 지정 되지 않은 동작이 발생 합니다.

### <a name="methods-and-features"></a>메서드 및 기능

다음 표에서 여 정의 된 중요 한 메서드는 `reader_writer_lock` 클래스입니다.

|메서드|설명|
|------------|-----------------|
|[lock](reference/reader-writer-lock-class.md#lock)|잠금에 대 한 읽기/쓰기 액세스를 획득합니다.|
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|잠금에 대 한 읽기/쓰기 액세스를 가져오려고 시도 하지만 차단 하지 않습니다.|
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|잠금에 대 한 읽기 전용 액세스를 획득합니다.|
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|잠금에 대 한 읽기 전용 액세스를 가져오려고 시도 하지만 차단 하지 않습니다.|
|[unlock](reference/reader-writer-lock-class.md#unlock)|잠금을 해제합니다.|

[[맨 위로 이동](#top)]

##  <a name="scoped_lock"></a> scoped_lock 및 scoped_lock_read

합니다 `critical_section` 고 `reader_writer_lock` 클래스 상호 제외 개체를 사용 하는 방법을 간소화 하는 중첩 된 도우미 클래스를 제공 합니다. 이러한 도우미 클래스 라고 *범위 잠금*합니다.

합니다 `critical_section` 클래스를 포함 합니다 [:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) 클래스입니다. 생성자에 제공 된 액세스를 획득 `critical_section` 개체; 개체에 대 한 소멸자 릴리스 액세스 합니다. `reader_writer_lock` 클래스를 포함 합니다 [scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) 클래스와 유사한 `critical_section::scoped_lock`제공에 대 한 쓰기 액세스를 관리 한다는, `reader_writer_lock` 개체입니다. 합니다 `reader_writer_lock` 클래스도 포함 합니다 [concurrency::reader_writer_lock::scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) 클래스입니다. 이 클래스는 제공 된에 대 한 읽기 액세스를 관리 `reader_writer_lock` 개체입니다.

범위가 지정 된 잠금을 사용 하 여 작업할 때는 여러 가지 이점을 제공 `critical_section` 고 `reader_writer_lock` 수동으로 개체입니다. 일반적으로 범위가 지정 된 잠금 스택에 할당 합니다. 범위가 지정 된 잠금 해제 해당 상호 제외 개체에 대 한 액세스를 자동으로; 소멸 될 때 따라서 있습니다 하지 수동으로 해제 기본 개체입니다. 함수를 여러 개 포함 된 경우에 유용 `return` 문입니다. 범위가 지정 된 잠금 수 예외 로부터 안전한 코드를 작성 하는 데도 도움이 됩니다. 경우는 `throw` 문을 사용 하면 스택이 해제 하 고 활성 상태인 모든 범위가 지정 된 잠금에 대 한 소멸자가 호출 되므로 상호 제외 개체 항상 올바르게 해제 됩니다.

> [!NOTE]
>  사용 하는 경우는 `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, 및 `reader_writer_lock::scoped_lock_read` 클래스 내부 상호 제외 개체에 대 한 액세스를 수동으로 해제 하지 마십시오. 잘못 된 상태에서 런타임을 넣으면 합니다.

##  <a name="event"></a> 이벤트

합니다 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 클래스 상태가 받을 수 있거나 신호 되지 않은 동기화 개체를 나타냅니다. 임계 영역, 공유 데이터에 대 한 액세스를 보호 하는 것이 목적인 같은 동기화 개체와 달리 이벤트 흐름 실행을 동기화 합니다.

`event` 클래스는 하나의 태스크가 다른 태스크에 대 한 작업 완료 하는 경우에 유용 합니다. 예를 들어, 파일 또는 네트워크 연결에서 데이터 읽기는 다른 작업이 하나 이상의 태스크 알릴 수 있습니다.

### <a name="methods-and-features"></a>메서드 및 기능

다음 표에서 다양 한 정의한 중요 한 메서드는 `event` 클래스입니다.

|메서드|설명|
|------------|-----------------|
|[wait](reference/event-class.md#wait)|이벤트가 신호를 받을 때까지 기다립니다.|
|[set](reference/event-class.md#set)|이벤트 신호 받음 상태로 설정합니다.|
|[reset](reference/event-class.md#reset)|이벤트 신호 되지 않은 상태로 설정합니다.|
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|여러 이벤트 신호를 받을 때까지 기다립니다.|

### <a name="example"></a>예제

사용 하는 방법을 보여 주는 예는 `event` 클래스를 참조 하십시오 [동기화 데이터 구조는 Windows API와 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)합니다.

[[맨 위로 이동](#top)]

## <a name="related-sections"></a>관련 단원

[동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
Windows API에서 제공 하는 동기화 데이터 구조체의 동작을 비교 합니다.

[동시성 런타임](../../parallel/concrt/concurrency-runtime.md)<br/>
병렬 프로그래밍을 간소화하는 동시성 런타임에 대해 설명하고 관련 항목의 링크를 제공합니다.
