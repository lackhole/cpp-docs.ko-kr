---
title: accelerator 및 accelerator_view 개체 사용
ms.date: 11/04/2016
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
ms.openlocfilehash: 05ca53d075867fefa43f7471bb795040d075274e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405393"
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>accelerator 및 accelerator_view 개체 사용

사용할 수 있습니다는 [가속기](../../parallel/amp/reference/accelerator-class.md) 하 고 [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) 장치 또는 에뮬레이터를 실행 하려면를 지정 하는 클래스에 C++ AMP 코드에서. 여러 장치 또는 에뮬레이터는 메모리 양, 공유 메모리 지원, 디버깅 지원 또는 배정밀도 지원 하 여 다른 시스템 있을 수 있습니다. C++Accelerated Massive Parallelism (C++ AMP) Api는 사용 가능한 가속기를 검사 하는 데 사용할 수 있는 하나를 기본값으로 설정에 여러 번 호출에 대 한 여러 accelerator_views를 지정 하 고 특수 디버깅 작업을 수행을 제공 합니다.

## <a name="using-the-default-accelerator"></a>기본 액셀러레이터를 사용 하 여

C++ AMP 런타임은 특정 항목을 선택 하는 코드를 작성 하지 않는 경우 기본 액셀러레이터 키를 선택 합니다. 런타임에서 다음과 같이 기본 액셀러레이터를 선택합니다.

1. 앱 디버그 모드로 실행 되는 경우 액셀러레이터는 디버깅을 지원 합니다.

2. 그렇지 않은 경우 설정 된 경우, CPPAMP_DEFAULT_ACCELERATOR 환경 변수에 의해 지정 된 액셀러레이터 키입니다.

3. 그렇지 않은 경우는 에뮬레이트되지 않는 장치입니다.

4. 그렇지 않으면 사용 가능한 메모리를 가장 많이 있는 장치입니다.

5. 그렇지 않으면 디스플레이에 연결 되지 않은 장치입니다.

또한 런타임에서 지정 된 `access_type` 의 `access_type_auto` 기본 액셀러레이터 키에 대 한 합니다. 즉, 기본 액셀러레이터는 공유 메모리 지원 되는 경우 및 전용된 (비공유) 메모리와 같을 수를 알고 있는 경우 성능 특성 (대역폭 및 대기 시간).

기본 액셀러레이터 키를 생성 하 고 해당 속성을 검사 하 여 기본 액셀러레이터 키의 속성을 확인할 수 있습니다. 다음 코드 예제에서는 경로, 액셀러레이터 메모리, 공유 메모리 지원, 배정밀도 지원 및 기본 액셀러레이터의 제한적 배정밀도 크기를 인쇄합니다.

```cpp
void default_properties() {
    accelerator default_acc;
    std::wcout << default_acc.device_path << "\n";
    std::wcout << default_acc.dedicated_memory << "\n";
    std::wcout << (accs[i].supports_cpu_shared_memory ?
        "CPU shared memory: true" : "CPU shared memory: false") << "\n";
    std::wcout << (accs[i].supports_double_precision ?
        "double precision: true" : "double precision: false") << "\n";
    std::wcout << (accs[i].supports_limited_double_precision ?
        "limited double precision: true" : "limited double precision: false") << "\n";
}
```

### <a name="cppampdefaultaccelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR 환경 변수

지정 CPPAMP_DEFAULT_ACCELERATOR 환경 변수를 설정할 수 있습니다는 `accelerator::device_path` 기본 액셀러레이터 키입니다. 경로 하드웨어에 따라 다릅니다. 다음 코드에서는 `accelerator::get_all` 함수를 사용 가능한 액셀러레이터 목록을 검색 하 고 경로 및 각 액셀러레이터의 특징을 표시 합니다.

```cpp
void list_all_accelerators()
{
    std::vector<accelerator> accs = accelerator::get_all();

    for (int i = 0; i <accs.size(); i++) {
        std::wcout << accs[i].device_path << "\n";
        std::wcout << accs[i].dedicated_memory << "\n";
        std::wcout << (accs[i].supports_cpu_shared_memory ?
            "CPU shared memory: true" : "CPU shared memory: false") << "\n";
        std::wcout << (accs[i].supports_double_precision ?
            "double precision: true" : "double precision: false") << "\n";
        std::wcout << (accs[i].supports_limited_double_precision ?
            "limited double precision: true" : "limited double precision: false") << "\n";
    }
}
```

## <a name="selecting-an-accelerator"></a>액셀러레이터 키를 선택

액셀러레이터 키를 선택 하려면 사용는 `accelerator::get_all` 해당 속성을 기반으로 하는 메서드를 사용 가능한 액셀러레이터 목록을 검색 하 고 하나를 선택 합니다. 이 예제에는 대부분의 메모리가 있는 액셀러레이터를 선택 하는 방법을 보여 줍니다.

```cpp
void pick_with_most_memory()
{
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator acc_chosen = accs[0];

    for (int i = 0; i <accs.size(); i++) {
        if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {
            acc_chosen = accs[i];
        }
    }

    std::wcout << "The accelerator with the most memory is "
        << acc_chosen.device_path << "\n"
        << acc_chosen.dedicated_memory << ".\n";
}
```

> [!NOTE]
> 반환 되는 가속기 중 `accelerator::get_all` CPU 액셀러레이터는 합니다. CPU 액셀러레이터에서 코드를 실행할 수 없습니다. CPU 액셀러레이터를 필터링 하려면의 값을 비교 합니다 [device_path](reference/accelerator-class.md#device_path) 반환한 액셀러레이터 키의 속성 `accelerator::get_all` 의 값을 사용 하 여를 [accelerator:: cpu_accelerator](reference/accelerator-class.md#cpu_accelerator)합니다. 자세한 내용은이 문서의 "특수 액셀러레이터" 섹션을 참조 하세요.

## <a name="shared-memory"></a>공유 메모리

공유 메모리는 메모리를 CPU와 가속기에서 액세스할 수입니다. 공유 메모리를 사용 하 여 제거 하거나 CPU와 액셀러레이터 간 데이터 복사 오버 헤드를 크게 줄여 줍니다. 메모리를 공유 되지만 CPU와 액셀러레이터를 모두에서 동시에 액세스할 수 없습니다 및 하면 정의 되지 않은 동작입니다. 액셀러레이터 키 속성 [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) 반환 **true** 액셀러레이터가 공유 메모리를 지원 하는 경우 및 [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) property get 기본값 [access_type](reference/concurrency-namespace-enums-amp.md#access_type) 에 할당 된 메모리에 대 한 합니다 `accelerator`-예를 들어 **배열**과 연결 된을 `accelerator`, 또는 `array_view` 에 액세스 하는 개체는 `accelerator`.

C++ AMP 런타임이 자동으로 최적의 기본을 선택 `access_type` 각각에 대해 `accelerator`, 공유 메모리의 성능 특성 (대역폭 및 대기 시간)는 전용된 (비공유) 액셀러레이터 메모리 보다 좋지 않을 수 있습니다 하지만 때 CPU에서 쓰거나 CPU 또는 둘 다에서 읽는 중입니다. 공유 메모리와 CPU에서 읽고 쓰기 위해 전용된 된 메모리를 수행 하는 경우 런타임은 기본적으로 `access_type_read_write`이 고, 그렇지 않으면 런타임은 보다 보수적인 기본값 `access_type`, 응용 프로그램이 메모리에 액세스 하는 경우이 재정의할 수 있습니다. 다른 계산 커널의 패턴 혜택 `access_type`합니다.

다음 코드 예제에 있는지 여부를 기본 액셀러레이터가 공유 메모리를 지원 및 다음 기본 액세스 형식을 재정의 만들고 확인 하는 방법을 보여 줍니다는 `accelerator_view` 에서.

```cpp
#include <amp.h>
#include <iostream>

using namespace Concurrency;

int main()
{
    accelerator acc = accelerator(accelerator::default_accelerator);

    // Early out if the default accelerator doesn’t support shared memory.
    if (!acc.supports_cpu_shared_memory)
    {
        std::cout << "The default accelerator does not support shared memory" << std::endl;
        return 1;
    }

    // Override the default CPU access type.
    acc.set_default_cpu_access_type(access_type_read_write);

    // Create an accelerator_view from the default accelerator. The
    // accelerator_view reflects the default_cpu_access_type of the
    // accelerator it’s associated with.
    accelerator_view acc_v = acc.default_view;
}
```

`accelerator_view` 항상 반영 합니다 `default_cpu_access_type` 의 `accelerator` 연결 된 하며 재정의 또는 변경 하는 인터페이스가 없는 해당 `access_type`합니다.

## <a name="changing-the-default-accelerator"></a>기본 액셀러레이터 변경

호출 하 여 기본 액셀러레이터를 변경할 수는 `accelerator::set_default` 메서드. 앱 당 실행 하 고 변경 해야 모든 코드는 GPU에서 실행 되기 전에 한 번만 기본 액셀러레이터를 변경할 수 있습니다. 액셀러레이터 키를 변경 하는 모든 후속 함수 호출 반환 **false**합니다. 에 대 한 호출에서 다른 액셀러레이터를 사용 하려는 경우 `parallel_for_each`,이 문서의 "여러 액셀러레이터 사용" 섹션을 참조 합니다. 다음 코드 예제는 에뮬레이트되지 않은, 표시 되는 연결 되지 않은 하 고, 이중 정밀도 지 원하는 하나에 기본 액셀러레이터를 설정 합니다.

```cpp
bool pick_accelerator()
{
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator chosen_one;

    auto result = std::find_if(accs.begin(), accs.end(),
        [] (const accelerator& acc) {
            return !acc.is_emulated &&
                acc.supports_double_precision &&
                !acc.has_display;
        });

    if (result != accs.end()) {
        chosen_one = *(result);
    }

    std::wcout <<chosen_one.description <<std::endl;
    bool success = accelerator::set_default(chosen_one.device_path);
    return success;
}
```

## <a name="using-multiple-accelerators"></a>여러 액셀러레이터 사용

앱에서 여러 액셀러레이터를 사용 하는 방법은 두 가지 있습니다.

- 전달할 수 있습니다 `accelerator_view` 개체에 대 한 호출에는 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 메서드.

- 생성할 수 있습니다는 **배열** 특정을 사용 하 여 `accelerator_view` 개체입니다. C + AMP 런타임은 선택 합니다 `accelerator_view` 캡처된 **배열** 람다 식에는 개체.

## <a name="special-accelerators"></a>특수 액셀러레이터

세 가지 특수 액셀러레이터의 장치 경로 속성으로 사용할 수는 `accelerator` 클래스:

- [accelerator::direct3d_ref 데이터 멤버](reference/accelerator-class.md#direct3d_ref): 이 단일 스레드 가속기는 일반 그래픽 카드를 에뮬레이트 하려면 CPU에서 소프트웨어를 사용 합니다. 디버깅을 기본적으로 사용 되지만 하드웨어 액셀러레이터 보다 느리기 때문에 프로덕션 환경에서 유용 하지 않습니다. 또한 DirectX SDK 및 Windows SDK에만 사용할 수 있습니다 및 고객의 컴퓨터에 설치 될 가능성이 있습니다. 자세한 내용은 [GPU 코드 디버그](/visualstudio/debugger/debugging-gpu-code)합니다.

- [accelerator::direct3d_warp 데이터 멤버](reference/accelerator-class.md#direct3d_warp): 이 가속기를 실행 하기 위한 대체 (fallback) 솔루션을 제공 C++ (SSE) 사용 하는 다중 코어 Cpu에서 AMP 코드입니다.

- [accelerator:: cpu_accelerator 데이터 멤버](reference/accelerator-class.md#cpu_accelerator): 스테이징 배열을 설정에 대 한이 가속기를 사용할 수 있습니다. 실행할 수 없습니다 C++ AMP 코드입니다. 자세한 내용은 참조는 [Staging Arrays in C++ AMP](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/11/09/staging-arrays-in-c-amp/) Parallel Programming in Native Code 블로그의에 게시 합니다.

## <a name="interoperability"></a>상호 운용성

C++ AMP 런타임이 간의 상호 운용성을 지원 합니다 `accelerator_view` 클래스와 Direct3D [ID3D11Device 인터페이스](/windows/desktop/api/d3d11/nn-d3d11-id3d11device)합니다. [create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) 메서드는 `IUnknown` 인터페이스와 반환을 `accelerator_view` 개체입니다. 합니다 [get_device](reference/concurrency-direct3d-namespace-functions-amp.md#get_device) 메서드는 `accelerator_view` 개체를 반환 합니다는 `IUnknown` 인터페이스입니다.

## <a name="see-also"></a>참고자료

[C++ AMP(C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[GPU 코드 디버그](/visualstudio/debugger/debugging-gpu-code)<br/>
[accelerator_view 클래스](../../parallel/amp/reference/accelerator-view-class.md)
