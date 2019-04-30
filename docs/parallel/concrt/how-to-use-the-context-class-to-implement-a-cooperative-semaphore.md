---
title: '방법: 상황에 맞는 클래스를 사용 하 여 공동 작업 세마포 구현'
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 92f77fade972bff1528bc9a22416670354c70f34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366708"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>방법: 상황에 맞는 클래스를 사용 하 여 공동 작업 세마포 구현

이 항목에는 concurrency:: context 클래스를 사용 하 여 공동 작업 세마포 클래스를 구현 하는 방법을 보여 줍니다.

`Context` 클래스를 사용 하면 차단 하거나 현재 실행 컨텍스트를 생성 합니다. 차단 또는 현재 컨텍스트를 생성 합니다. 경우에 유용 현재 컨텍스트에 리소스를 사용할 수 없기 때문에 계속할 수 없습니다. A *세마포* 은 현재 실행 컨텍스트는 리소스를 사용할 수 있을 때까지 기다려야 하는 한 가지 상황은의 예입니다. 임계 영역 개체를 같은 세마포를 리소스에 대 한 배타적 액세스 권한이 한 컨텍스트에서 코드를 사용 하도록 설정 하는 동기화 개체인 경우 그러나 임계 영역 개체와 다르게 세마포를 둘 이상의 컨텍스트에 리소스에 동시에 액세스할 수 있습니다. 컨텍스트의 최대 세마포 잠금이 있으면 각 추가 컨텍스트 잠금을 해제 하는 다른 컨텍스트에 대 한 대기 해야 합니다.

### <a name="to-implement-the-semaphore-class"></a>Semaphore 클래스를 구현 하려면

1. 이라고 하는 클래스를 선언 `semaphore`합니다. 추가 `public` 고 `private` 이 클래스에는 섹션입니다.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. 에 `private` 섹션을 `semaphore` 클래스를 선언를 [std:: atomic](../../standard-library/atomic-structure.md) 세마포 수를 보유 하는 변수 및 [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) 컨텍스트를 보유 하는 개체 세마포를 획득 하기 위해 대기 해야 하는 합니다.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. 에 `public` 부분을 `semaphore` 클래스 생성자를 구현 합니다. 생성자는 사용 된 `long long` 최대 수가 동시에 잠금을 보유할 수 있는 컨텍스트를 지정 하는 값입니다.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. 에 `public` 의 섹션을 `semaphore` 클래스를 구현 합니다는 `acquire` 메서드. 원자 단위 연산으로 횟수 세마포를이 메서드에 줄입니다. 세마포 카운트가 음수 되 면 현재 컨텍스트에 대기 큐와 호출의 끝에 추가 합니다 [concurrency::Context::Block](reference/context-class.md#block) 현재 컨텍스트를 차단 하는 방법입니다.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. 에 `public` 의 섹션을 `semaphore` 클래스를 구현 합니다는 `release` 메서드. 이 메서드는 원자성 작업으로 세마포 수를 늘립니다. 세마포 카운트가 증가 연산 전 음수 이면 컨텍스트가 하나 이상의 잠금을 기다리고 있는 경우 이 경우 대기 큐의 앞에 있는 컨텍스트를 차단 해제 합니다.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>예제

합니다 `semaphore` 때문에이 예제의 클래스는 협조적으로 동작 합니다 `Context::Block` 및 `Context::Yield` 런타임에서 다른 작업을 수행할 수 있도록 메서드 실행을 양보 합니다.

합니다 `acquire` 카운터를 하지만 종료 되지 않습니다 다른 컨텍스트 호출 하기 전에 대기 큐에 컨텍스트를 추가 하는 메서드 감소는 `release` 메서드. 이 고려 하는 `release` 메서드를 호출 하는 스핀 루프를 사용 하 여는 [concurrency::Context::Yield](reference/context-class.md#yield) 대기 하는 방법은 `acquire` 컨텍스트 추가 완료 하는 방법.

`release` 메서드를 호출할 수는 `Context::Unblock` 하기 전에 메서드를 `acquire` 메서드 호출을 `Context::Block` 메서드. 런타임에서 이러한 메서드를 순서에 관계 없이 호출할 수 있으므로이 경합을 방지할 필요가 없습니다. 경우는 `release` 메서드 호출 `Context::Unblock` 하기 전에 `acquire` 메서드 호출 `Context::Block` 동일한 컨텍스트, 해당 상황에 맞는 계속 차단 해제 합니다. 호출할 때마다 런타임은 필요로 `Context::Block` 해당 호출을 사용 하 여 일치 `Context::Unblock`합니다.

다음 예제에서는 전체 `semaphore` 클래스입니다. `wmain` 함수에서는이 클래스의 기본 사용법을 보여 줍니다. `wmain` 함수는 합니다 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘 세마포에 대 한 액세스를 필요로 하는 몇 가지 작업을 만듭니다. 3 개의 스레드가 언제 든 지 잠금을 보유할 수, 있으므로 작업도 완료 하 고 잠금을 해제 하 여 다른 작업 대기 해야 합니다.

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

```Output
In loop iteration 5...
In loop iteration 0...
In loop iteration 6...
In loop iteration 1...
In loop iteration 2...
In loop iteration 7...
In loop iteration 3...
In loop iteration 8...
In loop iteration 9...
In loop iteration 4...
```

에 대 한 자세한 내용은 합니다 `concurrent_queue` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다. 에 대 한 자세한 내용은 합니다 `parallel_for` 알고리즘을 참조 하세요 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `cooperative-semaphore.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc cooperative-semaphore.cpp**

## <a name="robust-programming"></a>강력한 프로그래밍

사용할 수는 *Resource Acquisition Is Initialization* (RAII) 패턴에 대 한 액세스를 제한 하는 `semaphore` 지정된 된 범위 개체입니다. RAII 패턴에서 데이터 구조는 스택에 할당 됩니다. 해당 데이터 구조를 초기화 하거나 만들어집니다 및 소멸 또는 데이터 구조 소멸 될 때 해당 리소스를 해제 하는 경우 리소스를 획득 합니다. RAII 패턴 바깥쪽 범위의 종료 되기 전에 소멸자가 호출 되는 것을 보장 합니다. 따라서 리소스를 올바르게 관리할 예외가 throw 될 때 함수를 여러 개 포함 된 경우 `return` 문입니다.

이라고 하는 클래스를 정의 하는 다음 예제에서는 `scoped_lock`에 정의 되어 있는 `public` 섹션을 `semaphore` 클래스. 합니다 `scoped_lock` 클래스와 유사 합니다 [:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) 하 고 [scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) 클래스입니다. 생성자는 `semaphore::scoped_lock` 클래스에 대 한 액세스를 획득 합니다 지정 `semaphore` 개체 및 소멸자는 개체에 대 한 액세스를 해제 합니다.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
에 전달 되는 작업 함수의 본문을 수정 하는 다음 예제는 `parallel_for` 알고리즘 사용 하 여 RAII 함수가 반환 되기 전에 세마포를 해제 합니다. 이 기술은 작업 함수는 예외 로부터 안전한 것을 확인 합니다.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>참고자료

[컨텍스트](../../parallel/concrt/contexts.md)<br/>
[병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)
